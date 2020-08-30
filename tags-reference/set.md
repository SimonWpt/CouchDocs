---
title: set
parent: Tags Reference
layout: default
---

# set

The **Set** tag is used to put some value in a variable. The variable, if not already present, is created.<br/>
(This tag is the counterpart of [**Show**](../show.html) tag which is used to display set variables)

The following example will create a variable called 'greeting' and set its value to 'Hello'

```html
<cms:set greeting='Hello' />
```

The following will create another variable known as 'message' and set its value to 'Hello'

```html
<cms:set message=greeting />
```

As with all other tags, nested tags may be used in parameters (taking care to use double quotes).<br/>
The following will set the value of 'message' to 'Hello World'.

```html
<cms:set message="<cms:show greeting /> World" />
```

> A valid variable name starts with a letter or underscore, followed by any number of letters, numbers, or underscores.
> **Set** cannot be used to set system variables (i.e. those that begin with prefix 'k\_').

## Parameters

The first parameter, as illustrated above, is mandatory and is used to set a named variable to a certain value. The tag also uses an optional unnamed (i.e. only the value can be provided).

* scope
* is_json

### scope

 The second parameter defines the **scope** within which the variable will be set.

```html
<cms:set message='hello' scope='global' />
```

The above is the same as

```html
<cms:set message='hello' 'global' />
```

Here 'global' defines the scope of 'message' variable

The valid values for this second parameter are -

* local
* parent
* global

### is_json

The content of the tag is in json format and the variable is converted into a multi-string array.

```html
<cms:set i18 = '
{
    "en" : {
        "app" : {
            "greet" : "Hello!"
        }
    },
    "es" : {
        "app" : {
            "greet" : "Hola!"
        }
    }
}
' is_json='1' />

<cms:set lang='es' />
<cms:get "i18.<cms:show lang />.app.greet" /><br>

<cms:set lang='en' />
<cms:get "i18.<cms:show lang />.app.greet" /><br>
```

Moving on and extending your example a bit:

```html
<cms:set climate.India='[]' is_json='1' />
<cms:set climate.India.Mumbai='pleasant' />
<cms:set climate.India.Delhi='moderate' />

<cms:set climate.Miami = 'great' />

Climate in Mumbai: <cms:show climate.India.Mumbai /><br>
Climate in Delhi: <cms:show climate.India.Delhi /><br>
Climate in Miami: <cms:show climate.Miami /><br>
```

## Variables

This tag does not set any variables of its own.

## Related Tags

* [show](./show.html)
* [get](./get.html)
* [get\_custom\_field](./get_custom_field.html)
* [pages](./pages.html)
