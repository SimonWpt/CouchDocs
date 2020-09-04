---
title: Customizing the List screen
parent: Core Concepts
layout: default
---

# config_list_view

The `config_list_view`-Tag provides in combination with the `field`-Tag some handy methods for tweaking your admin-panel. You can use it to customize the list view for cloned pages or mosaic.

## Parameters

* limit
* exclude
* searchable

### limit

This sets the number of pages shown on a single screen when pagination is required. e.g.

```html
<cms:config_list_view  limit='20' />
```

### exclude

Can be set to the (comma-separated) 'names' of pages that are to be excluded from the listing.

One use of this feature could be to exclude the vexing 'default' page that Couch automatically creates for all clonable templates.

Previously we had to resort to unpublish this default page and then rename it to something like 'PLEASE DO NOT DELETE' and hope that the warning is needed. Now we can, after unpublishing the default page, rename it to something simpler like 'default-page' and then set the 'exclude' parameter of
`<cms:config_list_view>` to skip this page from the listing e.g.

```html
<cms:config_list_view  exclude='default-page' />
```
### searchable

If this parameter is set to '1', a search box appears above the page listing. It can be useful for templates that can potentially have a large number of pages.

> Please be warned though - this search box uses the same <cms:search /> tag as used on the front-end. As such, it suffers from the same limitation of not searching for words shorter than 4 characters (a limitation MySQL fulltext search). This might limit the usefulness of the search in certain cases.

```html
<cms:config_list_view  searchable='1' />
```

## Example

```html
<cms:config_list_view searchable='1' exclude='default-page' limit='50' />
    <cms:field 'k_selector_checkbox' />
    <cms:field 'k_page_title' />
    <cms:field 'k_page_date' />
    <cms:field 'k_actions' />
</cms:config_list_view>
```


## Related Tags

* [field](./field.html)
* [config_form_view](./config_form_view.html)
