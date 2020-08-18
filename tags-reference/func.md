---
title: cms:func
parent: Tags Reference
layout: default
---

# func
The `<cms:func>`-Tag defines a function with parameter support, which can be called with the  `<cms:call>`-tag.

## Parameters

* unnamed
* parameters (optional)

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