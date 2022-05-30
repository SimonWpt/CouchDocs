---
title: addslashes
parent: Tags Reference
layout: default
---

# addslashes

The **addslashes** has become a necessary addition to escape characters. Very helpful in many situations where a mixture of single and double quotes creates problems. For instance, use it with **php** tag where a PHP variable is usually set by Couch statements.

## Parameters

* unnamed
* quote (optional)

## Example

```html
<cms:set test="O'Reilly" />
<cms:show test />
<cms:php>
    //$test = '<cms:show test />'; // this throws parse error because the value being set contains a single-quote (which is also used to surround the statement)
    $test = '<cms:addslashes quote='single'><cms:show test /></cms:addslashes>'; //default is 'double'
    echo '<h1>' . $test . '</h1>';
</cms:php>
```

## Related Tags

* [php](./php.html)
