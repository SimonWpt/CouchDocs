---
title: block_parent
parent: Tags Reference
layout: default
---

# block_parent

`<cms:block_parent />` fetches the parent block's original code so the effective child code becomes a mix of the parent code plus the child code that follows the `<cms:block_parent />`.

## Parameters

* none

## Example
**Parent**
```html
<head>
    <cms:block 'head'>
        <link rel="stylesheet" href="style.css" />
        <title><cms:block 'title'></cms:block> - My Webpage</title>
    </cms:block>
</head>
```

**Child**
```html
<cms:block 'head' >
    <cms:block_parent />
    <style type="text/css">
        .important { color: #336699; }
    </style>
</cms:block>
```

**Output**
```html
<head>
    <link rel="stylesheet" href="style.css" />
    <title><cms:block 'title'></cms:block> - My Webpage</title>
    <style type="text/css">
        .important { color: #336699; }
    </style>
</head>
```

For more information visit [https://www.couchcms.com/forum/viewtopic.php?f=5&t=10984]

## Related Tags

* [block_parent](./block.html)
* [extends](./extends.html)