---
title: cms:extends
parent: Tags Reference
layout: default
---

# extends
The `<cms:extends>`-Tag import an text file and gives you the ability in context with the `<cms:block>`-tag to extends it.

## Parameters

* unnamed

The first parameter is unnamed (i.e. only the value is passed) and the path of the text file.

## Example
`parent.html`
```html
<!DOCTYPE html>
<html>
    <head>
        <title><cms:block 'title'></cms:block> - My Webpage</title>
    </head>
    <body>
        <div id="content"><cms:block 'content'></cms:block></div>
    </body>
</html>
```
`child.html`
```html
<cms:extends 'parent.html' />

<cms:block 'title' >Index</cms:block>

<cms:block 'content' >
    <h1>Index</h1>
    <p class="important">
        Welcome on my awesome homepage.
    </p>
</cms:block>
```
> **Important** The <cms:extends> statement absolutely needs to be the very first line in the child statement or things will not work.
> 
> We we cannot actually make a 'template' inherit another 'template' (i.e. don't try putting the <cms:extends> statement directly within a 'template' and expect it to inherit another 'template'). We have to use 'snippets' for that. A 'template' can only call a 'snippet' using <cms:embed>.

For more information visit [https://www.couchcms.com/forum/viewtopic.php?f=5&t=10984]

## Related Tags

* [block](./block.html)
* [block_parent](./block_parent.html)