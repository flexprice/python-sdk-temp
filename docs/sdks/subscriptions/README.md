# Subscriptions

## Overview

### Available Operations

* [get_subscriptions](#get_subscriptions) - List subscriptions
* [post_subscriptions](#post_subscriptions) - Create subscription
* [post_subscriptions_addon](#post_subscriptions_addon) - Add addon to subscription
* [delete_subscriptions_addon](#delete_subscriptions_addon) - Remove addon from subscription
* [put_subscriptions_lineitems_id_](#put_subscriptions_lineitems_id_) - Update subscription line item
* [delete_subscriptions_lineitems_id_](#delete_subscriptions_lineitems_id_) - Delete subscription line item
* [post_subscriptions_search](#post_subscriptions_search) - List subscriptions by filter
* [post_subscriptions_usage](#post_subscriptions_usage) - Get usage by subscription
* [get_subscriptions_id_](#get_subscriptions_id_) - Get subscription
* [post_subscriptions_id_activate](#post_subscriptions_id_activate) - Activate draft subscription
* [get_subscriptions_id_addons_associations](#get_subscriptions_id_addons_associations) - Get active addon associations
* [post_subscriptions_id_cancel](#post_subscriptions_id_cancel) - Cancel subscription
* [post_subscriptions_id_change_execute](#post_subscriptions_id_change_execute) - Execute subscription plan change
* [post_subscriptions_id_change_preview](#post_subscriptions_id_change_preview) - Preview subscription plan change
* [get_subscriptions_id_entitlements](#get_subscriptions_id_entitlements) - Get subscription entitlements
* [get_subscriptions_id_grants_upcoming](#get_subscriptions_id_grants_upcoming) - Get upcoming credit grant applications
* [post_subscriptions_id_pause](#post_subscriptions_id_pause) - Pause a subscription
* [get_subscriptions_id_pauses](#get_subscriptions_id_pauses) - List all pauses for a subscription
* [post_subscriptions_id_resume](#post_subscriptions_id_resume) - Resume a paused subscription

## get_subscriptions

Get subscriptions with optional filtering

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/subscriptions" method="get" path="/subscriptions" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.get_subscriptions()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `request`                                                                                | [operations.GetSubscriptionsRequest](../../models/operations/getsubscriptionsrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `retries`                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                         | :heavy_minus_sign:                                                                       | Configuration to override the default retry behavior of the client.                      |

### Response

**[components.DtoListSubscriptionsResponse](../../models/components/dtolistsubscriptionsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions

Create a new subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions" method="post" path="/subscriptions" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions(request={
        "billing_cadence": components.TypesBillingCadence.RECURRING,
        "billing_period": components.TypesBillingPeriod.HALF_YEARLY,
        "currency": "Nakfa",
        "plan_id": "<id>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `request`                                                                                          | [components.DtoCreateSubscriptionRequest](../../models/components/dtocreatesubscriptionrequest.md) | :heavy_check_mark:                                                                                 | The request object to use for the request.                                                         |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |

### Response

**[components.DtoSubscriptionResponse](../../models/components/dtosubscriptionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_addon

Add an addon to a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/addon" method="post" path="/subscriptions/addon" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_addon(request={
        "addon_id": "<id>",
        "subscription_id": "<id>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `request`                                                                      | [components.DtoAddAddonRequest](../../models/components/dtoaddaddonrequest.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `retries`                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)               | :heavy_minus_sign:                                                             | Configuration to override the default retry behavior of the client.            |

### Response

**[components.DtoAddonAssociationResponse](../../models/components/dtoaddonassociationresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## delete_subscriptions_addon

Remove an addon from a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_/subscriptions/addon" method="delete" path="/subscriptions/addon" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.delete_subscriptions_addon(request={
        "addon_association_id": "<id>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `request`                                                                            | [components.DtoRemoveAddonRequest](../../models/components/dtoremoveaddonrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `retries`                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                     | :heavy_minus_sign:                                                                   | Configuration to override the default retry behavior of the client.                  |

### Response

**[components.DtoSuccessResponse](../../models/components/dtosuccessresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## put_subscriptions_lineitems_id_

Update a subscription line item by terminating the existing one and creating a new one

### Example Usage

<!-- UsageSnippet language="python" operationID="put_/subscriptions/lineitems/{id}" method="put" path="/subscriptions/lineitems/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.put_subscriptions_lineitems_id_(id="<id>", body={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                          | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                               | *str*                                                                                                              | :heavy_check_mark:                                                                                                 | Line Item ID                                                                                                       |
| `body`                                                                                                             | [components.DtoUpdateSubscriptionLineItemRequest](../../models/components/dtoupdatesubscriptionlineitemrequest.md) | :heavy_check_mark:                                                                                                 | Update Line Item Request                                                                                           |
| `retries`                                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                   | :heavy_minus_sign:                                                                                                 | Configuration to override the default retry behavior of the client.                                                |

### Response

**[components.DtoSubscriptionLineItemResponse](../../models/components/dtosubscriptionlineitemresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## delete_subscriptions_lineitems_id_

Delete a subscription line item by setting its end date

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_/subscriptions/lineitems/{id}" method="delete" path="/subscriptions/lineitems/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.delete_subscriptions_lineitems_id_(id="<id>", body={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                          | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                               | *str*                                                                                                              | :heavy_check_mark:                                                                                                 | Line Item ID                                                                                                       |
| `body`                                                                                                             | [components.DtoDeleteSubscriptionLineItemRequest](../../models/components/dtodeletesubscriptionlineitemrequest.md) | :heavy_check_mark:                                                                                                 | Delete Line Item Request                                                                                           |
| `retries`                                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                   | :heavy_minus_sign:                                                                                                 | Configuration to override the default retry behavior of the client.                                                |

### Response

**[components.DtoSubscriptionLineItemResponse](../../models/components/dtosubscriptionlineitemresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_search

List subscriptions by filter

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/search" method="post" path="/subscriptions/search" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_search(request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `request`                                                                                | [components.TypesSubscriptionFilter](../../models/components/typessubscriptionfilter.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `retries`                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                         | :heavy_minus_sign:                                                                       | Configuration to override the default retry behavior of the client.                      |

### Response

**[components.DtoListSubscriptionsResponse](../../models/components/dtolistsubscriptionsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_usage

Get usage for a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/usage" method="post" path="/subscriptions/usage" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_usage(request={
        "end_time": "2024-03-20T00:00:00Z",
        "lifetime_usage": False,
        "start_time": "2024-03-13T00:00:00Z",
        "subscription_id": "123",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                  | [components.DtoGetUsageBySubscriptionRequest](../../models/components/dtogetusagebysubscriptionrequest.md) | :heavy_check_mark:                                                                                         | The request object to use for the request.                                                                 |
| `retries`                                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                           | :heavy_minus_sign:                                                                                         | Configuration to override the default retry behavior of the client.                                        |

### Response

**[components.DtoGetUsageBySubscriptionResponse](../../models/components/dtogetusagebysubscriptionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_subscriptions_id_

Get a subscription by ID

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/subscriptions/{id}" method="get" path="/subscriptions/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.get_subscriptions_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Subscription ID                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoSubscriptionResponse](../../models/components/dtosubscriptionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_id_activate

Activate a draft subscription with a new start date

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/{id}/activate" method="post" path="/subscriptions/{id}/activate" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_id_activate(id="<id>", body={
        "start_date": "<value>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                        | Type                                                                                                             | Required                                                                                                         | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                             | *str*                                                                                                            | :heavy_check_mark:                                                                                               | Subscription ID                                                                                                  |
| `body`                                                                                                           | [components.DtoActivateDraftSubscriptionRequest](../../models/components/dtoactivatedraftsubscriptionrequest.md) | :heavy_check_mark:                                                                                               | Activate Draft Subscription Request                                                                              |
| `retries`                                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                 | :heavy_minus_sign:                                                                                               | Configuration to override the default retry behavior of the client.                                              |

### Response

**[components.DtoSubscriptionResponse](../../models/components/dtosubscriptionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_subscriptions_id_addons_associations

Get active addon associations for a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/subscriptions/{id}/addons/associations" method="get" path="/subscriptions/{id}/addons/associations" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.get_subscriptions_id_addons_associations(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Subscription ID                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[components.DtoAddonAssociationResponse]](../../models/.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_id_cancel

Cancel a subscription with enhanced proration support

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/{id}/cancel" method="post" path="/subscriptions/{id}/cancel" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_id_cancel(id="<id>", body={
        "cancellation_type": components.TypesCancellationType.END_OF_PERIOD,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `id`                                                                                               | *str*                                                                                              | :heavy_check_mark:                                                                                 | Subscription ID                                                                                    |
| `body`                                                                                             | [components.DtoCancelSubscriptionRequest](../../models/components/dtocancelsubscriptionrequest.md) | :heavy_check_mark:                                                                                 | Cancel Subscription Request                                                                        |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |

### Response

**[components.DtoCancelSubscriptionResponse](../../models/components/dtocancelsubscriptionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_id_change_execute

Execute a subscription plan change, including proration and invoice generation

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/{id}/change/execute" method="post" path="/subscriptions/{id}/change/execute" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_id_change_execute(id="<id>", body={
        "billing_cadence": components.TypesBillingCadence.ONETIME,
        "billing_cycle": components.TypesBillingCycle.ANNIVERSARY,
        "billing_period": components.TypesBillingPeriod.HALF_YEARLY,
        "proration_behavior": components.TypesProrationBehavior.NONE,
        "target_plan_id": "<id>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `id`                                                                                               | *str*                                                                                              | :heavy_check_mark:                                                                                 | Subscription ID                                                                                    |
| `body`                                                                                             | [components.DtoSubscriptionChangeRequest](../../models/components/dtosubscriptionchangerequest.md) | :heavy_check_mark:                                                                                 | Subscription change request                                                                        |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |

### Response

**[components.DtoSubscriptionChangeExecuteResponse](../../models/components/dtosubscriptionchangeexecuteresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_id_change_preview

Preview the impact of changing a subscription's plan, including proration calculations

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/{id}/change/preview" method="post" path="/subscriptions/{id}/change/preview" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_id_change_preview(id="<id>", body={
        "billing_cadence": components.TypesBillingCadence.RECURRING,
        "billing_cycle": components.TypesBillingCycle.ANNIVERSARY,
        "billing_period": components.TypesBillingPeriod.WEEKLY,
        "proration_behavior": components.TypesProrationBehavior.CREATE_PRORATIONS,
        "target_plan_id": "<id>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `id`                                                                                               | *str*                                                                                              | :heavy_check_mark:                                                                                 | Subscription ID                                                                                    |
| `body`                                                                                             | [components.DtoSubscriptionChangeRequest](../../models/components/dtosubscriptionchangerequest.md) | :heavy_check_mark:                                                                                 | Subscription change preview request                                                                |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |

### Response

**[components.DtoSubscriptionChangePreviewResponse](../../models/components/dtosubscriptionchangepreviewresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_subscriptions_id_entitlements

Get all entitlements for a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/subscriptions/{id}/entitlements" method="get" path="/subscriptions/{id}/entitlements" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.get_subscriptions_id_entitlements(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Subscription ID                                                     |
| `feature_ids`                                                       | List[*str*]                                                         | :heavy_minus_sign:                                                  | Feature IDs to filter by                                            |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoSubscriptionEntitlementsResponse](../../models/components/dtosubscriptionentitlementsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_subscriptions_id_grants_upcoming

Get upcoming credit grant applications for a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/subscriptions/{id}/grants/upcoming" method="get" path="/subscriptions/{id}/grants/upcoming" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.get_subscriptions_id_grants_upcoming(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Subscription ID                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoListCreditGrantApplicationsResponse](../../models/components/dtolistcreditgrantapplicationsresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_id_pause

Pause a subscription with the specified parameters

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/{id}/pause" method="post" path="/subscriptions/{id}/pause" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_id_pause(id="<id>", body={
        "pause_mode": components.TypesPauseMode.PERIOD_END,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `id`                                                                                             | *str*                                                                                            | :heavy_check_mark:                                                                               | Subscription ID                                                                                  |
| `body`                                                                                           | [components.DtoPauseSubscriptionRequest](../../models/components/dtopausesubscriptionrequest.md) | :heavy_check_mark:                                                                               | Pause subscription request                                                                       |
| `retries`                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                 | :heavy_minus_sign:                                                                               | Configuration to override the default retry behavior of the client.                              |

### Response

**[components.DtoSubscriptionPauseResponse](../../models/components/dtosubscriptionpauseresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_subscriptions_id_pauses

List all pauses for a subscription

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/subscriptions/{id}/pauses" method="get" path="/subscriptions/{id}/pauses" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.get_subscriptions_id_pauses(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Subscription ID                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[components.DtoListSubscriptionPausesResponse]](../../models/.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_subscriptions_id_resume

Resume a paused subscription with the specified parameters

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/subscriptions/{id}/resume" method="post" path="/subscriptions/{id}/resume" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.subscriptions.post_subscriptions_id_resume(id="<id>", body={
        "resume_mode": components.TypesResumeMode.SCHEDULED,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `id`                                                                                               | *str*                                                                                              | :heavy_check_mark:                                                                                 | Subscription ID                                                                                    |
| `body`                                                                                             | [components.DtoResumeSubscriptionRequest](../../models/components/dtoresumesubscriptionrequest.md) | :heavy_check_mark:                                                                                 | Resume subscription request                                                                        |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |

### Response

**[components.DtoSubscriptionPauseResponse](../../models/components/dtosubscriptionpauseresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |