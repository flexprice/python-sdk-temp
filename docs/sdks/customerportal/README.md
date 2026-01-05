# CustomerPortal

## Overview

### Available Operations

* [get_portal_external_id_](#get_portal_external_id_) - Create a customer portal session

## get_portal_external_id_

Generate a dashboard URL/token for a customer to access their billing information

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/portal/{external_id}" method="get" path="/portal/{external_id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.customer_portal.get_portal_external_id_(external_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `external_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | Customer External ID                                                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoPortalSessionResponse](../../models/components/dtoportalsessionresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |