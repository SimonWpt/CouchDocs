---
title: set_session
parent: Tags Reference
layout: default
---

# set_session

The **set_session** tag can be used to set a PHP session variable with a name and value.

> A PHP session variable is used to store information about, or change settings for a user session. Session variables hold information about one single user, and are available to all pages in one application.

## Parameters

* name
* value

### name

The name of the PHP session variable.

### value

The value of the PHP session variable. This value is stored on the clients computer.

## Variables

This tag is self-closing and does not set any variables of its own.

## Example

```html
<cms:set_session name='greeting' value='Hello world!' />
```

## Related Tags

* [set_flash](./set_flash.html)
* [get_flash](./get_flash.html)
* [get_session](./get_session.html)
* [delete_session](./delete_session.html)
* [set_cookie](./set_cookie.html)
* [get_cookie](./get_cookie.html)
* [delete_cookie](./delete_cookie.html)