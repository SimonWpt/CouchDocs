---
title: Tweaking the navigation
parent: Tutorials
layout: default
---

# Tweaking the backend navigation

Sometimes a website grows and the backend navigation looks utterly confusing. Lets say, you have a yoga studio. 
 
* Yoga Institute
* About us
* Teacher
* Rental
* Services
* Program
* Courses
* Workshops and Seminars
* Education
* Massages
* Personal yoga
* Business yoga
* Prices
* Booking
* Contact
* Registration
* Directions
* Imprint
* Data protection

The flat structure is no good readable in the backend. It would be nice to nest the navigation items like this:
 
 * Yoga Institute
   * About us
   * Teacher
   * Rental
 * Services
   * Program
   * Courses
   * Workshops and Seminars
   * Education
   * Massages
   * Personal yoga
   * Business yoga
   * Prices
   * Booking
 * Contact
   * Registration
   * Directions
   * Imprint
   * Data protection
 
 Fortunately, with just a few lines of code, you can create this order in CouchCMS. You have to edit the `couch/addons/kfunctions.php`:

```php
if( defined('K_ADMIN') ){
    $FUNCS->add_event_listener( 'register_admin_menuitems', 'my_register_admin_menuitems' );

    function my_register_admin_menuitems(){
        global $FUNCS;

        $FUNCS->register_admin_menuitem( array('name'=>'yoga-institute', 'title'=>'Yoga Institute', 'is_header'=>'1', 'weight'=>'0')  );
        $FUNCS->register_admin_menuitem( array('name'=>'services', 'title'=>'Services', 'is_header'=>'1', 'weight'=>'0')  );
        $FUNCS->register_admin_menuitem( array('name'=>'contact', 'title'=>'Contact', 'is_header'=>'1', 'weight'=>'0')  );

    }
}
```

Then you have to edit your template like this:

```html
<cms:template title='About us' parent='yoga-institute' icon='people' />
```

or

```html
<cms:template title='Directions' parent='contact' icon='location' />
```

If you edit all templates this way, you got a well-structured, collapsable backend navigation. Don't forget to use some memorable icons, you find an overview on [Open Iconic](https://useiconic.com/open#icons).