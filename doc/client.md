
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| `environment` | Environment | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| `timeout` | `int` | Timeout for API calls in seconds.<br>*Default*: `0` |
| `enableRetries` | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| `numberOfRetries` | `int` | The number of retries to make.<br>*Default*: `0` |
| `retryInterval` | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| `backOffFactor` | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| `maximumRetryWaitTime` | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| `retryOnTimeout` | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| `httpStatusCodesToRetry` | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| `httpMethodsToRetry` | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT'` |
| `oAuthClientId` | `string` | OAuth 2 Client ID |
| `oAuthRedirectUri` | `string` | OAuth 2 Redirection endpoint or Callback Uri |
| `oAuthToken` | `OAuthToken` | Object for storing information about the OAuth token |
| `oAuthScopes` | `string[] (OAuthScopeEnum)` |  |

The API client can be initialized as follows:

```php
$client = new SwaggerPetstoreLib\SwaggerPetstoreClient([
    // Set authentication parameters
    'oAuthClientId' => 'OAuthClientId',
    'oAuthRedirectUri' => 'OAuthRedirectUri',

    // Set OAuth 2.0 scopes
    'oAuthScopes' => [
        SwaggerPetstoreLib\Models\OAuthScopeEnum::READPETS,
        SwaggerPetstoreLib\Models\OAuthScopeEnum::WRITEPETS
    ],

    // Set the environment
    'environment' => 'production',
]);
```

## Swagger Petstore Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| getPetController() | Gets PetController |
| getStoreController() | Gets StoreController |
| getUserController() | Gets UserController |

