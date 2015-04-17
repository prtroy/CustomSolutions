#Add to Cart Preview for OrderCloud 

This module provides the user the ability to generate a list of multiple line items for one product without leaving the product's spec form. Once all combinations have been created, the user is then able to add the list to their cart.

##Setup
###1. Add module file to your project.
Add the **`addToCartPreview.js`** file to your project.

If you are using a repository, add this file to the **`/lib/oc`** directory.

If you are using file overrides, create a new file override named **`lib/oc/addToCartPreview.js`** and add this file as the content for that file.

**Be sure to reference both of this JS file in the `index.html` file**

###2. Load the module into the application.
Add a dependency for `OrderCloud-AddToCartPreview` to the Four51.app module in the **`js/app.js`** file.

##Usage
###1. Create a new Product Detail Template within the admin interface

Once created, navigate to the OrderCloud 2.0 tab. Replace this section: 

```html
    <button class="btn btn-success btn-block btn-lg" type="button" id="451_btn_orderadd" ng-click="addToOrder()">
        <loadingindicator ng-show="addToOrderIndicator" />
        <i ng-show="lineItemErrors.length > 0" class="fa fa-warning"></i>
        {{addToOrderText | r | xlat}}
        <span id="451qa_lineitem_total" class="badge" ng-if="!(user.Permissions.contains('HidePricing')) && (LineItem.LineTotal || variantLineItemsOrderTotal) > 0">
            {{(LineItem.LineTotal || variantLineItemsOrderTotal) | culturecurrency}}
        </span>
    </button>
```

with the following:

```html
    <addtocartpreview lineitem="LineItem" errors="lineItemErrors" user="user"></addtocartpreview>
```

###2. Apply Product Detail Template to product(s)

Your newly created Product Detail Template can be assigned to any products requiring the Add to Cart Preview.

###3. Variable Spec Image Variations (optional) 

If you wish for your Add to Cart Preview and Cart to show variable spec selection image variations (i.e. Color), in the product Variants section, "Generate Variants for the selection spec" and 
upload an image for each variable selection option. 


<sub><sup>Last Update: 4/17/15</sup></sub>