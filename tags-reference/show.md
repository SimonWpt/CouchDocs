---
title: show
parent: Tags Reference
layout: default
---

# show

The **Show** tag is used to display something on the page.<br/>
It could be a literal string e.g.

```html
<cms:show 'Hello World' />
```

or a variable (both system variables as well as all the editable regions on the page) e.g.

```html
<cms:show k_page_title />
<cms:show my_intro />
```

## Parameters

* var
* scope
* as_json

### var

Parameter **var** is usually the first provided parameter.

### scope

Valid scopes:
* global  (or *2*)
* local (or *1*)

If scope is set and first param is a variable, returns variable only from the specified scope —
```html
<cms:show var=k_page_title scope='local' />
```

### as_json

If the **var** is an array, prints it encoded in JSON —
```
<cms:show cars as_json='1' />
```

## Usage

Handling arrays deserves a few examples. Let's set up a couple of them with simple JSON —

```html
<cms:set cars='[ "Ford", "BMW", "Fiat" ]' is_json='1' />
<cms:set rec='{"name":"John", "age":30, "cars":[ "Ford", "BMW", "Fiat" ]}' is_json='1' />
```

Now, simple print as JSON would be done with parameter **as_json** &mdash;
```html
 <cms:show cars as_json='1' />
 <cms:show rec as_json='1' />
```

Performs access to values of array via index with dot (.) as separator &mdash;
```html
<cms:show cars.0 />
=> Ford
```

Same works for associative arrays &mdash;
```html
<cms:show rec.name />
=> John

<cms:show rec.cars.1 />
=> Ford

<cms:show rec.cars as_json='1' />
=> ["Ford","BMW","Fiat"]

<cms:show rec.cars />
=> Array
```

In the last example, tag will print the word *Array* to indicate that value is of type 'array' and parameter **as_json** is needed to see its content.
## Variables

This tag does not set any variables of its own.

## Related Tags

* [get](./get.html)
* [set](./set.html)
* [get_custom_field](./get_custom_field.html)
* [pages](./pages.html)
