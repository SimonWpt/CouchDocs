---
title: set_cookie
parent: Tags Reference
layout: default
---

# set_cookie

The **set_cookie** tag can be used to set a cookie with a name and value. An expiration time can also be set for the cookie.

```html
<cms:set_cookie 'my_test_cookie' 'hello world' />
```

```html
<cms:set_cookie name='my_test_cookie' value='hello world' />
```

## Parameters

* name
* value
* expire

### name

The name of the cookie.

### value

The value of the cookie. This value is stored on the clients computer.

### expire

The time in seconds for the cookie to expire. If set to 0, or omitted, the cookie will expire at the end of the session (when the browser closes).

```html
<cms:set_cookie 'my_test_cookie' value='hello world' expire='86400' />
```

The code above will set the expiration time of the cookie to 1 day (24 \* 60 \* 60).

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [get_cookie](./get_cookie.html)
* [delete_cookie](./delete_cookie.html)
* [set_flash](./set_flash.html)
* [get_flash](./get_flash.html)
* [set_session](./set_session.html)
* [get_session](./get_session.html)
* [delete_session](./delete_session.html)
