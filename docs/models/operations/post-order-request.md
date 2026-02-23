# PostOrderRequest

## Example Usage

```typescript
import { PostOrderRequest } from "@sfcompute/sdk/models/operations";

let value: PostOrderRequest = {
  body: {
    capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    side: "sell",
    nodeCount: 232126,
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
| `body`                                                                                                                                                      | [models.MarketApiV2CreateOrderRequest](../../models/market-api-v2-create-order-request.md)                                                                  | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |