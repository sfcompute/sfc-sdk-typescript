# ListNodeTemplatesRequest

## Example Usage

```typescript
import { ListNodeTemplatesRequest } from "@sfcompute/sdk/models/operations";

let value: ListNodeTemplatesRequest = {
  startingAfter: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
  endingBefore: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
};
```

## Fields

| Field                                                                 | Type                                                                  | Required                                                              | Description                                                           | Example                                                               |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `limit`                                                               | *number*                                                              | :heavy_minus_sign:                                                    | N/A                                                                   |                                                                       |
| `startingAfter`                                                       | *string*                                                              | :heavy_minus_sign:                                                    | Set to the response's `cursor` to fetch the next page.                | ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q                                         |
| `endingBefore`                                                        | *string*                                                              | :heavy_minus_sign:                                                    | Set to the response's `cursor` to fetch the previous page.            | ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q                                         |
| `includeDeleted`                                                      | *boolean*                                                             | :heavy_minus_sign:                                                    | N/A                                                                   |                                                                       |
| `include`                                                             | [models.NodeTemplateInclude](../../models/node-template-include.md)[] | :heavy_minus_sign:                                                    | Additional fields to include in the response.                         |                                                                       |