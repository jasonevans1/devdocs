---
group: rest-api
title: Manage low-quantity notifications
---

A merchant can configure 

**Service names**

```
inventoryLowQuantityNotificationApiGetSourceItemConfigurationSaveV1
inventoryLowQuantityNotificationApiGetSourceItemConfigurationV1
inventoryLowQuantityNotificationApiDeleteSourceItemConfigurationV1
```


**REST endpoints**

```
POST /V1/inventory/low-quantity-notification
GET /V1/inventory/low-quantity-notification/:sourceCode/:sku
DELETE /V1/inventory/low-quantity-notification
```

**sourceItemConfigurations parameters**


Name | Description | Type | Requirements
--- | --- | --- | ---
`source_code` | The product's assigned source code  | String | Required for POST and DELETE operations
`notify_stock_qty` | The threshold at which Magento notifies the merchant that the salable quantity of a product is low | Integer | Required for POST operations
`sku` | The product   | String | Required for POST and DELETE operations
{:style="table-layout:auto;"}

## Create a low quantity notification



**Sample usage**

`POST /V1/inventory/low-quantity-notification`

**Payload**

``` json
{
  "sourceItemConfigurations": [
    {
      "source_code": "reno_wh",
      "notify_stock_qty": 10,
      "sku": "sp2"
    }
  ]
}
```

**Response**

An empty array `[]`


## Return low-quantity notification information

This call returns detailed information about

**Sample usage**

`GET /V1/inventory/low-quantity-notification/reno_wh/sp2`

**Payload**

None

**Response**

``` json

Response body
{
"source_code": "reno_wh",
"notify_stock_qty": 10,
"sku": "sp2"
}
```

## Delete a low-quantity notification



**Sample usage**

`DELETE /V1/inventory/low-quantity-notification`

**Payload**



**Response**

Magento returns an empty array.

`[]`
