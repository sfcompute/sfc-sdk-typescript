# ListNodesResponse

## Example Usage

```typescript
import { ListNodesResponse } from "@sfcompute/sdk/models";

let value: ListNodesResponse = {
  object: "list",
  cursor: "nodec_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: true,
  data: [],
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `object`                                                                  | [models.ListNodesResponseObject](../models/list-nodes-response-object.md) | :heavy_check_mark:                                                        | N/A                                                                       | list                                                                      |
| `cursor`                                                                  | *string*                                                                  | :heavy_minus_sign:                                                        | N/A                                                                       | nodec_gqXR7s0Kj5mHvE2wNpLc4Q                                              |
| `hasMore`                                                                 | *boolean*                                                                 | :heavy_check_mark:                                                        | N/A                                                                       |                                                                           |
| `data`                                                                    | [models.NodeResponse](../models/node-response.md)[]                       | :heavy_check_mark:                                                        | N/A                                                                       |                                                                           |