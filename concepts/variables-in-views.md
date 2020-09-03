---
title: Variables available in Views
parent: Core Concepts
layout: default
---

# Variables available in Views

From what we have read so far, we know that a template can be either _clonable_ or _non-clonable_.<br/>
A _clonable_ template will necessarily have cloned pages associated with it hence it is said to be executing within a _page-view_ when a cloned page of it is accessed while it is said to be executing within a _list-view_ if it is accessed in a stand alone manner.

A _non-clonable_ template always represents one single page and hence it has no such views associated with it.

Depending on whether a template is clonable or non-clonable and upon the view it is being executed in, each time a template is accessed, Couch makes available certain variables that are relevant to the template's state.

For example, when executed in a _page-view_, a template is used to access a cloned page and hence all that cloned page's data (including all its editable region's contents) are made available by Couch for use by your script.

In contrast, when executed in a _list-view_, it is not any single page that is accessed and hence no such page specific data is made available. Instead, certain variables that describe the 'list-view' and make it easy for your script to actually 'list' the pages pertaining to the view, are made available.

A complete list of all the variables that become available during the above mentioned conditions are listed below.

For the sake of this example we make use of a template named _blog.php_ that has three editable regions defined within it - *my_blog_text*, *my_blog_image* and *my_blog_author* (these will be made available as variables with the same names. They are shown highlighted below).

The following variables are available in ALL the cases, irrespective of the clonable status of the template and the current view -

* k_page_link
* k_admin_link
* k_site_link
* k_admin_path
* k_site_path
* k_template_title
* k_template_name
* k_template_id
* k_template_link
* k_prettyurls
* k_site_charset
* k_email_from
* k_email_to
* k_is_commentable

### NON-CLONABLE TEMPLATE -

If _blog.php_ is non-clonable, the only way it can be accessed is -<br/>
_<http://www.mysite.com/blog.php>_

\- and the available variables are -

* k_is_list_page
* k_comments_count
* k_page_date
* k_page_modification_date
* **my_blog_text**
* **my_blog_image**
* **my_blog_author**

### CLONABLE TEMPLATE -

If _blog.php_ is made clonable, the different views it can be accessed in and the variables made available in each view are -

#### PAGE VIEW

e.g. *<http://www.mysite.com/blog/some_page_name.html>*<br/>
In this view, variables giving information about the current page, the containing folder (if the page resides in one) and the contents of the page's editable regions are made available.

The folowing variables carry information about the page in question -

* k_is_page
* k_page_title
* k_page_name
* k_page_id
* k_page_date
* k_page_modification_date
* k_comments_count

The following variables carry Information about the folder, if the page resides in one -

* k_page_folderid
* k_page_foldername
* k_page_foldertitle
* k_page_folderlink
* k_page_folderpagecount
* k_page_foldertotalpagecount

Finally the contents of editable regions -

* **my_blog_text**
* **my_blog_image**
* **my_blog_author**

#### FOLDER VIEW

e.g. *<http://www.mysite.com/blog/some_subfolder/>*<br/>
In this view, variables giving information about the folder mentioned in the URL are set.

* k_is_list
* k_is_folder
* k_folder_id
* k_folder_name
* k_folder_title
* k_folder_link
* k_folder_pagecount (_Number of pages in the folder_)
* k_folder_totalpagecount (_Total number of pages, including pages in subfolders_)

#### ARCHIVE VIEW

e.g. _<http://www.mysite.com/blog/2010/05/>_<br/>
In this view, variables giving information about the archive's time period (as given in the URL) are set.

* k_is_list
* k_is_archive
* k_archive_date
* k_next_archive_date
* k_archive_link
* k_day
* k_month
* k_year

#### HOME VIEW

e.g. _<http://www.mysite.com/blog/>_

* k_is_list
* k_is_home
* k_folder_pagecount (_Number of pages. Remember home view is also the root folder_)
* k_folder_totalpagecount (_Total number of cloned pages, including pages in subfolders_)

> **IMP.** Notice that for cloneable templates, the contents of the editable regions associated with a page are made available only in page view.

> **TIP:** You can use the Couch tags - [__*dump*__](../tags-reference/dump.html) and [__*dump_all*__](../tags-reference/dump_all.html) to see for youself all the variables with their current values.

Next is [**Listing Pages**](./listing-pages.html)
