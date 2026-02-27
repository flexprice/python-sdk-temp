# UpdateScheduledTaskRequest


## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `id`                                                                             | *str*                                                                            | :heavy_check_mark:                                                               | Scheduled Task ID                                                                |
| `body`                                                                           | [types.DtoUpdateScheduledTaskRequest](../types/dtoupdatescheduledtaskrequest.md) | :heavy_check_mark:                                                               | Update request (enabled: true/false to pause/resume)                             |