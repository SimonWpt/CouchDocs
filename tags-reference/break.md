---
title: break
parent: Tags Reference
layout: default
---

# break

The **break** tag can be used to abort a loop set by 'cms:each':

```html
<cms:each myvar >
    ...
    <cms:if mycond>
        <cms:break />
    </cms:if>
</cms:each>
```

## Example
```html
<cms:each '1,2,3,4,5' startcount='1' sep=','>
    <p>Chapter <cms:show k_count/></p>
    <cms:if k_count = '3' ><cms:break /><p>End of story.</p></cms:if>
    <cms:if k_count = '3' >
        <p>New beginning? Hardly so.</p>
    </cms:if>
</cms:each>
```
In this elementary example only the first 3 iterations (starting with *1*) will allow the 'cms:show' to execute.

Code above produces following output &ndash;
```txt
Chapter 1
Chapter 2
Chapter 3
End of story.
```

**Note:** 'cms:break' effect kicks in **after** the HTML for the wrapping (parent) condition has been evaluated and output generated.<br>
The next condition will have an effect of break in fullest, hence the story ends right there, before the new beginning.

Presented with arrays, JSON, large texts, comma-separated strings or sets of numbers &ndash; again, those are very simple examples, &ndash; it won't be a problem to extract a few values.

## Parameters

None.

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [each](./each.html)
* [continue](./continue.html)
