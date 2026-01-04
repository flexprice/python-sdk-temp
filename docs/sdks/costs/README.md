# Costs

## Overview

### Available Operations

* [post_costs](#post_costs) - Create a new costsheet
* [get_costs_active](#get_costs_active) - Get active costsheet for tenant
* [post_costs_analytics](#post_costs_analytics) - Get combined revenue and cost analytics
* [post_costs_analytics_v2](#post_costs_analytics_v2) - Get combined revenue and cost analytics
* [post_costs_search](#post_costs_search) - List costsheets by filter
* [get_costs_id_](#get_costs_id_) - Get a costsheet by ID
* [put_costs_id_](#put_costs_id_) - Update a costsheet
* [delete_costs_id_](#delete_costs_id_) - Delete a costsheet

## post_costs

Create a new costsheet with the specified name

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/costs" method="post" path="/costs" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.post_costs(request={
        "name": "<value>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                    | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `request`                                                                                    | [components.DtoCreateCostsheetRequest](../../models/components/dtocreatecostsheetrequest.md) | :heavy_check_mark:                                                                           | The request object to use for the request.                                                   |
| `retries`                                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                             | :heavy_minus_sign:                                                                           | Configuration to override the default retry behavior of the client.                          |

### Response

**[components.DtoCreateCostsheetResponse](../../models/components/dtocreatecostsheetresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 409                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_costs_active

Get the active costsheet for the current tenant

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/costs/active" method="get" path="/costs/active" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.get_costs_active()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoCostsheetResponse](../../models/components/dtocostsheetresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 404                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_costs_analytics

Retrieve combined analytics with ROI, margin, and detailed breakdowns. If start_time and end_time are not provided, defaults to last 7 days.

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/costs/analytics" method="post" path="/costs/analytics" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.post_costs_analytics(request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `request`                                                                                      | [components.DtoGetCostAnalyticsRequest](../../models/components/dtogetcostanalyticsrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `retries`                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                               | :heavy_minus_sign:                                                                             | Configuration to override the default retry behavior of the client.                            |

### Response

**[components.DtoGetDetailedCostAnalyticsResponse](../../models/components/dtogetdetailedcostanalyticsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_costs_analytics_v2

Retrieve combined analytics with ROI, margin, and detailed breakdowns. If start_time and end_time are not provided, defaults to last 7 days.

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/costs/analytics-v2" method="post" path="/costs/analytics-v2" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.post_costs_analytics_v2(request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `request`                                                                                      | [components.DtoGetCostAnalyticsRequest](../../models/components/dtogetcostanalyticsrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `retries`                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                               | :heavy_minus_sign:                                                                             | Configuration to override the default retry behavior of the client.                            |

### Response

**[components.DtoGetDetailedCostAnalyticsResponse](../../models/components/dtogetdetailedcostanalyticsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_costs_search

List costsheet records by filter with POST body

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/costs/search" method="post" path="/costs/search" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.post_costs_search(request=components.CostsheetFilter())

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `request`                                                                | [components.CostsheetFilter](../../models/components/costsheetfilter.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |
| `retries`                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)         | :heavy_minus_sign:                                                       | Configuration to override the default retry behavior of the client.      |

### Response

**[components.DtoListCostsheetResponse](../../models/components/dtolistcostsheetresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_costs_id_

Get a costsheet by ID with optional price expansion

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/costs/{id}" method="get" path="/costs/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.get_costs_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Costsheet ID                                                        |
| `expand`                                                            | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Comma-separated list of fields to expand (e.g., 'prices')           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoGetCostsheetResponse](../../models/components/dtogetcostsheetresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## put_costs_id_

Update a costsheet with the specified configuration

### Example Usage

<!-- UsageSnippet language="python" operationID="put_/costs/{id}" method="put" path="/costs/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.put_costs_id_(id="<id>", body={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                    | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `id`                                                                                         | *str*                                                                                        | :heavy_check_mark:                                                                           | Costsheet ID                                                                                 |
| `body`                                                                                       | [components.DtoUpdateCostsheetRequest](../../models/components/dtoupdatecostsheetrequest.md) | :heavy_check_mark:                                                                           | Costsheet configuration                                                                      |
| `retries`                                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                             | :heavy_minus_sign:                                                                           | Configuration to override the default retry behavior of the client.                          |

### Response

**[components.DtoUpdateCostsheetResponse](../../models/components/dtoupdatecostsheetresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404, 409              | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## delete_costs_id_

Soft delete a costsheet by setting its status to deleted

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_/costs/{id}" method="delete" path="/costs/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.costs.delete_costs_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Costsheet ID                                                        |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoDeleteCostsheetResponse](../../models/components/dtodeletecostsheetresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |