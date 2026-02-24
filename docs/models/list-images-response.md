# ListImagesResponse

## Example Usage

```typescript
import { ListImagesResponse } from "@sfcompute/sdk/models";

let value: ListImagesResponse = {
  object: "list",
  cursor: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: false,
  data: [],
};
```

## Fields

| Field                                                                       | Type                                                                        | Required                                                                    | Description                                                                 | Example                                                                     |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `object`                                                                    | [models.ListImagesResponseObject](../models/list-images-response-object.md) | :heavy_check_mark:                                                          | N/A                                                                         | list                                                                        |
| `cursor`                                                                    | *string*                                                                    | :heavy_minus_sign:                                                          | N/A                                                                         | imagec_gqXR7s0Kj5mHvE2wNpLc4Q                                               |
| `hasMore`                                                                   | *boolean*                                                                   | :heavy_check_mark:                                                          | N/A                                                                         |                                                                             |
| `data`                                                                      | [models.ImageListEntry](../models/image-list-entry.md)[]                    | :heavy_check_mark:                                                          | N/A                                                                         |                                                                             |