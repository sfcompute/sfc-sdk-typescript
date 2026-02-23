# ListOrdersRequest

## Example Usage

```typescript
import { ListOrdersRequest } from "@sfcompute/sdk/models/operations";

let value: ListOrdersRequest = {
  capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  createdAfter: 1738972800,
  createdBefore: 1738972800,
  startingAfter: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
  endingBefore: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
};
```

## Fields

| Field                                                                         | Type                                                                          | Required                                                                      | Description                                                                   | Example                                                                       |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `capacity`                                                                    | *string*                                                                      | :heavy_minus_sign:                                                            | Filter by capacity.                                                           | cap_k3R-nX9vLm7Qp2Yw5Jd8F                                                     |
| `side`                                                                        | [models.MarketApiSide](../../models/market-api-side.md)                       | :heavy_minus_sign:                                                            | N/A                                                                           |                                                                               |
| `status`                                                                      | [models.MarketApiV2OrderStatus](../../models/market-api-v2-order-status.md)[] | :heavy_minus_sign:                                                            | Filter by status (repeatable).                                                |                                                                               |
| `createdAfter`                                                                | *number*                                                                      | :heavy_minus_sign:                                                            | N/A                                                                           | 1738972800                                                                    |
| `createdBefore`                                                               | *number*                                                                      | :heavy_minus_sign:                                                            | N/A                                                                           | 1738972800                                                                    |
| `sortBy`                                                                      | *operations.ListOrdersSortBy*                                                 | :heavy_minus_sign:                                                            | Prefix with `-` for descending.                                               |                                                                               |
| `limit`                                                                       | *number*                                                                      | :heavy_minus_sign:                                                            | N/A                                                                           |                                                                               |
| `startingAfter`                                                               | *string*                                                                      | :heavy_minus_sign:                                                            | Set to the response's `cursor` to fetch the next page.                        | ordrc_gqXR7s0Kj5mHvE2wNpLc4Q                                                  |
| `endingBefore`                                                                | *string*                                                                      | :heavy_minus_sign:                                                            | Set to the response's `cursor` to fetch the previous page.                    | ordrc_gqXR7s0Kj5mHvE2wNpLc4Q                                                  |