# CreateCapacityRequest

## Example Usage

```typescript
import { CreateCapacityRequest } from "@sfcompute/sdk/models";

let value: CreateCapacityRequest = {
  name: "my-resource-name",
  zones: [
    "richmond",
  ],
  nodeTemplate: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
  startNodesAutomatically: true,
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

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            | Example                                                                                                |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `name`                                                                                                 | *string*                                                                                               | :heavy_minus_sign:                                                                                     | N/A                                                                                                    | my-resource-name                                                                                       |
| `zones`                                                                                                | *string*[]                                                                                             | :heavy_check_mark:                                                                                     | Datacenter locations orders into this capacity can acquire compute from.                               | [<br/>"richmond"<br/>]                                                                                 |
| `nodeTemplate`                                                                                         | *string*                                                                                               | :heavy_minus_sign:                                                                                     | N/A                                                                                                    | ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F                                                                            |
| `startNodesAutomatically`                                                                              | *boolean*                                                                                              | :heavy_check_mark:                                                                                     | Automatically start nodes when compute is available. Requires `node_template`.                         |                                                                                                        |
| `scheduler`                                                                                            | *models.SchedulerDetails*                                                                              | :heavy_minus_sign:                                                                                     | Schedulers automatically place buy and sell orders to<br/>attempt to achieve desired compute availability. |                                                                                                        |