---
title: Tweaking Ckeditor
parent: Core Concepts
layout: default
---

# Tweaking Ckeditor

Ckeditor aka the `<cms:editable type='richtext' name='my_text' />`-tag helps you editing content in backend.

## There a two scenarios for this tag.

### Inline

A editor put content in a place, where no block elements are allowed. But setting HTML inline tags like `<b>`, `<i>`, `<u>`, `<br>` or `<a>` would make sense:

```html
<h1><cms:show headline/></h1>
```

### Block

A editor put content in a place, where block elements are allowed. He writes `<p>` , `<ul>`, `<h1>` and more. And he can set HTML tags `<b>`, `<i>`, `<u>`, `<br>` or `<a>`, too.

```html
<div class="rte"><cms:show text/></div>
```

## The solution

Most editors are not familiar with the difference between a paragraph and a line break. They will forget, in which case they have to press `enter`' or `shift-enter`. Wouldn't it be great, if we define it for them?

I have some good news for you. In Aug 20, 2020 [@kksid](https://github.com/kksidd) made some changes to [field.php](https://github.com/CouchCMS/CouchCMS/commit/97629caa0c431839a85b927d77daed1de4101ffa#diff-e26c5ea6f12259e5ae18049dc70edce5).

### Extending the kfunctions
Place the following code in your addons/kfunctions.php

```php
$FUNCS->add_event_listener( 'ckeditor_alter_config', function(&$config, $f){
    $classes = explode( ' ', $f->class );
    if( count($classes) ){
        $arr_enter = array( 'ck-enter-p'=>'CKEDITOR.ENTER_P',  'ck-enter-br'=>'CKEDITOR.ENTER_BR', 'ck-enter-div'=>'CKEDITOR.ENTER_DIV' );
        $arr_shift_enter = array( 'ck-shiftenter-p'=>'CKEDITOR.ENTER_P',  'ck-shiftenter-br'=>'CKEDITOR.ENTER_BR', 'ck-shiftenter-div'=>'CKEDITOR.ENTER_DIV' );

        foreach( $classes as $class ){
            if( array_key_exists($class, $arr_enter) ){
                $config['enterMode'] = $arr_enter[$class];
            }

            if( array_key_exists($class, $arr_shift_enter) ){
                $config['shiftEnterMode'] = $arr_shift_enter[$class];
            }
        }
    }
});
```

### Add the right class

If you want to use `<br>`, when `enter` is hit, add the class `ck-enter-br` to the `richtext`-element:

```html
<cms:editable type='richtext' name='my_headline' label='Headline' toolbar='custom'
    custom_toolbar='bold, italic, strike' class='ck-enter-br' />
```

With the right class you can set the behavior of the `richtext`-element, when pressing `enter`:

* `ck-enter-p` creates a new `<p>` *default*
* `ck-enter-br` breaks the line with `<br>`
* `ck-enter-div` creates a new `<div>`

Of course you can change the `shift-enter` behavior, too:

* `ck-shiftenter-p` creates a new `<p>`
* `ck-shiftenter-br` breaks the line with `<br>` *default*
* `ck-shiftenter-div` creates a new `<div>`

There is no need to use the deprecated `nicedit`-tag.

## Related Information

* [forum artice](https://www.couchcms.com/forum/viewtopic.php?f=4&t=12782)
* [richtext](../tags-reference/editable/richtext.html)