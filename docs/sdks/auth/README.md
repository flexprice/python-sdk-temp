# Auth

## Overview

### Available Operations

* [post_auth_login](#post_auth_login) - Login
* [post_auth_signup](#post_auth_signup) - Sign up

## post_auth_login

Login a user

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/auth/login" method="post" path="/auth/login" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.auth.post_auth_login(request={
        "email": "Vilma.Marquardt39@hotmail.com",
        "password": "1JTVnJWCnaHOL7f",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `request`                                                                | [components.DtoLoginRequest](../../models/components/dtologinrequest.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |
| `retries`                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)         | :heavy_minus_sign:                                                       | Configuration to override the default retry behavior of the client.      |

### Response

**[components.DtoAuthResponse](../../models/components/dtoauthresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_auth_signup

Sign up a new user

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/auth/signup" method="post" path="/auth/signup" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.auth.post_auth_signup(request={
        "email": "Dejon.Wintheiser73@yahoo.com",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                  | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `request`                                                                  | [components.DtoSignUpRequest](../../models/components/dtosignuprequest.md) | :heavy_check_mark:                                                         | The request object to use for the request.                                 |
| `retries`                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)           | :heavy_minus_sign:                                                         | Configuration to override the default retry behavior of the client.        |

### Response

**[components.DtoAuthResponse](../../models/components/dtoauthresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |