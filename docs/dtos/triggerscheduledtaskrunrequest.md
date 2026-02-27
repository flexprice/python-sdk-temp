# TriggerScheduledTaskRunRequest


## Fields

| Field                                                                              | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `id`                                                                               | *str*                                                                              | :heavy_check_mark:                                                                 | Scheduled Task ID                                                                  |
| `body`                                                                             | [Optional[types.DtoTriggerForceRunRequest]](../types/dtotriggerforcerunrequest.md) | :heavy_minus_sign:                                                                 | Optional start and end time for custom range                                       |