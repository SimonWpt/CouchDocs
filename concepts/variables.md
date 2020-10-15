---
title: Variables
parent: Core Concepts
layout: default
---

# Variables

Don't get put off by that programming term. Variable is simply a place that can hold different values at different times.

You can use the Couch tag named [__*set*__](../tags-reference/set.html) to place values within variables. For example the following snippet -

```html
<cms:set my_message='Hello World' />
```

\- will place value 'Hello World' within a variable named *my_message* (i.e. set *my_message* to 'Hello World').  
This variable (*my_message*) can then be used elsewhere.

For example, in the following snippet -

```html
<cms:show 'Hello' />
```

\- we are passing 'Hello' as the parameter for [__*show*__](../tags-reference/show.html) to display. If instead we do the following -

```html
<cms:show my_message />
```

\- instead of explicitly passing 'Hello' as parameter, we are passing the value CONTAINED within *my_message* as the parameter. In this case 'Hello World' will get displayed.

Thus we see that variables act as simple containers for values.  
The value can be changed anytime, thus -

```html
<cms:set my_message='Salut!' />
<cms:show my_message />
```

\- [__*show*__](../tags-reference/show.html) will now display 'Salut!'.

In the examples above, we set the variable ourselves manually.  
However, the variables that we'll be dealing with more often are those that we'll find automatically set for us. e.g. -

1. At the execution of a page, Couch automatically sets certain variables that describe the current page and the context it is being executed in. These variables remain available throughout the page.  
      
    For example - the following snippet placed in any template will output the name of the template -  
      
    ```<cms:show k_template_name />```
    and the following will output the link (URL) of the page -  
      
    ```<cms:show k_page_link />```
    In the examples above, *k_template_name* and *k_page_link* are variables that have been set by Couch.  
      
    See: [Variables available in Views](./variables-in-views.html)    
2. A Paired tag usually sets certain variables that pertain to the task the tag does. These variables remain available only within the start-tag and the end-tag.  
      
    For example - we have already seen how the [__*repeat*__](../tags-reference/repeat.html) tag simply repeats the contents enclosed within it the number of times specified by the _count_ parameter. At each iteration, the [__*repeat*__](../tags-reference/repeat.html) tag sets a variable named *k_count* that is set to the count of the current iteration.  
      
    ```html
    <cms:repeat count='4'>
        <cms:show k_count /><br>
    </cms:repeat>
    ```
    The snippet above will output -  
    **0**  
    **1**  
    **2**  
    **3**  

Having now seen what variables are, we can move on to complete the previous topic - [**Setting a Tag's Parameters**](./setting-parameters.html).
