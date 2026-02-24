# ListNodeTemplatesResponse

## Example Usage

```typescript
import { ListNodeTemplatesResponse } from "@sfcompute/sdk/models";

let value: ListNodeTemplatesResponse = {
  cursor: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: false,
  data: [],
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `object`                                                             | *"list"*                                                             | :heavy_minus_sign:                                                   | N/A                                                                  |                                                                      |
| `cursor`                                                             | *string*                                                             | :heavy_minus_sign:                                                   | N/A                                                                  | ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q                                        |
| `hasMore`                                                            | *boolean*                                                            | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |
| `data`                                                               | [models.NodeTemplateResponse](../models/node-template-response.md)[] | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |