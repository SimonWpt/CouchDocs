---
title: get_session
parent: Tags Reference
layout: default
---

# get_session

The **get_session** tag can be used to fetch value contained within any PHP session variable set by the **set_session** tag.

## Parameters

* name

### name

The name of the PHP session variable the value of which is to be retrieved.

## Variables

This is a self closing tag and sets no variables of its own.

## Example

```html
<cms:get_session 'greeting' />
```

## Related Tags

* [set_flash](./set_flash.html)
* [get_flash](./get_flash.html)
* [set_session](./set_session.html)
* [delete_session](./delete_session.html)
* [set_cookie](./set_cookie.html)
* [get_cookie](./get_cookie.html)
* [delete_cookie](./delete_cookie.html)
