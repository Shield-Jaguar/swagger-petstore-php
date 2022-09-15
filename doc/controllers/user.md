# User

Operations about user

Find out more about our store: [http://swagger.io](http://swagger.io)

```php
$userController = $client->getUserController();
```

## Class Name

`UserController`

## Methods

* [Create Users With Array Input](../../doc/controllers/user.md#create-users-with-array-input)
* [Create Users With List Input](../../doc/controllers/user.md#create-users-with-list-input)
* [Get User by Name](../../doc/controllers/user.md#get-user-by-name)
* [Update User](../../doc/controllers/user.md#update-user)
* [Delete User](../../doc/controllers/user.md#delete-user)
* [Login User](../../doc/controllers/user.md#login-user)
* [Logout User](../../doc/controllers/user.md#logout-user)
* [Create User](../../doc/controllers/user.md#create-user)


# Create Users With Array Input

Creates list of users with given input array

```php
function createUsersWithArrayInput(array $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[]`](../../doc/models/user.md) | Body, Required | List of user object |

## Response Type

`void`

## Example Usage

```php
$body = [];

$body[0] = new Models\User;

$body[1] = new Models\User;


$userController->createUsersWithArrayInput($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiException` |


# Create Users With List Input

Creates list of users with given input array

```php
function createUsersWithListInput(array $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[]`](../../doc/models/user.md) | Body, Required | List of user object |

## Response Type

`void`

## Example Usage

```php
$body = [];

$body[0] = new Models\User;

$body[1] = new Models\User;


$userController->createUsersWithListInput($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiException` |


# Get User by Name

Get user by user name

```php
function getUserByName(string $username): User
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | The name that needs to be fetched. Use user1 for testing. |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```php
$username = 'username0';

$result = $userController->getUserByName($username);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiException` |
| 404 | User not found | `ApiException` |


# Update User

This can only be done by the logged in user.

```php
function updateUser(string $username, User $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | name that need to be updated |
| `body` | [`User`](../../doc/models/user.md) | Body, Required | Updated user object |

## Response Type

`void`

## Example Usage

```php
$username = 'username0';
$body = new Models\User;

$userController->updateUser($username, $body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid user supplied | `ApiException` |
| 404 | User not found | `ApiException` |


# Delete User

This can only be done by the logged in user.

```php
function deleteUser(string $username): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | The name that needs to be deleted |

## Response Type

`void`

## Example Usage

```php
$username = 'username0';

$userController->deleteUser($username);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiException` |
| 404 | User not found | `ApiException` |


# Login User

Logs user into the system

```php
function loginUser(string $username, string $password): string
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Query, Required | The user name for login |
| `password` | `string` | Query, Required | The password for login in clear text |

## Response Type

`string`

## Example Usage

```php
$username = 'username0';
$password = 'password4';

$result = $userController->loginUser($username, $password);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username/password supplied | `ApiException` |


# Logout User

Logs out current logged in user session

```php
function logoutUser(): void
```

## Response Type

`void`

## Example Usage

```php
$userController->logoutUser();
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiException` |


# Create User

This can only be done by the logged in user.

```php
function createUser(User $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User`](../../doc/models/user.md) | Body, Required | Created user object |

## Response Type

`void`

## Example Usage

```php
$body = new Models\User;

$userController->createUser($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiException` |

