---
title: concat
parent: Tags Reference
layout: default
---

# concat

The **concat** tag is a utility tag that can be used to concatenate several values together into a single string.

For example, suppose we have two variables 'first_name' and 'last_name'.

```html
<cms:set first_name = 'John' />
<cms:set last_name = 'Doe' />
```

To set a variable, 'welcome_message' to 'Hello John Doe! We welcome you!', using both the variables, we can do either this -

```html
<cms:set welcome_message="Hello <cms:show first_name/> <cms:show last_name/>! We welcome you!" />
```

or use **concat** as follows -

```html
<cms:set welcome_message="<cms:concat 'Hello ' first_name ' ' last_name '! We welcome you!' />" />
```

Here we supply **concat** with all parts of the string as unnamed parameters separated by spaces (i.e. 'Hello ', first_name, ' ', last_name, and '! We welcome you!' with space between each as separator) and **concat** simply returns back the concatenated string.

If many values are supplied to **concat**, the code sometimes becomes a little difficult to comprehend (as might be the case in the snippet above) because the only demarcation between the parameters is the space.

In such cases, we can try naming the parameters (any arbitrary names can be used). Thus the above snippet could be written as —
 ```html
<cms:set welcome_message="<cms:concat p1='Hello ' p2=first_name p3=' ' p4=last_name p5='! We welcome you!' />" />
 ```

Hopefully that should make the snippet more legible.


One benefit is that it avoids using '<cms:show />' with all variables used within the tag.<br>
Another is that we can use `\n` and `\t` for inserting newline and tab characters in the string. For example —

```html
<cms:set msg = "<cms:concat 'item_name: ' pp_item_name '\n'
    'item_number: ' pp_item_number '\n'
    'quantity: ' pp_quantity />" />
```
In the snippet above, 'msg' variable is being set in response to a successful PayPal transaction and will then be emailed.


If you aim to concat a large chunks of text, long variables, results of other tags - and place all of that into a variable,
it may be best to consider an alternative way of setting a variable – via tag 'cms:capture'.



## Parameters

Concat takes any number of unnamed parameters (either literal strings or variables) and returns back a single string containing the concatenated values.

Unnamed parameters can be given any names to aid visual separation e.g.
```html
<cms:concat p1='My ' p2='name is ' p3=k_user_title />

<cms:concat
   p1='My '
   p2='name is '
   p3=k_user_title
/>
```

## Variables

This tag does not set any variables of its own.

## Related Tags

* [capture](./capture.html)
