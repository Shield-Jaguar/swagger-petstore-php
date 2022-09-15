# Store

Access to Petstore orders

```php
$storeController = $client->getStoreController();
```

## Class Name

`StoreController`

## Methods

* [Place Order](../../doc/controllers/store.md#place-order)
* [Get Order by Id](../../doc/controllers/store.md#get-order-by-id)
* [Delete Order](../../doc/controllers/store.md#delete-order)
* [Get Inventory](../../doc/controllers/store.md#get-inventory)


# Place Order

Place an order for a pet

```php
function placeOrder(Order $body): Order
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Order`](../../doc/models/order.md) | Body, Required | order placed for purchasing the pet |

## Response Type

[`Order`](../../doc/models/order.md)

## Example Usage

```php
$body = new Models\Order;

$result = $storeController->placeOrder($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid Order | `ApiException` |


# Get Order by Id

For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions

```php
function getOrderById(int $orderId): Order
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `int` | Template, Required | ID of pet that needs to be fetched<br>**Constraints**: `>= 1`, `<= 10` |

## Response Type

[`Order`](../../doc/models/order.md)

## Example Usage

```php
$orderId = 62;

$result = $storeController->getOrderById($orderId);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiException` |
| 404 | Order not found | `ApiException` |


# Delete Order

For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors

```php
function deleteOrder(int $orderId): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `int` | Template, Required | ID of the order that needs to be deleted<br>**Constraints**: `>= 1` |

## Response Type

`void`

## Example Usage

```php
$orderId = 62;

$storeController->deleteOrder($orderId);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiException` |
| 404 | Order not found | `ApiException` |


# Get Inventory

Returns a map of status codes to quantities

```php
function getInventory(): array
```

## Response Type

`array<string,int>`

## Example Usage

```php
$result = $storeController->getInventory();
```

