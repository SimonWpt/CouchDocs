---
title: repeatable
parent: Tags Reference
layout: default
---

# repeatable

Please see [**Core Concepts - Repeatable Regions**](../concepts/repeatable-regions.html) for an in-depth discussion about this tag.

## Parameters

* name
* label
* order
* limit
* offset
* stacked_layout
* startcount

### name

A unique name identifying the repeatable block created by this tag. This parameter is mandatory.

### label

Label instructs Couch to display a more user friendly name than the _name_ attribute above. Unlike _name_, it has no limitation of the type of characters that can be used within it. If _label_ attribute is not supplied, Couch by default uses the _name_ as the _label_.

### order

Can be set to either _asc_ or _desc_ or _random_ for setting the sort order to ascending, descending or random.

### limit

The `'limit'` parameter will make the tag show only the specified number of rows.

```html
<cms:show_repeatable 'contacts' order='desc' >..
```

### offset

The `'offset'` parameter will make the tag to begin showing the rows after skipping the number of rows specified in offset.

```html
<cms:show_repeatable 'contacts' offset='2' >..
```

### stacked_layout

Couch can display the regions stacked vertically (instead of horizontally in a row).

```html
<cms:repeatable name='contacts' label='Contacts' stacked_layout='1'>
```

## Variables

Two new variables are also made available while looping through the rows in repeatable-regions

```html
<cms:show_repeatable 'contacts'>
    <cms:if k_first_row >
        ..
    </cms:if>

    ..

    <cms:if k_last_row >
        ..
    </cms:if>
</cms:show_repeatable>
```

To get the values entered into the editable regions enclosed by this block, use [**show_repeatable**](./show_repeatable.html) tag.
