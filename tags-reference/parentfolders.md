---
title: parentfolders
parent: Tags Reference
layout: default
---

# parentfolders

The **parentfolders** tag enumerates all the ancestor folders of a given folder.

```html
<cms:parentfolders folder='china' >
    <a href="<cms:show k_folder_link/>"><cms:show k_folder_title/></a>&nbsp;>
</cms:parentfolders>
```

The snippet above will iterate through all the ancestor folders of the folder named 'china', starting from the topmost ancestor.

Please see [**Core Concepts - Folders**](../concepts/using-folders.html#parents-and-children) for more info.

## Parameters

* folder
* masterpage

### folder

The folder the parents of which are to be enumerated.

### masterpage

The template containing the folder above. If skipped, the template of the current executing page is used.

## Variables

At each iteration, this tag sets variables that describe the parent folder being enumerated.

* k_folder_id
* k_folder_name
* k_folder_title
* k_folder_desc
* k_folder_link
* k_folder_pagecount
* k_folder_totalpagecount
* k_level

## Related Tags

* [folder](./folder.html)
* [folders](./folders.html)
* [listfolders](./listfolders.html)
* [dropdownfolders](./dropdownfolders.html)
* [is_ancestor](./is_ancestor.html)
* [breadcrumbs](./breadcrumbs.html)
