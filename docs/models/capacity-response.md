# CapacityResponse

## Example Usage

```typescript
import { CapacityResponse } from "@sfcompute/sdk/models";

let value: CapacityResponse = {
  object: "capacity",
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
        nodeAllocation: 978476,
      },
    ],
    byZone: {
      "key": [
        {
          effectiveAt: 1738972800,
          nodeAllocation: 528716,
        },
      ],
    },
  },
  createdAt: 1738972800,
  scheduler: {
    desiredQuantity: 476178,
    managedWindowMinutes: 630630,
    minSellPriceDollarsPerNodeHour: "2.500000",
    maxBuyPriceDollarsPerNodeHour: "2.500000",
    enabled: true,
    type: "spot_scaler",
  },
};
```

## Fields

| Field                                                                                                                                                                      | Type                                                                                                                                                                       | Required                                                                                                                                                                   | Description                                                                                                                                                                | Example                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `object`                                                                                                                                                                   | [models.CapacityResponseObject](../models/capacity-response-object.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                         | N/A                                                                                                                                                                        | capacity                                                                                                                                                                   |
| `id`                                                                                                                                                                       | *string*                                                                                                                                                                   | :heavy_check_mark:                                                                                                                                                         | N/A                                                                                                                                                                        | cap_k3R-nX9vLm7Qp2Yw5Jd8F                                                                                                                                                  |
| `name`                                                                                                                                                                     | *string*                                                                                                                                                                   | :heavy_minus_sign:                                                                                                                                                         | N/A                                                                                                                                                                        | my-resource-name                                                                                                                                                           |
| `zones`                                                                                                                                                                    | *string*[]                                                                                                                                                                 | :heavy_check_mark:                                                                                                                                                         | Datacenter locations orders into this capacity can acquire compute from.                                                                                                   |                                                                                                                                                                            |
| `nodeTemplate`                                                                                                                                                             | *string*                                                                                                                                                                   | :heavy_minus_sign:                                                                                                                                                         | N/A                                                                                                                                                                        | ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F                                                                                                                                                |
| `startNodesAutomatically`                                                                                                                                                  | *boolean*                                                                                                                                                                  | :heavy_check_mark:                                                                                                                                                         | If enabled, nodes will be provisioned and terminated + deleted<br/>automatically based on currently available allocation in this capacity.<br/>Requires `node_template` to be set. |                                                                                                                                                                            |
| `allocationSchedule`                                                                                                                                                       | [models.AllocationSchedule](../models/allocation-schedule.md)                                                                                                              | :heavy_check_mark:                                                                                                                                                         | N/A                                                                                                                                                                        |                                                                                                                                                                            |
| `createdAt`                                                                                                                                                                | *number*                                                                                                                                                                   | :heavy_check_mark:                                                                                                                                                         | Unix timestamp.                                                                                                                                                            | 1738972800                                                                                                                                                                 |
| `scheduler`                                                                                                                                                                | *models.SchedulerDetails*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                         | Schedulers automatically place buy and sell orders to<br/>attempt to achieve desired compute availability.                                                                 |                                                                                                                                                                            |