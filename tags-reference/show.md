---
title: show
parent: Tags Reference
layout: default
---

# show

The **Show** tag is used to display something on the page.<br/>
It could be a literal string e.g.

```html
<cms:show 'Hello World' />
```

or a variable (both system variables as well as all the editable regions on the page) e.g.

```html
<cms:show k_page_title />
<cms:show my_intro />
```

## Parameters

No named parameters. Uses the first provided parameter.

## Variables

This tag does not set any variables of its own.

## Related Tags

* [get](./get.html)
* [set](./set.html)
* [get\_custom\_field](../get_custom_field.html)
* [pages](./pages.html)
