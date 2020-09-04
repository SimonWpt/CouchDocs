---
title: cloak_url
parent: Tags Reference
layout: default
---

# cloak_url

The **cloak_url** tag, as the name suggests, can be used to cloak links so that it does not become apparent from just looking at the links as to where they actually lead to.

Please see [**Core Concepts - Cloaked Links**](../concepts/cloaked-links.html) for a detailed discussion of this tag.

## Parameters

* link
* expiry
* access_level
* prompt_login
* redirect
* force_download

### link

The link (URL) to cloak.

### expiry

This parameter can be used to set a time (in seconds) after which the link produced wll no longer be valid.

### access_level

If an access level is set by this parameter, only authenticated users with the right level of privileges will be able to access the link.

### prompt_login

This parameter works in tandem with the *access_level* parameter above. With this parameter set to '1', if a link that has an access level set on it is accessed by someone who is not privileged enough, a login box is shown to hime thus promting him to login for accessing the link.<br/>
By default, this parameter is '0' and unauthorized users are simply served a blank page.

### redirect

If this parameter is set to '1', the user is redirected to the _link_ provided (by issuing a HTTP 302 redirect).

### force_download

By default, this tag evaluates the type of the file being linked to and sends back proper Content-Type to the browser. This causes the browser to display certain files (e.g. image files like gif, png etc.) directly while displaying a messagebox prompting the user to download certain types of files (e.g. executables, zip files etc.).<br/>
If this parameter is set to '1', Couch will cause the browser to always display the download box regardless of the type of file being served.

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [cloak_email](./cloak_email.html)
