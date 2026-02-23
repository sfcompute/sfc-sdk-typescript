# ListCapacitiesHandlerRequest

## Example Usage

```typescript
import { ListCapacitiesHandlerRequest } from "@sfcompute/sdk/models/operations";

let value: ListCapacitiesHandlerRequest = {
  startingAfter: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
  endingBefore: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                | Example                                                    |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `limit`                                                    | *number*                                                   | :heavy_minus_sign:                                         | N/A                                                        |                                                            |
| `startingAfter`                                            | *string*                                                   | :heavy_minus_sign:                                         | Set to the response's `cursor` to fetch the next page.     | capc_gqXR7s0Kj5mHvE2wNpLc4Q                                |
| `endingBefore`                                             | *string*                                                   | :heavy_minus_sign:                                         | Set to the response's `cursor` to fetch the previous page. | capc_gqXR7s0Kj5mHvE2wNpLc4Q                                |
| `includeDeleted`                                           | *boolean*                                                  | :heavy_minus_sign:                                         | N/A                                                        |                                                            |