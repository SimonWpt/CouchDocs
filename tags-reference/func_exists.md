---
title: func_exists
parent: Tags Reference
layout: default
---

# func_exists

The **func_exists** tag can be used to check if a particular 'cms:func' function is available.
```html
<cms:func_exists 'mycond' />
```

## Usage

One scenario for this tag is customization of warnings when some func is not registered.<br>

```html
<cms:if "<cms:func_exists 'makecoffee' />">
    <cms:call 'makecoffee' />
</cms:if>
```

## Parameters

* unnamed

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [func](./func.html)
* [tag_exists](./tag_exists.html)
