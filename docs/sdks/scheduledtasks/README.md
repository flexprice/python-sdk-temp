# ScheduledTasks

## Overview

### Available Operations

* [get_tasks_scheduled](#get_tasks_scheduled) - List scheduled tasks
* [post_tasks_scheduled](#post_tasks_scheduled) - Create a scheduled task
* [post_tasks_scheduled_schedule_update_billing_period](#post_tasks_scheduled_schedule_update_billing_period) - Schedule update billing period
* [get_tasks_scheduled_id_](#get_tasks_scheduled_id_) - Get a scheduled task
* [put_tasks_scheduled_id_](#put_tasks_scheduled_id_) - Update a scheduled task
* [delete_tasks_scheduled_id_](#delete_tasks_scheduled_id_) - Delete a scheduled task
* [post_tasks_scheduled_id_run](#post_tasks_scheduled_id_run) - Trigger force run

## get_tasks_scheduled

Get a list of scheduled tasks with optional filters

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/tasks/scheduled" method="get" path="/tasks/scheduled" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.scheduled_tasks.get_tasks_scheduled()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `request`                                                                                  | [operations.GetTasksScheduledRequest](../../models/operations/gettasksscheduledrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `retries`                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                           | :heavy_minus_sign:                                                                         | Configuration to override the default retry behavior of the client.                        |

### Response

**[components.DtoListScheduledTasksResponse](../../models/components/dtolistscheduledtasksresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_tasks_scheduled

Create a new scheduled task for data export

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/tasks/scheduled" method="post" path="/tasks/scheduled" -->
```python
from flexprice_sdk_test import FlexPrice
from flexprice_sdk_test.models import components


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.scheduled_tasks.post_tasks_scheduled(request={
        "connection_id": "<id>",
        "entity_type": components.TypesScheduledTaskEntityType.CREDIT_TOPUPS,
        "interval": components.TypesScheduledTaskInterval.FIFTEEN_MIN,
        "job_config": {},
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `request`                                                                                            | [components.DtoCreateScheduledTaskRequest](../../models/components/dtocreatescheduledtaskrequest.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |
| `retries`                                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                     | :heavy_minus_sign:                                                                                   | Configuration to override the default retry behavior of the client.                                  |

### Response

**[components.DtoScheduledTaskResponse](../../models/components/dtoscheduledtaskresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_tasks_scheduled_schedule_update_billing_period

Schedule an update billing period workflow

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/tasks/scheduled/schedule-update-billing-period" method="post" path="/tasks/scheduled/schedule-update-billing-period" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.scheduled_tasks.post_tasks_scheduled_schedule_update_billing_period(request={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                          | Type                                                                                                                                               | Required                                                                                                                                           | Description                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                          | [operations.PostTasksScheduledScheduleUpdateBillingPeriodRequest](../../models/operations/posttasksscheduledscheduleupdatebillingperiodrequest.md) | :heavy_check_mark:                                                                                                                                 | The request object to use for the request.                                                                                                         |
| `retries`                                                                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                   | :heavy_minus_sign:                                                                                                                                 | Configuration to override the default retry behavior of the client.                                                                                |

### Response

**[operations.PostTasksScheduledScheduleUpdateBillingPeriodResponse](../../models/operations/posttasksscheduledscheduleupdatebillingperiodresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400                        | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## get_tasks_scheduled_id_

Get a scheduled task by ID

### Example Usage

<!-- UsageSnippet language="python" operationID="get_/tasks/scheduled/{id}" method="get" path="/tasks/scheduled/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.scheduled_tasks.get_tasks_scheduled_id_(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Scheduled Task ID                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[components.DtoScheduledTaskResponse](../../models/components/dtoscheduledtaskresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## put_tasks_scheduled_id_

Update a scheduled task by ID - Only enabled field can be changed (pause/resume)

### Example Usage

<!-- UsageSnippet language="python" operationID="put_/tasks/scheduled/{id}" method="put" path="/tasks/scheduled/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.scheduled_tasks.put_tasks_scheduled_id_(id="<id>", body={
        "enabled": True,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `id`                                                                                                 | *str*                                                                                                | :heavy_check_mark:                                                                                   | Scheduled Task ID                                                                                    |
| `body`                                                                                               | [components.DtoUpdateScheduledTaskRequest](../../models/components/dtoupdatescheduledtaskrequest.md) | :heavy_check_mark:                                                                                   | Update request (enabled: true/false to pause/resume)                                                 |
| `retries`                                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                     | :heavy_minus_sign:                                                                                   | Configuration to override the default retry behavior of the client.                                  |

### Response

**[components.DtoScheduledTaskResponse](../../models/components/dtoscheduledtaskresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## delete_tasks_scheduled_id_

Archive a scheduled task by ID (soft delete) - Sets status to archived and deletes from Temporal

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_/tasks/scheduled/{id}" method="delete" path="/tasks/scheduled/{id}" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    flex_price.scheduled_tasks.delete_tasks_scheduled_id_(id="<id>")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Scheduled Task ID                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |

## post_tasks_scheduled_id_run

Trigger a force run export immediately for a scheduled task with optional custom time range

### Example Usage

<!-- UsageSnippet language="python" operationID="post_/tasks/scheduled/{id}/run" method="post" path="/tasks/scheduled/{id}/run" -->
```python
from flexprice_sdk_test import FlexPrice


with FlexPrice(
    server_url="https://api.example.com",
    api_key_auth="<YOUR_API_KEY_HERE>",
) as flex_price:

    res = flex_price.scheduled_tasks.post_tasks_scheduled_id_run(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                   | *str*                                                                                                  | :heavy_check_mark:                                                                                     | Scheduled Task ID                                                                                      |
| `body`                                                                                                 | [Optional[components.DtoTriggerForceRunRequest]](../../models/components/dtotriggerforcerunrequest.md) | :heavy_minus_sign:                                                                                     | Optional start and end time for custom range                                                           |
| `retries`                                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                       | :heavy_minus_sign:                                                                                     | Configuration to override the default retry behavior of the client.                                    |

### Response

**[components.DtoTriggerForceRunResponse](../../models/components/dtotriggerforcerunresponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.ErrorsErrorResponse | 400, 404                   | application/json           |
| errors.ErrorsErrorResponse | 500                        | application/json           |
| errors.SDKError            | 4XX, 5XX                   | \*/\*                      |