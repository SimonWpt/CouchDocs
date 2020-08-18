---
title: call
parent: Tags Reference
layout: default
---

# func
The `<cms:call>`-Tag calls a function with optional parameters.

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

* [func](./func.html)