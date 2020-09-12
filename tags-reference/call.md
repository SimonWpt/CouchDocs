---
title: call
parent: Tags Reference
layout: default
---

# call
![self-closed](https://img.shields.io/badge/tag-self--closed-blue)

The **call** tag executes a function with optional parameters. It is a self-closed tag and if used as a tag-pair will not execute anything enclosed within.

Call invokes both named functions and anonymous functions (those stored in a variable).

## Parameters

The very first parameter is invariably expected to be the name of the called function or variable (for anonymous functions).<br />
As for the rest, call takes any number of named/unnamed parameters (either literal strings or variables).

**Note:** Unnamed parameters must appear in the same order, defined by **func** tag. Named parameters can appear in any order.

## Example

```html
<cms:func 'makecoffee' type='cappuccino' size='medium'>
    Making a <cms:show size /> cup of <cms:show type />.<br />
</cms:func>

<cms:call 'makecoffee' />
=> Making a medium cup of cappuccino.<br />

<cms:call 'makecoffee' 'espresso' 'large' />
=> Making a large cup of espresso.<br />

<cms:call 'makecoffee' size='small' type='espresso' />
=> Making a small cup of espresso.<br />
```

Anonymous functions are stored in a variable, hence we supply the variable itself without quotes i.e. passing by value, not by name.

```html
<cms:func _into='my_cond' previous_work_experience=''>
    <cms:if previous_work_experience='Yes'>show<cms:else />hide</cms:if>
</cms:func>

<cms:call my_cond previous_work_experience='Yes' />
=> show
```

## Variables

Call conveniently sets variables that become available *only* inside the function.

* k\_func &ndash; contains either name of the function or a word `anonymous`
* k\_args &ndash; associative array of passed arguments, e.g.
```json
[{"name":"size","val":"small"},{"name":"type","val":"espresso"}]
```

* k\_named_args &ndash; array of passed named arguments, e.g.
```json
{"type":"espresso","size":"small"}
```

Sets no variables of its own that can be used within its opening and closing tags.

## Related Tags

* [func](./func.html)


## Links

- An exemplar tutorial on using functions as well as examples in [official forum post.](https://www.couchcms.com/forum/viewtopic.php?f=8&t=11368&start=10#p30174)
- Invoking anonymous functions in Conditional Fields as explained in tutorial in [official forum post.](https://www.couchcms.com/forum/viewtopic.php?f=5&t=11512)
