---
title: paypal_button
parent: Tags Reference
layout: default
---

# paypal_button

Please see [**Core Concepts - PayPal**](../concepts/paypal.html) for a detailed discussion about this tag and its usage.

## Parameters

* image
* processor
* show_shipping

### image

This parameter is used to set the image used as the button.<br/>
You can either choose to use an image of your own or you may use one of the buttons made available by PayPal.

**Using your own image -**

```html
<cms:paypal_button image="<cms:show k_site_link />/images/my_button.gif" />
```

**Using PayPal provided images -**

To use these images, set the _image_ parameter to a number ranging from 0 to 8\.

```html
<cms:paypal_button image='3' />
```

The numbers represent the folllowing images -

![](../assets/img/contents/paypal_button.png)

### processor

The generated button provides PayPal with a link to the page that will process the IPN sent by it. By default this will be the link of the page the button is located on. If you have placed the **paypal_processor** tag, that handles the IPN, on some other page, set that pages link as this parameter.

### show_shipping

If the product being sold is not downloadable and requires a shipping address, set this parameter to '1'. This will make PayPal prompt the buyer for a shipping address.

## Variables

This tag is self-closing and does not set any variables of its own.

## Related Tags

* [paypal_processor](./paypal_processor.html)
