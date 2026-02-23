# PatchCapacityHandlerRequest

## Example Usage

```typescript
import { PatchCapacityHandlerRequest } from "@sfcompute/sdk/models/operations";

let value: PatchCapacityHandlerRequest = {
  id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  body: {
    zones: [
      "richmond",
    ],
    scheduler: {
      desiredQuantity: 424173,
      managedWindowMinutes: 602358,
      minSellPriceDollarsPerNodeHour: "2.500000",
      maxBuyPriceDollarsPerNodeHour: "2.500000",
      enabled: true,
    },
  },
};
```

## Fields

| Field                                                                                     | Type                                                                                      | Required                                                                                  | Description                                                                               | Example                                                                                   |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `id`                                                                                      | *string*                                                                                  | :heavy_check_mark:                                                                        | N/A                                                                                       | cap_k3R-nX9vLm7Qp2Yw5Jd8F                                                                 |
| `body`                                                                                    | [models.MarketApiPatchCapacityRequest](../../models/market-api-patch-capacity-request.md) | :heavy_check_mark:                                                                        | N/A                                                                                       |                                                                                           |