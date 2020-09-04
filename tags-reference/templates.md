---
title: templates
parent: Tags Reference
layout: default
---

# templates

The **templates** tag can be used to enumerate all the templates that are managed by Couch.

Example -

```html
<cms:templates show_hidden='1' order='desc'>
    <cms:dump />
</cms:templates>
```

## Parameters

* show_hidden
* orderby
* order

### show_hidden

By default the hidden templates are not enumerated. This can be changed by setting this parameter to 1\.

### orderby

The templates can be ordered by one of these attributes - _name_, _title_ or _order_. The default is _order_.

### order

Can be set to either _asc_ or _desc_.

## Variables

* k_total
* k_template_id
* k_template_name
* k_template_title
* k_template_desc
* k_template_access_level
* k_template_is_clonable
* k_template_is_commentable
* k_template_is_executable
* k_template_is_hidden
* k_template_order
* k_template_link

## Related Tags

* [pages](./pages.html)
* [folders](./folders.html)
* [archives](./archives.html)
* [comments](./comments.html)
