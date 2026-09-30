# Amplify Fusion - Supplier Order Collaboration API

An Amplify Fusion implementation of a Supplier Order Collaboration API defined by [this OpenAPI spec](Supplier_Order_Collaboration_OpenAPI_3_1.yaml).

Leverages the [Supplier Order Collaboration Mock backend](https://github.com/lbrenman/mock-purchase-order-backend).

An MCP Server for the backend systems is also included.

## Supported Features

* API Key authentication
  * Create a Fusion conusmer app per consumer (e.g. consumer id)
  * Create an entry in the `consumerIdLookup` cross reference table mapping the consumer app name (e.g. Apex-App) to the consumerId (e.g. apex-supplier-portal)
  
* GET /purchase-orders
  * `supplierId` query param, pagination and some error handling not yet implemented
* GET /purchase-orders/{purchaseOrderId}
   * `supplierId` query param, pagination and some error handling not yet implemented

* A web app for front end API calls

* An MCP Server to the back end (ERP, SRM, TMS) with the following tools
  * erp_find_purchase_orders
  * srm_list_consumers
  * srm_check_entitlement
  * tms_find_shipments

## Getting Started

* Import project file, `SupplierOrderCollaborationAPI.zip`, into Fusion
* Edit ERP, SRM and TMS Connections and point to the [Supplier Order Collaboration Mock backend](https://github.com/lbrenman/mock-purchase-order-backend) URL

* For front end API Calls
  * Create a Fusion consumer application with an api key for each consumer and enter into the `consumerIdLookup` cross reference table
  * Activate the `SupplierOrderCollaborationAPI` API and get it's URL
  * Activate the `webapp` Integration and get it's URL and past into a browser to launch the front end app
  * Click on Settings and enter the SupplierOrderCollaborationAPI` API URL and create consumer with API Keys and click Save. Optionally export.
    ![image](images/settings.png)
  * Cick on Purchase Orders and select a consumer from the picker in the upper right corner and click the Load Orders button and click on a Purchase Order. You have just called the GET /purchase-orders and GET /purchase-orders/{puchaseOrderId} methods
    ![image](images/pos.png)
  * Click on the Activity tab to review the activity details
    ![image](images/activity.png)
    ![image](images/activity-details.png)
    ![image](images/activity-error-details.png)

* For Backend MCP Server
  * Activate the `SupplierOrderCollaborationMCP` MCP Server and get it's URL
  * Call it from Postman or an LLM such as Claude Desktop
  * Sample prompts
    * "get all purchase orders"
      ![image](images/get-all-purchase-orders.png)
    * "list consumers"
      ![image](images/list-consumers.png)
    * "get purchase orders for apex-supplier-portal"
      ![image](images/get-purchase-orders-for.png)
    * "find shipments for apex-supplier-portal"
      ![image](images/find-shipments-for.png)