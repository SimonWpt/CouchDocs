---
title: delete_session
parent: Tags Reference
layout: default
---

# delete_session

The **delete_session** tag can be used to delete any PHP session variable created using the **set_session** tag.

## Parameters

This tag accepts no parameters.

## Variables

This tag is self-closing and does not set any variables of its own.

## Example

```html
<cms:delete_session 'greeting' />
```

## Related Tags

* [set_flash](./set_flash.html)
* [get_flash](./get_flash.html)
* [set_session](./set_session.html)
* [get_session](./get_session.html)
* [set_cookie](./set_cookie.html)
* [get_cookie](./get_cookie.html)
* [delete_cookie](./delete_cookie.html)
