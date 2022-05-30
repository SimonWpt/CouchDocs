---
title: func
parent: Tags Reference
layout: default
---

# func

The **func** tag works by wrapping a piece of code and executing it sometime later upon a call. Unlike 'cms:capture' the code is not executed immediately.<br>
Enclosed code may be configured to output different results depending on different values of its variables. Tag 'cms:func' then  helps define such variables and, titled with a name, becomes a powerful instrument with unlimited function.

## Parameters

* unnamed, &ndash; mandatory parameter that gives name to the function
* parameters (optional), &ndash; virtually unlimited number of user-defined variables that accept values from a caller.

## Example

```html
<cms:func 'makecoffee' type='cappuccino' size='medium'>
    Making a <cms:show size /> cup of <cms:show type />.<br />
</cms:func>

<cms:call 'makecoffee' />
<cms:call 'makecoffee' 'espresso' 'large' />
<cms:call 'makecoffee' size='small' type='espresso' />
```


## Related Tags

* [call](./call.html)
