---
title: else_if
parent: Tags Reference
layout: default
---

# else_if

With the current logic tags (`cms:if` and `cms:else`)it isn't uncommon to find oneself in a rather 'heavily-nested' situation. A lot of screen space is lost in the text editor and, more importantly, it can also make reading code somewhat challenging. Let's use Couch's standard view handling as an example:

```html
<cms:if k_is_page >
    Page
<cms:else />
    <cms:if k_is_home >
        Home
    <cms:else />
        <cms:if k_is_folder >
            Folder
        <cms:else />
            Archive
        </cms:if>
    </cms:if>
</cms:if>
```

While embedding snippets certainly helps to alleviate some of the aforementioned problems, it isn't always an appropriate solution.

The addition of cms:else_if tag to the suite of logic tags now transforms the previous code example to:

```html
<cms:if k_is_page >
    Page
<cms:else_if k_is_home />
    Home
<cms:else_if k_is_folder />
    Folder
<cms:else />
    Archive
</cms:if>
```

## Parameters

Same as [if](./if.html).

## Variables

This tag does not set any variables of its own.

## Related Tags

* [if](./if.html)
* [else](./else.html)
