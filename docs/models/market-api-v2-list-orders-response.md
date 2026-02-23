# MarketApiV2ListOrdersResponse

## Example Usage

```typescript
import { MarketApiV2ListOrdersResponse } from "@sfcompute/sdk/models";

let value: MarketApiV2ListOrdersResponse = {
  cursor: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: false,
  data: [
    {
      id: "ordr_k3R-nX9vLm7Qp2Yw5Jd8F",
      capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
      side: "sell",
      allowStanding: true,
      zones: [
        "richmond",
      ],
      nodeCount: 975144,
      startAt: 1738972800,
      endAt: 1738972800,
      limitPriceDollarsPerNodeHour: "2.500000",
      status: "standing",
      createdAt: 1738972800,
      filledAt: 1738972800,
      filledPriceDollarsPerNodeHour: "2.500000",
      cancelledAt: 1738972800,
    },
  ],
};
```

## Fields

| Field                                                                          | Type                                                                           | Required                                                                       | Description                                                                    | Example                                                                        |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `object`                                                                       | *"list"*                                                                       | :heavy_minus_sign:                                                             | N/A                                                                            |                                                                                |
| `cursor`                                                                       | *string*                                                                       | :heavy_minus_sign:                                                             | N/A                                                                            | ordrc_gqXR7s0Kj5mHvE2wNpLc4Q                                                   |
| `hasMore`                                                                      | *boolean*                                                                      | :heavy_check_mark:                                                             | N/A                                                                            |                                                                                |
| `data`                                                                         | [models.MarketApiV2OrderResponse](../models/market-api-v2-order-response.md)[] | :heavy_check_mark:                                                             | N/A                                                                            |                                                                                |