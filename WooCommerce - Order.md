### Using some WC_Order and WC_Abstract_Order methods (example): ###

```php
// Get an instance of the WC_Order object (same as before)
$order = wc_get_order( $order_id );

// Get the order ID
$order_id = $order->get_id();

// Get the custumer ID
$order_id = $order->get_user_id();

// ... and so on ...
Get and access to the order data properties (in an array of values):

// Get an instance of the WC_Order object
$order = wc_get_order( $order_id );

$order_data = $order->get_data(); // The Order data

$order_id = $order_data['id'];
$order_parent_id = $order_data['parent_id'];
$order_status = $order_data['status'];
$order_currency = $order_data['currency'];
$order_version = $order_data['version'];
$order_payment_method = $order_data['payment_method'];
$order_payment_method_title = $order_data['payment_method_title'];
$order_payment_method = $order_data['payment_method'];
$order_payment_method = $order_data['payment_method'];
```

### Creation and modified WC_DateTime Object date string ###

```php
// Using a formated date ( with php date() function as method)
$order_date_created = $order_data['date_created']->date('Y-m-d H:i:s');
$order_date_modified = $order_data['date_modified']->date('Y-m-d H:i:s');

// Using a timestamp ( with php getTimestamp() function as method)
$order_timestamp_created = $order_data['date_created']->getTimestamp();
$order_timestamp_modified = $order_data['date_modified']->getTimestamp();


$order_discount_total = $order_data['discount_total'];
$order_discount_tax = $order_data['discount_tax'];
$order_shipping_total = $order_data['shipping_total'];
$order_shipping_tax = $order_data['shipping_tax'];
$order_total = $order_data['cart_tax'];
$order_total_tax = $order_data['total_tax'];
$order_customer_id = $order_data['customer_id']; // ... and so on

## BILLING INFORMATION:

$order_billing_first_name = $order_data['billing']['first_name'];
$order_billing_last_name = $order_data['billing']['last_name'];
$order_billing_company = $order_data['billing']['company'];
$order_billing_address_1 = $order_data['billing']['address_1'];
$order_billing_address_2 = $order_data['billing']['address_2'];
$order_billing_city = $order_data['billing']['city'];
$order_billing_state = $order_data['billing']['state'];
$order_billing_postcode = $order_data['billing']['postcode'];
$order_billing_country = $order_data['billing']['country'];
$order_billing_email = $order_data['billing']['email'];
$order_billing_phone = $order_data['billing']['phone'];

## SHIPPING INFORMATION:

$order_shipping_first_name = $order_data['shipping']['first_name'];
$order_shipping_last_name = $order_data['shipping']['last_name'];
$order_shipping_company = $order_data['shipping']['company'];
$order_shipping_address_1 = $order_data['shipping']['address_1'];
$order_shipping_address_2 = $order_data['shipping']['address_2'];
$order_shipping_city = $order_data['shipping']['city'];
$order_shipping_state = $order_data['shipping']['state'];
$order_shipping_postcode = $order_data['shipping']['postcode'];
$order_shipping_country = $order_data['shipping']['country'];
Get the order items and access the data with WC_Order_Item_Product and WC_Order_Item methods:

// Get an instance of the WC_Order object
$order = wc_get_order($order_id);

// Iterating through each WC_Order_Item_Product objects
foreach ($order->get_items() as $item_key => $item_values):

    ## Using WC_Order_Item methods ##

    // Item ID is directly accessible from the $item_key in the foreach loop or
    $item_id = $item_values->get_id();

    ## Using WC_Order_Item_Product methods ##

    $item_name = $item_values->get_name(); // Name of the product
    $item_type = $item_values->get_type(); // Type of the order item ("line_item")

    $product_id = $item_values->get_product_id(); // the Product id
    $wc_product = $item_values->get_product(); // the WC_Product object
    ## Access Order Items data properties (in an array of values) ##
    $item_data = $item_values->get_data();

    $product_name = $item_data['name'];
    $product_id = $item_data['product_id'];
    $variation_id = $item_data['variation_id'];
    $quantity = $item_data['quantity'];
    $tax_class = $item_data['tax_class'];
    $line_subtotal = $item_data['subtotal'];
    $line_subtotal_tax = $item_data['subtotal_tax'];
    $line_total = $item_data['total'];
    $line_total_tax = $item_data['total_tax'];

endforeach;
```