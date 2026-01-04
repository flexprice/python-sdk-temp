# Entitlements

## Overview

### Available Operations

* [get_addons_id_entitlements](#get_addons_id_entitlements) - Get addon entitlements
* [get_entitlements](#get_entitlements) - Get entitlements
* [post_entitlements](#post_entitlements) - Create a new entitlement
* [post_entitlements_bulk](#post_entitlements_bulk) - Create multiple entitlements in bulk
* [post_entitlements_search](#post_entitlements_search) - List entitlements by filter
* [get_entitlements_id_](#get_entitlements_id_) - Get an entitlement by ID
* [put_entitlements_id_](#put_entitlements_id_) - Update an entitlement
* [delete_entitlements_id_](#delete_entitlements_id_) - Delete an entitlement
* [get_plans_id_entitlements](#get_plans_id_entitlements) - Get plan entitlements

## get_addons_id_entitlements

Get all entitlements for an addon

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/addons/{id}/entitlements" method="get" path="/addons/{id}/entitlements" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.get_addons_id_entitlements(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Addon ID                                                            |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoListEntitlementsResponse](../../models/components/dtolistentitlementsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_entitlements

Get entitlements with the specified filter

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/entitlements" method="get" path="/entitlements" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.get_entitlements()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `request`                                                                              | [operations.GetEntitlementsRequest](../../models/operations/getentitlementsrequest.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `retries`                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                       | :heavy_minus_sign:                                                                     | Configuration to override the default retry behavior of the client.                    |

### Response

**[components.DtoListEntitlementsResponse](../../models/components/dtolistentitlementsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_entitlements

Create a new entitlement with the specified configuration

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/entitlements" method="post" path="/entitlements" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.post_entitlements(request={
        "feature_id": "<id>",
        "feature_type": components.TypesFeatureType.BOOLEAN,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `request`                                                                                        | [components.DtoCreateEntitlementRequest](../../models/components/dtocreateentitlementrequest.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |
| `retries`                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                 | :heavy_minus_sign:                                                                               | Configuration to override the default retry behavior of the client.                              |

### Response

**[components.DtoEntitlementResponse](../../models/components/dtoentitlementresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_entitlements_bulk

Create multiple entitlements with the specified configurations

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/entitlements/bulk" method="post" path="/entitlements/bulk" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.post_entitlements_bulk(request={
        "items": [],
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                | [components.DtoCreateBulkEntitlementRequest](../../models/components/dtocreatebulkentitlementrequest.md) | :heavy_check_mark:                                                                                       | The request object to use for the request.                                                               |
| `retries`                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                         | :heavy_minus_sign:                                                                                       | Configuration to override the default retry behavior of the client.                                      |

### Response

**[components.DtoCreateBulkEntitlementResponse](../../models/components/dtocreatebulkentitlementresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_entitlements_search

List entitlements by filter

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/entitlements/search" method="post" path="/entitlements/search" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.post_entitlements_search(request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `request`                                                                              | [components.TypesEntitlementFilter](../../models/components/typesentitlementfilter.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `retries`                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                       | :heavy_minus_sign:                                                                     | Configuration to override the default retry behavior of the client.                    |

### Response

**[components.DtoListEntitlementsResponse](../../models/components/dtolistentitlementsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_entitlements_id_

Get an entitlement by ID

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/entitlements/{id}" method="get" path="/entitlements/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.get_entitlements_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Entitlement ID                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoEntitlementResponse](../../models/components/dtoentitlementresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## put_entitlements_id_

Update an entitlement with the specified configuration

### Example Usage

<!-- UsageSnippet language="python" operationID="put_/entitlements/{id}" method="put" path="/entitlements/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.put_entitlements_id_(id="<id>", body={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `id`                                                                                             | *str*                                                                                            | :heavy_check_mark:                                                                               | Entitlement ID                                                                                   |
| `body`                                                                                           | [components.DtoUpdateEntitlementRequest](../../models/components/dtoupdateentitlementrequest.md) | :heavy_check_mark:                                                                               | Entitlement configuration                                                                        |
| `retries`                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                 | :heavy_minus_sign:                                                                               | Configuration to override the default retry behavior of the client.                              |

### Response

**[components.DtoEntitlementResponse](../../models/components/dtoentitlementresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## delete_entitlements_id_

Delete an entitlement

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_/entitlements/{id}" method="delete" path="/entitlements/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.delete_entitlements_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Entitlement ID                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoSuccessResponse](../../models/components/dtosuccessresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_plans_id_entitlements

Get all entitlements for a plan

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/plans/{id}/entitlements" method="get" path="/plans/{id}/entitlements" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.entitlements.get_plans_id_entitlements(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Plan ID                                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoPlanResponse](../../models/components/dtoplanresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |