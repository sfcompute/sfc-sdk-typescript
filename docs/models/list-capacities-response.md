# ListCapacitiesResponse

## Example Usage

```typescript
import { ListCapacitiesResponse } from "@sfcompute/sdk/models";

let value: ListCapacitiesResponse = {
  object: "list",
  cursor: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: true,
  data: [],
};
```

## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         | Example                                                                             |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `object`                                                                            | [models.ListCapacitiesResponseObject](../models/list-capacities-response-object.md) | :heavy_check_mark:                                                                  | N/A                                                                                 | list                                                                                |
| `cursor`                                                                            | *string*                                                                            | :heavy_minus_sign:                                                                  | N/A                                                                                 | capc_gqXR7s0Kj5mHvE2wNpLc4Q                                                         |
| `hasMore`                                                                           | *boolean*                                                                           | :heavy_check_mark:                                                                  | N/A                                                                                 |                                                                                     |
| `data`                                                                              | [models.CapacityResponse](../models/capacity-response.md)[]                         | :heavy_check_mark:                                                                  | N/A                                                                                 |                                                                                     |