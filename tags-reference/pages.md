---
title: pages
parent: Tags Reference
layout: default
---

# pages

**Pages** tag can be used to list all pages belonging to a template.

```html
<cms:pages masterpage='blog.php'>
     <!-- All the variables of each page cloned out of this template are available here -->
     <cms:show k_page_title /><br>
</cms:pages>
```

\- the snippet given above will fetch all pages cloned out of _blog.php_ template.<br/>
The _masterpage_ parameter stands for the template's name. If this parameter is omitted, the name of the current template (i.e. the template this snippet is placed in) will be used.

This tag iterates through each of the fetched page and makes available all the data associated with the page as variables. The variables are exactly the same as those made available had the page been accessed discretly via its URL (i.e. in its [_page-view_](../concepts/variables-in-views.html)).

**Pages** tag supports a number of parameters that can be used to fine tune the actual pages that get fetched.

## Parameters

* masterpage
* id
* page_name
* limit
* paginate
* offset
* startcount
* folder
* include_subfolders
* start_on
* stop_before
* show_future_entries
* orderby
* order
* custom_field

### masterpage

```html
<cms:pages masterpage='blog.php'></cms:pages>
```

This example would fetch all pages cloned from blog.php.

If this parameter is skipped, the template being currently executed is used instead. Thus -

```html
<cms:pages></cms:pages>
```

This example would fetch all pages cloned from the template being currently executed.

### id

```html
<cms:pages masterpage='blog.php' id='14'></cms:pages>
```

This example would fetch only page with id of 14 that has been cloned from blog.php.

```html
<cms:pages masterpage='blog.php' id='14, 13'></cms:pages>
```

This example would fetch only pages with id of 14 or 13 that have been cloned from blog.php.

```html
<cms:pages masterpage='blog.php' id='NOT 14, 13'></cms:pages>
```

This example would fetch all pages cloned from blog.php except the two with the ids of 14 or 13\.

### page_name

```html
<cms:pages masterpage='blog.php' page_name='my_first_entry'></cms:pages>
```

This example would fetch the page named 'my_first_entry' that has been cloned from blog.php.

```html
<cms:pages masterpage='blog.php' page_name='my_first_entry, my_another_entry'></cms:pages>
```

This example would fetch pages named 'my_first_entry' or 'my_another_entry' that have been cloned from blog.php.

```html
<cms:pages masterpage='blog.php' page_name='NOT my_first_entry, my_another_entry'></cms:pages>
```

This example would fetch all pages cloned from blog.php except the two named 'my_first_entry' or 'my_another_entry'.

### limit

```html
<cms:pages masterpage='blog.php' limit='5'></cms:pages>
```

This example would fetch five pages cloned from blog.php. (Since no 'orderby' and 'order' parameters specified, the default values of these parameters will be used and the most recent five pages will be fetched.)

### paginate

```html
<cms:pages masterpage='blog.php' limit='5' paginate='1'></cms:pages>
```

This example would fetch ALL pages cloned from blog.php but show only 5 at one time. To move to the next 5 or the previous 5 pages, pagination code has to be used (see [**Pagination**](../concepts/pagination.html)).

### offset

```html
<cms:pages masterpage='blog.php' offset='2'></cms:pages>
```

This example would fetch pages cloned from blog.php after skipping the first two.

### startcount

```html
<cms:pages masterpage='blog.php' startcount='0'></cms:pages>
```

The *k_count*, *k_record_from*, *k_current_record* and *k_record_to* variables (see [**Pagination**](../concepts/pagination.html)) start by default from '1'. This can be changed to any other value by setting this parameter.

### folder

```html
<cms:pages masterpage='blog.php' folder='classic-bikes'></cms:pages>
```

This example would fetch pages cloned from blog.php and belonging to folder named 'classic-bikes'.

```html
<cms:pages masterpage='blog.php' folder='classic-bikes, super-bikes'></cms:pages>
```

This example would fetch pages cloned from blog.php and belonging to folders named 'classic-bikes' or 'super-bikes'.

```html
<cms:pages masterpage='blog.php' folder='NOT classic-bikes, super-bikes'></cms:pages>
```

This example would fetch all pages cloned from blog.php except those belonging to folders named 'classic-bikes' or 'super-bikes'.

By default Couch will only fetch pages that lie DIRECTLY within the given folder(s).<br/>
To include the pages that are within the subfolders of the given folder(s), set the *include_subfolders* parameter as well.<br/>
See below.

In the _folder-view_ (see [**Views**](../concepts/views.html)), the *k_folder_name* variable is set to the name of the current folder. It can be used to list the right pages -

```html
<cms:pages folder=k_folder_name include_subfolders='1'></cms:pages>
```

### include_subfolders

```html
<cms:pages masterpage='blog.php' folder='classic-bikes' include_subfolders='1'></cms:pages>
```

This example would fetch all pages cloned from blog.php that belong to 'classic-bikes' or any of its sub-folders.

This parameter augments the _folder_ parameter given above which only fetches pages that lie DIRECTLY within the given folder(s).

### start_on

```html
<cms:pages masterpage='blog.php' start_on='2010-02-01'></cms:pages>
```

This example would fetch all pages cloned from blog.php that have been published on or after the 1st of February, 2010\.

### stop_before

```html
<cms:pages masterpage='blog.php' stop_before='2010-03-01'></cms:pages>
```

This example would fetch all pages cloned from blog.php that have been published before the first of March, 2010\.

The parameters *start_on* and *stop_before* can be combined to fetch pages published betwen a particular time period. Thus -

```html
<cms:pages masterpage='blog.php' start_on='2010-02-01' stop_before='2010-03-01'></cms:pages>
```

This example would fetch all pages cloned from blog.php that have been published on or after the first of February, 2010 but before the first of March, 2010\. (i.e. only during the month of February of 2010)

In the _archive-view_ (see [**Views**](../concepts/views.html)), the *k_archive_date* and the *k_next_archive_date* are set to the first day of the archive and the first day of the next archive (month). These can be used to easily fetch pages that belong to only that archive period -

```html
<cms:pages start_on=k_archive_date stop_before=k_next_archive_date ></cms:pages>
```

### show_future_entries

```html
<cms:pages masterpage='blog.php' show_future_entries='0'></cms:pages>
```

This example would fetch only those pages cloned from blog.php that have been published on or before the current date (i.e. skip those pages the publication date of whom fall in the future).

### orderby

The pages fetched can be sorted and ordered according to the following fields -

* publish_date (_default_)
* page_name
* page_title
* modification_date
* comments_count
* random

Thus -

```html
<cms:pages masterpage='blog.php' orderby='page_name'></cms:pages>
```

Apart from the three fields mentioned above, any of the custom field defined in the template (i.e. the editable regions contained within the template) may be used for sorting the fetched pages. Thus, for example if the template 'blog.php' has three editable regions - *my_blog_text*, *my_blog_image* and *my_blog_author*, the following snippet -

```html
<cms:pages masterpage='blog.php' orderby='my_blog_author'></cms:pages>
```

will sort the fetched pages by the custom field named 'my_blog_author'.

<p class="notice">**IMP.** Though any type of editable region can be used as the orderby field, it is the 'text', 'textarea', 'dropdown' and 'radio' types that are best suited for ordering the pages.</p>

Multiple fields can be used together for sorting e.g.

```html
<cms:pages masterpage='blog.php' orderby='modification_date, page_name'></cms:pages>
```

### order

```html
<cms:pages masterpage='blog.php' orderby='publish_date' order='desc'></cms:pages>
```

This example would fetch all pages cloned from blog.php and arrange them in descending order of 'publish_date'.

If _order_ parameter is not set, the default value used is 'desc'. Since the default value used for _orderby_ is 'publish_date', the above snippet is equivalent to the following -

```html
<cms:pages masterpage='blog.php'></cms:pages>
```

If multiple fields have been used in the _orderby_ parameter, separate sort orders can be set for each of the _orderby_ field. Thus -

```html
<cms:pages orderby='my_custom_field_1, my_custom_field_2' order='asc, desc'></cms:pages>
```

The above will first sort pages in ascending order of 'my_custom_field_1'. The pages having the same value for 'my_custom_field_1' will then be sorted in descending order of 'my_custom_field_2'.

### custom_field

The editable regions defined for a template can be used to fetch cloned pages that contain certain values within those editable regions (custom fields) -

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author=jeffrey'></cms:pages>
```

This example would fetch all cloned pages of blog.php where the editable region 'my_blog_author' contained the word 'jeffrey' anywhere within it.

To fetch those pages where the editable region 'my_blog_author' exactly matches the term 'jeffrey', use '==' instead of '='. Thus -

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author==jeffrey'></cms:pages>
```

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author==jeffrey, arthur'></cms:pages>
```

This example would fetch all cloned pages of blog.php where the editable region 'my_blog_author' exactly matches either the term 'jeffrey' or 'arthur'.

<p class="notice">
    Since a comma ',' is being used to separate two values, if any of the values contains a comma<br/>
    within itself you'll have to 'escape' the comma by prepending it with a backward slash -<br/>
    'my_blog_text=veni, vidi, veci'  - contains any of the terms veni, vidi or veci<br/>
    'my_blog_text=veni\\, vidi\\, veci' - contains the phrase 'veni, vidi, veci'.<br/>
    <br/>
    Similarly if any of the values contains a single quote ''' or double quote '"', it can be escaped likewise.
</p>

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author!=jeffrey'></cms:pages>
```

This example would fetch all cloned pages of blog.php where the editable region 'my_blog_author' DOES NOT contain the word 'jeffrey' anywhere within it.

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author!==jeffrey'></cms:pages>
```

This example would fetch all cloned pages of blog.php where the editable region 'my_blog_author' DOES NOT exactly match the term 'jeffrey'.

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author!=jeffrey, arthur'></cms:pages>
```

This example would fetch all cloned pages of blog.php where the editable region 'my_blog_author' DOES NOT contain the words 'jeffrey' and 'arthur' anywhere within it.

<p class="error">
    The above snippet might seem a little counter-intuitive.<br/>
    It does not mean fetch all pages that contain neither jeffrey nor arthur. It means fetch only those pages that do not<br/>
    have both jeffrey and arthur in the same field.<br/>
    For how to fetch pages that contain neither jeffrey nor arthur, use the multiple fields examples given below.
</p>

Multiple custom fields may be combined together with a pipe '|' character (The pipe stands for a boolean AND) -<br/>
The same custom field may be repeated.

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author!=jeffrey | my_blog_author!=arthur'></cms:pages>
```

This example would fetch all pages that do not contain 'jeffrey' AND do not contain 'arthur' anywhere within 'my_blog_author' (i.e. have neither jeffrey nor arthur).

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author=jeffrey | my_blog_author=arthur'></cms:pages>
```

This example would fetch all pages that contain 'jeffery' AND contain 'arthur' somewhere within 'my_blog_author' (i.e. contain both jeffery as well as arthur).

```html
<cms:pages masterpage='blog.php' custom_field='my_blog_author=jeffrey | my_blog_text=fellow countrymen'></cms:pages>
```

This example would fetch all pages that contain 'jeffery' within 'my_blog_author' AND contain 'fellow countrymen' within 'my_blog_text'

Custom fields can also be used for comparisions other than the equality and non-equality described above.<br/>
For example, we can fetch pages that have the value of a certain editable region 'greater than' or 'less than' a particular value.

<p class="notice">
    Please bear in mind that if an editable region will contain values that you plan to compare in this manner<br/>
    (i.e. test whether the value is greater or less than some value), most probably the value will be a 'number' -<br/>
    age &lt; 35<br/>
    salary &gt; 12500<br/>
    distance &gt;= 23.56<br/>
    price = 355.39<br/>
    <br/>
    Telephone number, though it might contain all numeric values, is not a 'number' because you are unlikely to do something like -<br/>
    telephone_number &lt; 234567878<br/>
    <br/>
    For all such cases where the values will be numbers and you'd want to use them in the *custom_field* parameter, MAKE SURE to set the *search_type* parameter of the editable regions to either 'integer' (for values that will not be fractional e.g. number of bathrooms) or 'decimal' (for values that can be fractional e.g. price).<br/>
    <br/>
    Remember that only editable regions of types 'text', 'radio' and 'dropdown' can be made of 'integer'/'decimal' search_type.
</p>

As an example of numeric fields -

```html
<cms:pages custom_field='distance<50 | price>=1000000 | price<=3000000'></cms:pages>
```

This example would fetch all pages with custom field distance containing a value less than 50<br/>
AND custom field price 'greater than or equal to' 1000000<br/>
AND custom field price 'less than or equal to' 3000000 (i.e. price between 1000000 and 3000000)

The following comparisions can be done with numeric fields -

* = (equal to)
* != (not equal to)
* <= (less than or equal to)
* &gt;= (greater than or equal to)
* &lt;&gt; (not equal to)
* &lt; (less than)
* &gt; (greater than)

## Variables

As this tag iterates through all the fetched pages, at each iteration it sets all the variables that one normally finds set when that page is accessed in a _page-view_ (see [**Variables available in Views**](../concepts/variables-in-views.html)).<br/>
Apart from this, several variables are also set that indicate the current status of the loop.<br/>
These variables can be used to show the fetched pages in a paginated manner.<br/>
See [**Pagination**](../concepts/pagination.html).

## Related Tags

* [folders](./folders.html)
* [archives](./archives.html)
* [templates](./templates.html)
* [comments](./comments.html)
