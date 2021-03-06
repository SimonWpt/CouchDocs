---
title: search_form
parent: Tags Reference
layout: default
---

# search_form

The **search_form** is a simple tag that creates a form that could be used with the **search** tag.

Examples -

```html
<cms:search_form />
```

```html
<cms:search_form msg='Search' processor="<cms:show k_site_link/>search.php" />
```

## Parameters

* msg
* processor

### msg

This parameter sets the message displayed within the search textbox. By default the string '_Search.._' gets displayed.

### processor

This parameter sets the _action_ parameter of the generated form. This needs to be set to the URL of the page that has the **pages** tag on it.<br/>
If left empty, the **pages** tag is expected to be on the same page as the **search_form** tag.

## Variables

This tag sets no variables of its own.

## Related Tags

* [search](./search.html)
