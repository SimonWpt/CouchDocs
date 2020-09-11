---
title: not
parent: Tags Reference
layout: default
---

# func
The `<cms:not>`-Tag is used to test the 'reverse' of a logical statement.

## Parameters

* parameters (logical expression)

## Example

```html
<cms:if "<cms:not username = 'admin' />" >
    <h3>Your are user: <cms:show username />!</h3>
    <cms:else />
    <h3>Hello <cms:show username />!</h3>
</cms:if>
```

## Related Tags

* [if](./if.html)
* [else](./else.html)
* [else_if](./else_if.html)
