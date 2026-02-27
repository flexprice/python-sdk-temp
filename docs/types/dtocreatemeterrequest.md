# DtoCreateMeterRequest


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            | Example                                                |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `aggregation`                                          | [types.MeterAggregation](../types/meteraggregation.md) | :heavy_check_mark:                                     | N/A                                                    |                                                        |
| `event_name`                                           | *str*                                                  | :heavy_check_mark:                                     | N/A                                                    | api_request                                            |
| `filters`                                              | List[[types.MeterFilter](../types/meterfilter.md)]     | :heavy_minus_sign:                                     | N/A                                                    |                                                        |
| `name`                                                 | *str*                                                  | :heavy_check_mark:                                     | N/A                                                    | API Usage Meter                                        |
| `reset_usage`                                          | [types.ResetUsage](../types/resetusage.md)             | :heavy_check_mark:                                     | N/A                                                    |                                                        |