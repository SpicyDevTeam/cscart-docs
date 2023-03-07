*********
Shipments
*********

URLs
====

*   http://example.com/api/**shipments**—refer to all shipments. Only ``GET`` and ``POST`` are supported.
*   http://example.com/api/**shipments/:id**—refer to a particular shipment. ``GET``, ``PUT``, and ``DELETE`` are supported.

Pagination
==========

To get a specific number of shipments or list of shipments from a concrete page in a response, use pagination parameters:

.. list-table::
    :header-rows: 1
    :stub-columns: 1
    :widths: 20 30

    *   -   Pagination param
        -   Description
    *   -   page
        -   Shows shipments on a page with the defined number
    *   -   items_per_page
        -   Shows N shipments, where N - is a number defined in the parameter

**Examples:**

*   *http://example.com/api/shipments?page=5*

Response is an array with 10 shipments from the 5th page (10 is the default value of the ``items_per_page`` parameter).

*   *http://example.com/api/shipments?items_per_page=20*

Response is an array with 20 shipments from the first page.

*   *http://example.com/api/shipments?page=5&items_per_page=20*

Response is an array with 20 shipments from the 5th page.

Fields
======

A shipment has a number of properties, represented by fields.

The full list of supported fields is given below. Mandatory fields are marked with **\***. The **\**** mark means that only one of these fields is mandatory.

.. note:: Any field not listed in the table below will be ignored if occurs in an API request JSON data.

.. list-table::
    :header-rows: 1
    :stub-columns: 1
    :widths: 5 15 10 20

    *   -   Field name
        -   Description
        -   Default value
        -   Supported values
    *   -   carrier**
        -   Carrier name
        -   ''
        -   Valid carrier name
    *   -   order_id*
        -   Order ID
        -   —
        -   Valid order ID
    *   -   products*
        -   Shipped products
        -   —
        -   JSON object with cart item ID as key and its quantity as value
    *   -   shipping
        -   Shipping method name
        -   'Custom shipping method'
        -   Valid shipping method name
    *   -   shipping_id*
        -   Shipping method ID
        -   1
        -   Valid shipping method ID
    *   -   user_id
        -   Customer's user ID
        -   —
        -   Valid used ID
    *   -   tracking_number**
        -   Tracking number
        -   ''
        -   string
    *   -   comments
        -   ''
        -   Comments
        -   string
    *   -   group_key
        -   Supplier group key
        -   Set automatically
        -   Valid supplier group key
    *   -   order_timestamp
        -   Order creation timestamp
        -   Set automatically
        -   Valid timestamp in UNIX format
    *   -   status
        -   Shipments status
        -   P
        -   P - Picked up, A - Packed, S - Shipped
    *   -   order_status
        -   Order status (after shipment creation)
        -   Do not change
        -   P - Paid, C - Complete, O - Open, F - Failed, D - Declined, B - Backordered, I - Canceled, Y - Awaiting call