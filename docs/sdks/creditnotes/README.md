# CreditNotes

## Overview

### Available Operations

* [get_creditnotes](#get_creditnotes) - List credit notes with filtering
* [post_creditnotes](#post_creditnotes) - Create a new credit note
* [get_creditnotes_id_](#get_creditnotes_id_) - Get a credit note by ID
* [post_creditnotes_id_finalize](#post_creditnotes_id_finalize) - Process a draft credit note
* [post_creditnotes_id_void](#post_creditnotes_id_void) - Void a credit note

## get_creditnotes

Lists credit notes with filtering

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/creditnotes" method="get" path="/creditnotes" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.credit_notes.get_creditnotes()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `request`                                                                            | [operations.GetCreditnotesRequest](../../models/operations/getcreditnotesrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `retries`                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                     | :heavy_minus_sign:                                                                   | Configuration to override the default retry behavior of the client.                  |

### Response

**[components.DtoListCreditNotesResponse](../../models/components/dtolistcreditnotesresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 401, 403, 404         | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_creditnotes

Creates a new credit note

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/creditnotes" method="post" path="/creditnotes" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.credit_notes.post_creditnotes(request={
        "invoice_id": "<id>",
        "reason": components.TypesCreditNoteReason.BILLING_ERROR,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `request`                                                                                      | [components.DtoCreateCreditNoteRequest](../../models/components/dtocreatecreditnoterequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `retries`                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                               | :heavy_minus_sign:                                                                             | Configuration to override the default retry behavior of the client.                            |

### Response

**[components.DtoCreditNoteResponse](../../models/components/dtocreditnoteresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 401, 403, 404         | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_creditnotes_id_

Retrieves a credit note by ID

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/creditnotes/{id}" method="get" path="/creditnotes/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.credit_notes.get_creditnotes_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Credit note ID                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoCreditNoteResponse](../../models/components/dtocreditnoteresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 401, 403, 404         | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_creditnotes_id_finalize

Processes a draft credit note

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/creditnotes/{id}/finalize" method="post" path="/creditnotes/{id}/finalize" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.credit_notes.post_creditnotes_id_finalize(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Credit note ID                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoCreditNoteResponse](../../models/components/dtocreditnoteresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 401, 403, 404         | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_creditnotes_id_void

Voids a credit note

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/creditnotes/{id}/void" method="post" path="/creditnotes/{id}/void" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.credit_notes.post_creditnotes_id_void(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Credit note ID                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoCreditNoteResponse](../../models/components/dtocreditnoteresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 401, 403, 404         | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |