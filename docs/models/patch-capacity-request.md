# PatchCapacityRequest

## Example Usage

```typescript
import { PatchCapacityRequest } from "@sfcompute/sdk/models";

let value: PatchCapacityRequest = {
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
};
```

## Fields

| Field                                                                                                                                        | Type                                                                                                                                         | Required                                                                                                                                     | Description                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`                                                                                                                                       | *string*                                                                                                                                     | :heavy_minus_sign:                                                                                                                           | Unique name for this capacity. Set to null to clear.                                                                                         |
| `zones`                                                                                                                                      | *string*[]                                                                                                                                   | :heavy_minus_sign:                                                                                                                           | Datacenter locations orders into this capacity can acquire compute from.<br/>Replaces existing zones. Does not affect already scheduled compute. |
| `nodeTemplate`                                                                                                                               | *string*                                                                                                                                     | :heavy_minus_sign:                                                                                                                           | Template applied when nodes are automatically provisioned within the<br/>capacity. The template is not applied to pre-existing nodes.        |
| `startNodesAutomatically`                                                                                                                    | *boolean*                                                                                                                                    | :heavy_minus_sign:                                                                                                                           | Automatically provision and terminate nodes based on currently available<br/>allocation. Requires `node_template` to be set.                 |
| `scheduler`                                                                                                                                  | *models.SchedulerDetails*                                                                                                                    | :heavy_minus_sign:                                                                                                                           | Schedulers automatically place buy and sell orders to<br/>attempt to achieve desired compute availability.                                   |