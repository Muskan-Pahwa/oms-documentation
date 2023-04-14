# Check Inventory API

Get the stock details of the product on the specific locations. To get the stock details, you will need to call the `/checkInventory` endpoint with the GET method. 

## Request

### End Point
`https://<host>/api/checkInventory`

Example: https://demo-oms.hotwax.io/api/checkInventory

### Header
Content-Type: application/json


### Params
```
{
  "sku": "",
  "productId": " ",
  "facilityId": ""
}
```
Example Request: `https://demo-oms.hotwax.io/api/checkInventory?productId=10018&facilityId=Store_2&facilityId=Store_1`

| Parameter Name | Description | Required (Y/N) |
| --- | --- | --- |
| `sku` | The SKU of the product | N |
| `productId` | HotWax Commerce internal product Id | N |
| `facilityId` | The HotWax Commerce facility Id where product inventory is located | N |

Note: It is required to pass either `sku` or `productId`


## Response

### Status Code
HTTP/1.1 200 OK

### Headers
Content-Type: application/json


### Body
  
```
{
  "count": "2",
  "docs": [{
    "facilityId": "Store_1",
    "atp": 0.000000
  },
  {
    "facilityId": "Store_2",
    "atp": 4.000000
  }]
}
```

| Parameter Name | Description |
| --- | --- |
|  `count`| Results count |
| `docs` | The array of results found |
| `facilityId` | The Id of the facility in HotWax |
| `atp` | The available to promise inventory of the product |
