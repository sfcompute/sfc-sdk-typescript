# MarketApiListCapacitiesResponse

## Example Usage

```typescript
import { MarketApiListCapacitiesResponse } from "@sfcompute/sdk/models";

let value: MarketApiListCapacitiesResponse = {
  cursor: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: false,
  data: [
    {
      id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
      name: "my-resource-name",
      zones: [
        "richmond",
      ],
      nodeTemplate: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
      startNodesAutomatically: false,
      allocationSchedule: {
        total: [
          {
            effectiveAt: 1738972800,
            nodeAllocation: 864662,
          },
        ],
        byZone: {},
      },
      createdAt: 1738972800,
      scheduler: {
        desiredQuantity: 331669,
        managedWindowMinutes: 674168,
        minSellPriceDollarsPerNodeHour: "2.500000",
        maxBuyPriceDollarsPerNodeHour: "2.500000",
        enabled: false,
      },
    },
  ],
};
```

## Fields

| Field                                                                           | Type                                                                            | Required                                                                        | Description                                                                     | Example                                                                         |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `object`                                                                        | *"list"*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             |                                                                                 |
| `cursor`                                                                        | *string*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             | capc_gqXR7s0Kj5mHvE2wNpLc4Q                                                     |
| `hasMore`                                                                       | *boolean*                                                                       | :heavy_check_mark:                                                              | N/A                                                                             |                                                                                 |
| `data`                                                                          | [models.MarketApiCapacityResponse](../models/market-api-capacity-response.md)[] | :heavy_check_mark:                                                              | N/A                                                                             |                                                                                 |