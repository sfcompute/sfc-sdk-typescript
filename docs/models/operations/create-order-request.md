# CreateOrderRequest

## Example Usage

```typescript
import { CreateOrderRequest } from "@sfcompute/sdk/models/operations";

let value: CreateOrderRequest = {
  body: {
    capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    side: "sell",
    nodeCount: 993066,
    startAt: 1738972800,
    endAt: 1738972800,
    limitPriceDollarsPerNodeHour: "2.500000",
  },
};
```

## Fields

| Field                                                                                                                                                       | Type                                                                                                                                                        | Required                                                                                                                                                    | Description                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `idempotencyKey`                                                                                                                                            | *string*                                                                                                                                                    | :heavy_minus_sign:                                                                                                                                          | Unique key to ensure idempotent order creation. If provided, duplicate requests with the same key will not place a new order and return the original order. |
| `body`                                                                                                                                                      | [models.V2CreateOrderRequest](../../models/v2-create-order-request.md)                                                                                      | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |