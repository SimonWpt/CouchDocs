---
title: get_cookie
parent: Tags Reference
layout: default
---

# get_cookie

The **get_cookie** tag can be used to fetch value contained within any cookie set by the **set_cookie** tag.

```html
<cms:get_cookie 'my_test_cookie' />
```

The snippet above will retrieve the value set within the cookie named 'my_test_cookie'

## Parameters

* name

### name

The name of the cookie the value of which is to be retrieved.

## Variables

This is a self closing tag and sets no variables of its own.

## Related Tags

* [set_cookie](./set_cookie.html)
* [delete_cookie](./delete_cookie.html)
* [set_flash](./set_flash.html)
* [get_flash](./get_flash.html)
* [set_session](./set_session.html)
* [get_session](./get_session.html)
* [delete_session](./delete_session.html)