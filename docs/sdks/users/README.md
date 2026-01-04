# Users

## Overview

### Available Operations

* [post_users](#post_users) - Create service account
* [get_users_me](#get_users_me) - Get user info
* [post_users_search](#post_users_search) - List users with filters

## post_users

Create a new service account with required roles. Only service accounts can be created via this endpoint.

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/users" method="post" path="/users" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.users.post_users(request={
        "roles": [],
        "type": components.TypesUserType.SERVICE_ACCOUNT,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `request`                                                                          | [components.DtoCreateUserRequest](../../models/components/dtocreateuserrequest.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |
| `retries`                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                   | :heavy_minus_sign:                                                                 | Configuration to override the default retry behavior of the client.                |

### Response

**[components.DtoUserResponse](../../models/components/dtouserresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_users_me

Get the current user's information

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/users/me" method="get" path="/users/me" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.users.get_users_me()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoUserResponse](../../models/components/dtouserresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_users_search

Search and filter users by type (user/service_account), roles, etc.

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/users/search" method="post" path="/users/search" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.users.post_users_search(request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `request`                                                                | [components.TypesUserFilter](../../models/components/typesuserfilter.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |
| `retries`                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)         | :heavy_minus_sign:                                                       | Configuration to override the default retry behavior of the client.      |

### Response

**[components.DtoListUsersResponse](../../models/components/dtolistusersresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |