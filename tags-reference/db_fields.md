---
title: db_fields
parent: Tags Reference
layout: default
---

# db_fields

The **db_fields** tag can be used to get programmatically a list of all registered names of editables for a template.

The tag is part of DataBound tag suite.

## Usage
Try the following -

```html
<cms:db_fields masterpage=''>
    <cms:dump />
</cms:db_fields>
```
**Catch:** If there are no editable fields defined for a given masterpage, tag will not execute enclosed code.

## Parameters

* masterpage
* page_name
* names
* types
* skip_system
* skip_deleted
* bound
* render_display

### masterpage

This parameter is required and used to specify the template the fields of which are to be enumerated.

### names

Name(s) of fields to fetch. Can have negation.

### types

Type(s) of fields to fetch. Can have negation.

## Variables

Every possible variable associated with a field is set into context. Use 'cms:dump' to view them all.

## Related Tags

