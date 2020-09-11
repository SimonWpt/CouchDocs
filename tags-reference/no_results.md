---
title: no_results
parent: Tags Reference
layout: default
---

# func
The `<cms:no_results>`-Tag can be used with pages, comments, search, related_pages, reverse_related_pages and query tags for conditions where the number of pages fetched by these tags is zero.

## Parameters

* unnamed

## Example

```html
<cms:pages ..>
   ...

   <cms:no_results>
      <h3>No pages found</h3>
   </cms:no_results>
</cms:pages>
```

## Related Tags

* [comments](./comments.html)
* [pages](./pages.html)
* [related_pages](./related_pages.html)
* [search](./search.html)
* [query](./query.html)
