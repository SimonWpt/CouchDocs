---
title: block
parent: Tags Reference
layout: default
---

# block

The **block** tag is some kind of a placeholder. Any snippet 'extending' (or 'inheriting') the snippet containing **block** can choose to replace these placeholders (blocks) with its own content.

Please see [**Template inheritance**](https://www.couchcms.com/forum/viewtopic.php?f=5&t=10984) for an in-depth discussion about this tag and its relevant mates.

## Parameters

* unnamed

The first parameter is unnamed (i.e. only the value is passed) and the name of the block.

## Example

`parent.html`
```html
<!DOCTYPE html>
<html>
    <head>
        <cms:block 'head'>
            <link rel="stylesheet" href="style.css" />
            <title><cms:block 'title'></cms:block> - My Webpage</title>
        </cms:block>
    </head>
    <body>
        <div id="content"><cms:block 'content'></cms:block></div>
        <div id="footer">
            <cms:block 'footer'>
                &copy; Copyright 2011 by <a href="http://domain.invalid/">you</a>.
            </cms:block>
        </div>
    </body>
</html>
```

`child.html`
```html
<cms:extends 'parent.html' />

<cms:block 'title' >Index</cms:block>

<cms:block 'head' >
    <cms:block_parent />
    <style type="text/css">
        .important { color: #336699; }
    </style>
</cms:block>

<cms:block 'content' >
    <h1>Index</h1>
    <p class="important">
        Welcome on my awesome homepage.
    </p>
</cms:block>
```

`test.php`
```html
<?php require_once("couch/cms.php"); ?>
<cms:template>

</cms:template>

<cms:embed 'child.html' />

<?php COUCH::invoke(); ?>
```

Please notice, that this child snippet contains *only* `<cms:block>`s as first-level tags. This is important - all other tags at first-level will be totally ignored (in Symfony this actually throws an error). These blocks, in turn, can have any markup or Couch tags within them (even other `<cms:block>` tags nested within).



## Related Tags

* [block_parent](./block_parent.html)
* [extends](./extends.html)
