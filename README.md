# Amplify Fusion - Supplier Order Collaboration API

An Amplify Fusion implementation of a Supplier Order Collaboration API defined by [this OpenAPI spec](Supplier_Order_Collaboration_OpenAPI_3_1.yaml).

Leverages the [Supplier Order Collaboration Mock backend](https://github.com/lbrenman/mock-purchase-order-backend).

Currently supports:

* API Key authentication
  * Create a Fusion conusmer app per consumer (e.g. consumer id)
  * Create an entry in the `consumerIdLookup` cross reference table mapping the conusmer app to the consumerId
* GET /purchase-orders
    * `supplierId` query param abd pagination not yet supported