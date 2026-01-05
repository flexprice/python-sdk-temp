# CustomerDashboard

## Overview

### Available Operations

* [get_customer_dashboard_external_id](#get_customer_dashboard_external_id) - Create a customer dashboard session
* [post_customer_dashboard_analytics](#post_customer_dashboard_analytics) - Get customer analytics
* [post_customer_dashboard_cost_analytics](#post_customer_dashboard_cost_analytics) - Get customer cost analytics
* [get_customer_dashboard_info](#get_customer_dashboard_info) - Get customer information
* [put_customer_dashboard_info](#put_customer_dashboard_info) - Update customer information
* [post_customer_dashboard_invoices](#post_customer_dashboard_invoices) - Get customer invoices
* [get_customer_dashboard_invoices_id_](#get_customer_dashboard_invoices_id_) - Get invoice by ID
* [post_customer_dashboard_subscriptions](#post_customer_dashboard_subscriptions) - Get customer subscriptions
* [get_customer_dashboard_subscriptions_id_](#get_customer_dashboard_subscriptions_id_) - Get subscription by ID
* [get_customer_dashboard_usage](#get_customer_dashboard_usage) - Get customer usage summary
* [post_customer_dashboard_wallets](#post_customer_dashboard_wallets) - Get customer wallets
* [get_customer_dashboard_wallets_id_](#get_customer_dashboard_wallets_id_) - Get wallet by ID

## get_customer_dashboard_external_id

Generate a dashboard URL/token for a customer to access their billing information

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/customer-dashboard/:external_id" method="get" path="/customer-dashboard/:external_id" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.customer_dashboard.get_customer_dashboard_external_id()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoDashboardSessionResponse](../../models/components/dtodashboardsessionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_customer_dashboard_analytics

Get usage analytics for the authenticated customer

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/customer-dashboard/analytics" method="post" path="/customer-dashboard/analytics" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.post_customer_dashboard_analytics(security=operations.PostCustomerDashboardAnalyticsSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), request={
        "end_time": "2024-01-31T23:59:59Z",
        "expand": [
            "price",
            "meter",
            "feature",
        ],
        "feature_ids": [
            "feat_123",
            "feat_456",
        ],
        "group_by": [
            "source",
            "feature_id",
        ],
        "sources": [
            "api",
            "web",
        ],
        "start_time": "2024-01-01T00:00:00Z",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                              | [components.DtoDashboardAnalyticsRequest](../../models/components/dtodashboardanalyticsrequest.md)                     | :heavy_check_mark:                                                                                                     | The request object to use for the request.                                                                             |
| `security`                                                                                                             | [operations.PostCustomerDashboardAnalyticsSecurity](../../models/operations/postcustomerdashboardanalyticssecurity.md) | :heavy_check_mark:                                                                                                     | The security requirements to use for the request.                                                                      |
| `retries`                                                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                       | :heavy_minus_sign:                                                                                                     | Configuration to override the default retry behavior of the client.                                                    |

### Response

**[components.DtoGetUsageAnalyticsResponse](../../models/components/dtogetusageanalyticsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_customer_dashboard_cost_analytics

Get cost analytics for the authenticated customer

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/customer-dashboard/cost-analytics" method="post" path="/customer-dashboard/cost-analytics" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.post_customer_dashboard_cost_analytics(security=operations.PostCustomerDashboardCostAnalyticsSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), request={
        "end_time": "2024-01-31T23:59:59Z",
        "feature_ids": [
            "feat_123",
            "feat_456",
        ],
        "start_time": "2024-01-01T00:00:00Z",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                      | Type                                                                                                                           | Required                                                                                                                       | Description                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                      | [components.DtoDashboardCostAnalyticsRequest](../../models/components/dtodashboardcostanalyticsrequest.md)                     | :heavy_check_mark:                                                                                                             | The request object to use for the request.                                                                                     |
| `security`                                                                                                                     | [operations.PostCustomerDashboardCostAnalyticsSecurity](../../models/operations/postcustomerdashboardcostanalyticssecurity.md) | :heavy_check_mark:                                                                                                             | The security requirements to use for the request.                                                                              |
| `retries`                                                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                               | :heavy_minus_sign:                                                                                                             | Configuration to override the default retry behavior of the client.                                                            |

### Response

**[components.DtoGetDetailedCostAnalyticsResponse](../../models/components/dtogetdetailedcostanalyticsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_customer_dashboard_info

Get the authenticated customer's information

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/customer-dashboard/info" method="get" path="/customer-dashboard/info" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.get_customer_dashboard_info(security=operations.GetCustomerDashboardInfoSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                 | [operations.GetCustomerDashboardInfoSecurity](../../models/operations/getcustomerdashboardinfosecurity.md) | :heavy_check_mark:                                                                                         | The security requirements to use for the request.                                                          |
| `retries`                                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                           | :heavy_minus_sign:                                                                                         | Configuration to override the default retry behavior of the client.                                        |

### Response

**[components.DtoCustomerResponse](../../models/components/dtocustomerresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## put_customer_dashboard_info

Update the authenticated customer's profile information

### Example Usage

<!-- UsageSnippet language="python" operationID="put_/customer-dashboard/info" method="put" path="/customer-dashboard/info" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.put_customer_dashboard_info(security=operations.PutCustomerDashboardInfoSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                  | [components.DtoUpdateCustomerRequest](../../models/components/dtoupdatecustomerrequest.md)                 | :heavy_check_mark:                                                                                         | The request object to use for the request.                                                                 |
| `security`                                                                                                 | [operations.PutCustomerDashboardInfoSecurity](../../models/operations/putcustomerdashboardinfosecurity.md) | :heavy_check_mark:                                                                                         | The security requirements to use for the request.                                                          |
| `retries`                                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                           | :heavy_minus_sign:                                                                                         | Configuration to override the default retry behavior of the client.                                        |

### Response

**[components.DtoCustomerResponse](../../models/components/dtocustomerresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 401                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_customer_dashboard_invoices

Get all invoices for the authenticated customer with pagination

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/customer-dashboard/invoices" method="post" path="/customer-dashboard/invoices" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.post_customer_dashboard_invoices(security=operations.PostCustomerDashboardInvoicesSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), request={
        "limit": 20,
        "page": 1,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                            | [components.DtoDashboardPaginatedRequest](../../models/components/dtodashboardpaginatedrequest.md)                   | :heavy_check_mark:                                                                                                   | The request object to use for the request.                                                                           |
| `security`                                                                                                           | [operations.PostCustomerDashboardInvoicesSecurity](../../models/operations/postcustomerdashboardinvoicessecurity.md) | :heavy_check_mark:                                                                                                   | The security requirements to use for the request.                                                                    |
| `retries`                                                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                     | :heavy_minus_sign:                                                                                                   | Configuration to override the default retry behavior of the client.                                                  |

### Response

**[components.DtoListInvoicesResponse](../../models/components/dtolistinvoicesresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_customer_dashboard_invoices_id_

Get a specific invoice for the authenticated customer

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/customer-dashboard/invoices/{id}" method="get" path="/customer-dashboard/invoices/{id}" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.get_customer_dashboard_invoices_id_(security=operations.GetCustomerDashboardInvoicesIDSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                             | [operations.GetCustomerDashboardInvoicesIDSecurity](../../models/operations/getcustomerdashboardinvoicesidsecurity.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `id`                                                                                                                   | *str*                                                                                                                  | :heavy_check_mark:                                                                                                     | Invoice ID                                                                                                             |
| `retries`                                                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                       | :heavy_minus_sign:                                                                                                     | Configuration to override the default retry behavior of the client.                                                    |

### Response

**[components.DtoInvoiceResponse](../../models/components/dtoinvoiceresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_customer_dashboard_subscriptions

Get all subscriptions for the authenticated customer with pagination

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/customer-dashboard/subscriptions" method="post" path="/customer-dashboard/subscriptions" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.post_customer_dashboard_subscriptions(security=operations.PostCustomerDashboardSubscriptionsSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), request={
        "limit": 20,
        "page": 1,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                      | Type                                                                                                                           | Required                                                                                                                       | Description                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                      | [components.DtoDashboardPaginatedRequest](../../models/components/dtodashboardpaginatedrequest.md)                             | :heavy_check_mark:                                                                                                             | The request object to use for the request.                                                                                     |
| `security`                                                                                                                     | [operations.PostCustomerDashboardSubscriptionsSecurity](../../models/operations/postcustomerdashboardsubscriptionssecurity.md) | :heavy_check_mark:                                                                                                             | The security requirements to use for the request.                                                                              |
| `retries`                                                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                               | :heavy_minus_sign:                                                                                                             | Configuration to override the default retry behavior of the client.                                                            |

### Response

**[components.DtoListSubscriptionsResponse](../../models/components/dtolistsubscriptionsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_customer_dashboard_subscriptions_id_

Get a specific subscription for the authenticated customer

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/customer-dashboard/subscriptions/{id}" method="get" path="/customer-dashboard/subscriptions/{id}" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.get_customer_dashboard_subscriptions_id_(security=operations.GetCustomerDashboardSubscriptionsIDSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                        | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                       | [operations.GetCustomerDashboardSubscriptionsIDSecurity](../../models/operations/getcustomerdashboardsubscriptionsidsecurity.md) | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |
| `id`                                                                                                                             | *str*                                                                                                                            | :heavy_check_mark:                                                                                                               | Subscription ID                                                                                                                  |
| `retries`                                                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                 | :heavy_minus_sign:                                                                                                               | Configuration to override the default retry behavior of the client.                                                              |

### Response

**[components.DtoSubscriptionResponse](../../models/components/dtosubscriptionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_customer_dashboard_usage

Get usage summary for the authenticated customer's metered features

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/customer-dashboard/usage" method="get" path="/customer-dashboard/usage" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.get_customer_dashboard_usage(security=operations.GetCustomerDashboardUsageSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                    | [operations.GetCustomerDashboardUsageRequest](../../models/operations/getcustomerdashboardusagerequest.md)   | :heavy_check_mark:                                                                                           | The request object to use for the request.                                                                   |
| `security`                                                                                                   | [operations.GetCustomerDashboardUsageSecurity](../../models/operations/getcustomerdashboardusagesecurity.md) | :heavy_check_mark:                                                                                           | The security requirements to use for the request.                                                            |
| `retries`                                                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                             | :heavy_minus_sign:                                                                                           | Configuration to override the default retry behavior of the client.                                          |

### Response

**[components.DtoCustomerUsageSummaryResponse](../../models/components/dtocustomerusagesummaryresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_customer_dashboard_wallets

Get all wallet balances for the authenticated customer

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/customer-dashboard/wallets" method="post" path="/customer-dashboard/wallets" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.post_customer_dashboard_wallets(security=operations.PostCustomerDashboardWalletsSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                          | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `security`                                                                                                         | [operations.PostCustomerDashboardWalletsSecurity](../../models/operations/postcustomerdashboardwalletssecurity.md) | :heavy_check_mark:                                                                                                 | The security requirements to use for the request.                                                                  |
| `retries`                                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                   | :heavy_minus_sign:                                                                                                 | Configuration to override the default retry behavior of the client.                                                |

### Response

**[List[components.DtoWalletBalanceResponse]](../../models/.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_customer_dashboard_wallets_id_

Get a specific wallet for the authenticated customer

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/customer-dashboard/wallets/{id}" method="get" path="/customer-dashboard/wallets/{id}" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import operations


with FlexPrice(
    server_url="https://api.example.com",
) as flex_price:

    res = flex_price.customer_dashboard.get_customer_dashboard_wallets_id_(security=operations.GetCustomerDashboardWalletsIDSecurity(
        bearer_auth="<YOUR_API_KEY_HERE>",
    ), id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                           | [operations.GetCustomerDashboardWalletsIDSecurity](../../models/operations/getcustomerdashboardwalletsidsecurity.md) | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |
| `id`                                                                                                                 | *str*                                                                                                                | :heavy_check_mark:                                                                                                   | Wallet ID                                                                                                            |
| `retries`                                                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                     | :heavy_minus_sign:                                                                                                   | Configuration to override the default retry behavior of the client.                                                  |

### Response

**[components.DtoWalletBalanceResponse](../../models/components/dtowalletbalanceresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 401, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |