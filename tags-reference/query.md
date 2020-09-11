---
title: query
parent: Tags Reference
layout: default
---

# query
The `<cms:query>`-Tag can be used to run raw SQL SELECT statements.
While it is a very powerful tag, it expects familiarty with how Couch stores its data in the database.

**Important**
> 1. Only SELECT statements can be used.
> 2. Don't use LIMIT / OFFSET in the raw SQL statement itself. Use the tag's parameters instead else the tag will throw error.
> 3. ORDER BY clause in raw SQL can mess up the count query (used internally for pagination) if it contains 'calculated fields'. For such cases the raw query can be stripped off this clause and the 'orderby' param of 'cms:query' tag used to provide the raw clause (this can include asc, desc etc.).

## Parameters

* unnamed
* parameters (optional)

## Example

As you know, the cms:pages tag's 'masterpage' parameter allows specifying only a single template which constrains us to use it for listing only pages belonging to a single template. Sometimes, it could be useful to show pages from multiple templates in a single list (e.g. for creating a Tumblr style site with a separate template for each 'post type').
The following snippet uses cms:query to execute a raw SQL query that fetches pages from two templates (of course, you're free to set any number of your own here)

```html
<cms:query
    sql="SELECT p.id pid, t.name tname
        FROM <cms:php>echo K_TBL_PAGES;</cms:php> p
        inner join <cms:php>echo K_TBL_TEMPLATES;</cms:php> t
        on p.template_id = t.id
        WHERE (t.name='actors.php' or t.name='movies.php')
        AND publish_date < '<cms:date format='Y-m-d H:i:s' />'
        AND NOT publish_date = '0000-00-00 00:00:00'
        ORDER BY publish_date desc;"
    limit='10'
    paginate='1'>

    <cms:show pid />-<cms:show tname /><br/>

    <cms:pages masterpage=tname id=pid>
       <a href="<cms:show k_page_link />"><cms:show k_page_title /></a><br />
    </cms:pages>

    <br />
    <cms:paginator />
</cms:query>
```

The following code cycle through a customer table and write the email to the file `query.log`.

```html
<cms:query sql="SELECT email FROM customer">
    <cms:php>
        file_put_contents(".query.log", "- Email: <cms:show email />".PHP_EOL , FILE_APPEND | LOCK_EX);
    </cms:php>
</cms:query>
```