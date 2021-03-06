---
title: php
parent: Tags Reference
layout: default
---

# php

The **php** tag can be used to execute raw PHP code enclosed within its opening and closing tags. The enclosed PHP code can contain Couch tags which will be fully executed to yield the final PHP code that will be eventually evaled to return the output.

> Take care not to allow execution of arbitrary PHP code as this could have security implications.

Examples -

```html
<cms:php> echo( "Hello World" ); </cms:php>
```

```html
<cms:set k_success2="<cms:php>
    echo(str_replace( \"\n\", '|', \"<cms:show k_success/>\" ));
</cms:php>" />
```

Notice how in the last snippet above, we are using the **php** tag as a parameter of the **set** tag and how we are using the Couch **show** tag as a parameter of the PHP *str_replace* function.

## Parameters

Takes no parameters.

## Variables

Sets no variables.

## Related Tags

* [addslashes](./addslashes.html)