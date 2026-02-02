# TypesMoyasarConnectionMetadata


## Fields

| Field                                                 | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `publishable_key`                                     | *Optional[str]*                                       | :heavy_minus_sign:                                    | Moyasar Publishable Key (encrypted, for frontend use) |
| `secret_key`                                          | *Optional[str]*                                       | :heavy_minus_sign:                                    | Moyasar Secret Key (encrypted)                        |
| `webhook_secret`                                      | *Optional[str]*                                       | :heavy_minus_sign:                                    | Moyasar Webhook Secret (encrypted, optional)          |