# UpdateCapacityRequest

## Example Usage

```typescript
import { UpdateCapacityRequest } from "@sfcompute/sdk/models/operations";

let value: UpdateCapacityRequest = {
  id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  body: {
    zones: [
      "richmond",
    ],
    scheduler: {
      desiredQuantity: 476178,
      managedWindowMinutes: 630630,
      minSellPriceDollarsPerNodeHour: "2.500000",
      maxBuyPriceDollarsPerNodeHour: "2.500000",
      enabled: true,
      type: "spot_scaler",
    },
  },
};
```

## Fields

| Field                                                                 | Type                                                                  | Required                                                              | Description                                                           | Example                                                               |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `id`                                                                  | *string*                                                              | :heavy_check_mark:                                                    | N/A                                                                   | cap_k3R-nX9vLm7Qp2Yw5Jd8F                                             |
| `body`                                                                | [models.PatchCapacityRequest](../../models/patch-capacity-request.md) | :heavy_check_mark:                                                    | N/A                                                                   |                                                                       |