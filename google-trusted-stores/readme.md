#Setting up Google Trusted Stores in your Monster Commerce Store

If you aren't familiar with Google Trusted Stores, its simply a program that Google provides to help instill customer confidence in your business. Its' free and provides a substantial value proposition for any eCommerce business, large or small.

You can read about the program here: http://www.google.com/trustedstores/for-businesses/

Technical Details: https://support.google.com/trustedstoresmer...;hl=en&rd=1


##Introduction


If you have successfully signed up with Google for the Trusted Stores program, the next step involves setting up some code on your storefront to communicate with Google's service. Installation instructions have been provided below for your use/convenience.

You must sign up for the program before you can perform the installation. 

NOTE: The instructions provided are not official and were created by myself personally. Network Solutions/Web.com do not officially endorse the content of this thread and no warranties express or implied are granted for the content of this thread.

##Installation Instructions

*Important notes*

- *This will only work if you have your own dedicated SSL installed for your store. Contact support for details on purchasing a dedicated SSL if you don't have one.*
- *These instructions require performing basic HTML/Javscript modifications. Please insure you exercise care when making changes to your storefront, as your storefront's design is not warrantied against user changes.*


###Global Code (global.html)

This code appears on all pages and must be inserted into the very bottom of your Site Footer (Design-->Site Design-->Header/Footer).

*Notes*

*Adjust line 30 to include your store's ID.*

- *If you're using Google Shopping. please edit line 40 to include your Google Shopping ID. If you're NOT using google shopping, please remove this line. *
- *In order for the script to work correctly (re: passing the product ID in the right cirumstances) please add this line of HTML to the bottom of ALL product list designs you're using in the store (for Homepage specials, categories, search page, recommended/related products, etc). *


````
    <div class="product-id" style="display: none;"><%Product.Id%></div>
````
(source: product-list.html)


###Order Confirmation Page Code (order-confirmation.html)

This code must be inserted into the bottom of the Confirmation Message field (Operations-->Payments-->Edit Payment Method). For best results, please disable the WYSIWYG before inserting the code.

FYI: Once finalized, you'll need to copy this into the Confirmation Message for each active Payment Method within your store (both Credit Card/Alternate Payments). 

*Notes*

- *The cart cannot support identifying if an item is backordered, so this has to be set to No (N).*
- *This code sample _does NOT include support for digital products_. A special modification will be required to use this script and sell eProducts.*


###Setting the Estimated Shipping Date/Delivery Date

Again the cart really isn't setup to accommodate this, but you can manually specify a value to satisfy the requirement.

####Examples: 

If you usually will ship an item within 3 days of the order being placed, you can modfy the code at line 60 like so:

```
    var shippingDelay = 3;
```

*This the estimated number of days until the order ships*

Same goes for the Delivery date estimate (# of days for delivery). For this cart, you'll want to just figure out an average number to place here (i.e. if your shipping methods average a delivery time of 4 days, insert the value 4). See below example (referenced from line 73:

```
    var estDeliveryTime = 4;
```

**This the estimated number of days until the order is delivered once shipping, could be an average transit time



###Wrap Up

Make sure you've read through the global.html and order-confirmation.html files to make any necessary changes. As mentioned above/below, there are a few areas in which you'll need to edit the script to plug in your account information (among other things). 

Do you use Google Shopping? If so, you'll need to edit the code in the global.html and order-confirmation.html files to include your Google Shopping Account ID.

- global.html - Line: 40
- order-confirmation.html - Line: 173


Questions or problems? Submit an Issue via Github.