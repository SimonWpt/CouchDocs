---
title: comments
parent: Tags Reference
layout: default
---

# comments

Please see [**Core Concepts - Comments**](../concepts/using-comments.html) for a full discussion of the Comments tag.

## Parameters

* masterpage
* page_id
* page_name
* limit
* paginate
* offset
* order

Normally _comments_ tag will fetch all the available approved comments.<br/>
It can be constrained into fetching comments from only certain pages by setting the _masterpage_, *page_id* and *page_name* parameters.

### masterpage

```html
<cms:comments masterpage='blog.php'></cms:comments>
```

Fetch comments of only the pages that have been cloned out of blog.php.

```html
<cms:comments masterpage='blog.php, testimonial.php'></cms:comments>
```

Fetch comments of only the pages that have been cloned out of blog.php or testimonial.php.

```html
<cms:comments masterpage='NOT blog.php, testimonial.php'></cms:comments>
```

Fetch comments of all the pages except those that have been cloned out of blog.php or testimonial.php.

### page_id

```html
<cms:comments page_id='13'></cms:comments>
```

Fetch comments of only the page with the id of '13'.

```html
<cms:comments page_id='13, 17'></cms:comments>
```

Fetch comments of only the pages that have an id of '13' or '17'.

```html
<cms:comments page_id='NOT 13, 17'></cms:comments>
```

Fetch comments of all the pages except the pages that have an id of '13' or '17'.

### page_name

```html
<cms:comments page_name='my_first_entry'></cms:comments>
```

Fetch comments of only the page named 'my_first_entry'.

```html
<cms:comments page_name='my_first_entry, my_another_entry'></cms:comments>
```

Fetch comments of only the pages named 'my_first_entry' or 'my_another_entry'.

```html
<cms:comments page_name='NOT my_first_entry, my_another_entry'></cms:comments>
```

Fetch comments of all the pages except the pages named 'my_first_entry' or 'my_another_entry'.

### limit

```html
<cms:comments limit='5'></cms:comments>
```

Fetch five approved comments. (Since 'order' is not specified, the default value of 'desc' will be used and the latest 5 comments will be fetched.

### paginate

```html
<cms:comments limit='5' paginate='1'></cms:comments>
```

Fetch ALL approved comments but show only 5 at one time. To move to the next 5 or the previous 5 comments, pagination code has to be used (see [**paginator**](./paginator.html)).

### offset

```html
<cms:comments limit='5' offset='2'></cms:comments>
```

Fetch five approved comments after skipping the first two.

### order

Comments are always ordered by their dates. The order in which they are displayed can be made either ascending or descending by setting this parameter to 'asc' or 'desc' respectively. If omitted, 'desc' (latest first) is assumed.

```html
<cms:comments order='asc'></cms:comments>
```

Fetch all approved comments and order them in ascending order (oldest first) of their dates.

## Variables

* k_comment_id
* k_comment
* k_comment_author_id
* k_comment_author
* k_comment_author_email
* k_comment_author_website
* k_comment_date
* k_comment_link
* k_comment_page_id
* k_comment_page_title
* k_comment_page_name
* k_comment_template_name

In addition to these variables, the pagination related variables that describe the current status of the loop are also set. Please see [**paginator**](./paginator.html) for details.

## Related Tags

* [process_comment](./process_comment.html)
* [pages](./pages.html)
* [folders](./folders.html)
* [archives](./archives.html)
* [templates](./templates.html)
