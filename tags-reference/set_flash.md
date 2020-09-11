---
title: set_flash
parent: Tags Reference
layout: default
---

# set_flash

The **set_flash** tag can be used to set a flash data variable with a name and value.

> 'Flash data' are i.e. session variables that exist for only a single server request, specifically the next one, and then are deleted.

**Important**
> Two scenarios can cause flash messages not to work as expected:
> 1. Multiple redirects (as happens when prettyURLs are on but a page is accessed using the 'older' URL. This causes Couch to redirect it to the newer (pretty) URL. The second redirection causes the flash message to be lost as it remains available for only one redirect)
> 2. The page being redirected to has been cached by Couch (in which case the cached page would be supplied).

## Parameters

* name
* value

### name

The name of the flash data variable.

### value

The value of the flash data variable. This value is stored on the clients computer.

## Variables

This tag is self-closing and does not set any variables of its own.

## Example

```html
<h3>Flash Message: <cms:get_flash 'flash_msg' /></h3>
<cms:form method="post" anchor='0'>
   <cms:if k_success >
       <cms:set_flash name='flash_msg' value="Your transaction is complete!" /> 
       <cms:redirect k_page_link />    
   </cms:if>
   <cms:input name="submit" type="submit" value="Submit" />
</cms:form>
```

## Related Tags

* [get_flash](./get_flash.html)
* [set_session](./set_session.html)
* [get_session](./get_session.html)
* [delete_session](./delete_session.html)
* [set_cookie](./set_cookie.html)
* [get_cookie](./get_cookie.html)
* [delete_cookie](./delete_cookie.html)