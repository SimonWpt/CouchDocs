---
title: get_field
parent: Tags Reference
layout: default
---

# get_field

The **get_field** tag can be used to fetch the value contained within any editable region defined within any template.

This tag replaces the existing `<cms:get_custom_field>` tag which is deprecated. Unlike the `<cms:get_custom_field>` tag, this new tag works with almost all custom field types and also system fields. It takes the same parameters as its older counterpart but can also be used as a tag-pair.

## Parameters

* var
* masterpage
* page

### var

The name of the editable region the value of which is to be fetched.

### masterpage

The name of the template that defines the editable region. This parameter is mandatory.

### page

The name of the page that contains the editable region.  
For non-clonable pages this parameter can be skipped.

Examples -  

**Code:**

```html
<cms:get_field 'address' masterpage='contact.php' />
```

The code above is for non-clonable templates. The example fetches the `'address'` field from `'contact.php'` template.  
  
**Code:**

```html
<cms:get_field 'content' masterpage='news.php' page='some-news' />
```

The code above is for clonable templates. The example fetches the `'content'` field from a page named `'some-news'` belonging to the ``'news.php'`` template.  
  
**Code:**

```html
<cms:get_field 'images' masterpage='news.php' page='some-news' >
    <cms:show_repeatable k_field_name >
        ..
    </cms:show_repeatable>
</cms:get_field>
```

Code above fetches a 'repeatable-region' named 'images' from a clonable template's page.  
Please notice that this was not possible with <cms:get_custom_field>.  

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [show](./show.html)
* [get](./get.html)
* [set](./set.html)
* [pages](./pages.html)
