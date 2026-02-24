# ListImagesRequest

## Example Usage

```typescript
import { ListImagesRequest } from "@sfcompute/sdk/models/operations";

let value: ListImagesRequest = {
  startingAfter: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
  endingBefore: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
};
```

## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                | Example                                                                    |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `limit`                                                                    | *number*                                                                   | :heavy_minus_sign:                                                         | Maximum number of results to return (1-200, default 50).                   |                                                                            |
| `startingAfter`                                                            | *string*                                                                   | :heavy_minus_sign:                                                         | Cursor for forward pagination (from a previous response's `cursor` field). | imagec_gqXR7s0Kj5mHvE2wNpLc4Q                                              |
| `endingBefore`                                                             | *string*                                                                   | :heavy_minus_sign:                                                         | Cursor for backward pagination.                                            | imagec_gqXR7s0Kj5mHvE2wNpLc4Q                                              |
| `includeDeleted`                                                           | *boolean*                                                                  | :heavy_minus_sign:                                                         | Include soft-deleted images in the results.                                |                                                                            |