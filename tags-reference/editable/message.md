---
title: type = 'message'
parent: Editable
grand_parent: Tags Reference
layout: default
---

# type = 'message'

Editable region of _message_ type is used to show arbitrary chunks of HTML to the user in the admin panel (in this sense, this tag is not editable at all). Any HTML enclosed within this tag will be output unchanged which makes it perfect for displaying messages in formatted HTML.

An example of this type -

```html
<cms:editable name='banner' type='message'>
<blockquote><p>The "free" distribution of unwelcome or misleading messages to thousands of people is an annoying and sometimes destructive use of the Internet's unprecedented efficiency.<br/>
<span style="color: rgb(51, 51, 51);">Bill Gates, New York Times, 1998</span></p></blockquote>
</cms:editable>
```

## Parameters

Please note that this tag ignores the _label_ and _desc_ parameters used with all other types.
