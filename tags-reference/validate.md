---
title: validate
parent: Tags Reference
layout: default
---

# validate
There are situations where our code needs to deal directly with parameters provided by vistors through querystring (i.e. as URL's parameters). Security demands that such user-provided values must be treated with absolute suspicion and be thoroughly verified for their correctness before using them anywhere in the code.

Couch lends us a helping hand in this quest by sanitizing all GET parameters automatically. Further, the cms:gpc tag used to get the parameters also does the same. So the values are not likely to do any harm (e.g. result in XSS) but they still can be incorrect i.e. not what our code expects.

Validating the passed parameters required falling back on PHP so far.Now we can use the cms:validate tag for doing this.

## Parameters

* var
* validator

### var

Name of the variable to fetch the value of.

### validator

The 'validator' parameter accepts the same values as accepted by [<cms:editable />](./editable) e.g.

* min_len
* max_len
* exact_len
* alpha
* alpha_num
* integer
* non_negative_integer
* non_zero_integer
* decimal
* non_negative_decimal
* non_zero_decimal
* email
* matches_field
* regex

## Example

```html
<cms:set get_id="<cms:gpc method='get' var='id' />"/>

<cms:if "<cms:validate get_id validator='non_zero_integer' />">
    ...
</cms:if>
```

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [gpc](./gpc.html)
* 