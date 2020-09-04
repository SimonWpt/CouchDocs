---
title: content_type
parent: Tags Reference
layout: default
---

# content_type

The **content_type** tag can be used to make the web server send back the contents with the desired Content-Type in the HTTP header.<br/>
By default every web page is send back as '_text/html_'.

As an example, the RSS feed requires it content type to be set as '_text/xml_' for the browsers to properly recognize the feed. The following snippet does the job -

```html
<cms:content_type 'text/xml' />
```

Please see [**Core Concepts - RSS Feeds**](../concepts/rss-feeds.html) for an example of the usage of this tag.

## Parameters

* value

### value

The desired content type. Some example values are '_text/xml_', '_text/plain_', '_text/css_', '_image/gif_', '_application/pdf_' and '_application/zip_'.

## Variables

This tag is self-closing and does not set any variables of its own.
