# V2ListOrdersResponse

## Example Usage

```typescript
import { V2ListOrdersResponse } from "@sfcompute/sdk/models";

let value: V2ListOrdersResponse = {
  object: "list",
  cursor: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: false,
  data: [],
};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      | Example                                                                          |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `object`                                                                         | [models.V2ListOrdersResponseObject](../models/v2-list-orders-response-object.md) | :heavy_check_mark:                                                               | N/A                                                                              | list                                                                             |
| `cursor`                                                                         | *string*                                                                         | :heavy_minus_sign:                                                               | N/A                                                                              | ordrc_gqXR7s0Kj5mHvE2wNpLc4Q                                                     |
| `hasMore`                                                                        | *boolean*                                                                        | :heavy_check_mark:                                                               | N/A                                                                              |                                                                                  |
| `data`                                                                           | [models.V2OrderResponse](../models/v2-order-response.md)[]                       | :heavy_check_mark:                                                               | N/A                                                                              |                                                                                  |