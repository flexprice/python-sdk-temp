# DtoCreateScheduledTaskRequest


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `connection_id`                                                      | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `enabled`                                                            | *Optional[bool]*                                                     | :heavy_minus_sign:                                                   | N/A                                                                  |
| `entity_type`                                                        | [types.ScheduledTaskEntityType](../types/scheduledtaskentitytype.md) | :heavy_check_mark:                                                   | N/A                                                                  |
| `interval`                                                           | [types.ScheduledTaskInterval](../types/scheduledtaskinterval.md)     | :heavy_check_mark:                                                   | N/A                                                                  |
| `job_config`                                                         | [types.S3JobConfig](../types/s3jobconfig.md)                         | :heavy_check_mark:                                                   | N/A                                                                  |