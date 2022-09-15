# Pet

Everything about your Pets

Find out more: [http://swagger.io](http://swagger.io)

```php
$petController = $client->getPetController();
```

## Class Name

`PetController`

## Methods

* [Upload File](../../doc/controllers/pet.md#upload-file)
* [Add Pet](../../doc/controllers/pet.md#add-pet)
* [Update Pet](../../doc/controllers/pet.md#update-pet)
* [Find Pets by Status](../../doc/controllers/pet.md#find-pets-by-status)
* [Find Pets by Tags](../../doc/controllers/pet.md#find-pets-by-tags)
* [Get Pet by Id](../../doc/controllers/pet.md#get-pet-by-id)
* [Update Pet With Form](../../doc/controllers/pet.md#update-pet-with-form)
* [Delete Pet](../../doc/controllers/pet.md#delete-pet)


# Upload File

uploads an image

```php
function uploadFile(int $petId, ?string $additionalMetadata = null, ?FileWrapper $file = null): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `int` | Template, Required | ID of pet to update |
| `additionalMetadata` | `?string` | Form, Optional | Additional data to pass to server |
| `file` | `?FileWrapper` | Form, Optional | file to upload |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

[`ApiResponse`](../../doc/models/api-response.md)

## Example Usage

```php
$petId = 152;

$result = $petController->uploadFile($petId);
```


# Add Pet

Add a new pet to the store

```php
function addPet(Pet $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Pet`](../../doc/models/pet.md) | Body, Required | Pet object that needs to be added to the store |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

`void`

## Example Usage

```php
$body_name = 'name6';
$body_photoUrls = ['photoUrls1'];
$body = new Models\Pet(
    $body_name,
    $body_photoUrls
);

$petController->addPet($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `ApiException` |


# Update Pet

Update an existing pet

```php
function updatePet(Pet $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Pet`](../../doc/models/pet.md) | Body, Required | Pet object that needs to be added to the store |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

`void`

## Example Usage

```php
$body_name = 'name6';
$body_photoUrls = ['photoUrls1'];
$body = new Models\Pet(
    $body_name,
    $body_photoUrls
);

$petController->updatePet($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiException` |
| 404 | Pet not found | `ApiException` |
| 405 | Validation exception | `ApiException` |


# Find Pets by Status

Multiple status values can be provided with comma separated strings

```php
function findPetsByStatus(array $status): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | [`string[] (Status2Enum)`](../../doc/models/status-2-enum.md) | Query, Required | Status values that need to be considered for filter |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

[`Pet[]`](../../doc/models/pet.md)

## Example Usage

```php
$status = [Models\Status2Enum::PENDING, Models\Status2Enum::SOLD, Models\Status2Enum::AVAILABLE];

$result = $petController->findPetsByStatus($status);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid status value | `ApiException` |


# Find Pets by Tags

**This endpoint is deprecated.**

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

```php
function findPetsByTags(array $tags): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tags` | `string[]` | Query, Required | Tags to filter by |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

[`Pet[]`](../../doc/models/pet.md)

## Example Usage

```php
$tags = ['tags5', 'tags6'];

$result = $petController->findPetsByTags($tags);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid tag value | `ApiException` |


# Get Pet by Id

Returns a single pet

```php
function getPetById(int $petId): Pet
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `int` | Template, Required | ID of pet to return |

## Response Type

[`Pet`](../../doc/models/pet.md)

## Example Usage

```php
$petId = 152;

$result = $petController->getPetById($petId);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiException` |
| 404 | Pet not found | `ApiException` |


# Update Pet With Form

Updates a pet in the store with form data

```php
function updatePetWithForm(int $petId, ?string $name = null, ?string $status = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `int` | Template, Required | ID of pet that needs to be updated |
| `name` | `?string` | Form, Optional | Updated name of the pet |
| `status` | `?string` | Form, Optional | Updated status of the pet |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

`void`

## Example Usage

```php
$petId = 152;

$petController->updatePetWithForm($petId);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `ApiException` |


# Delete Pet

Deletes a pet

```php
function deletePet(int $petId, ?string $apiKey = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `int` | Template, Required | Pet id to delete |
| `apiKey` | `?string` | Header, Optional | - |

## Requires scope

`WRITEPETS`, `READPETS`

## Response Type

`void`

## Example Usage

```php
$petId = 152;

$petController->deletePet($petId);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiException` |
| 404 | Pet not found | `ApiException` |

