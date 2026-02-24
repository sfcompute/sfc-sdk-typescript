# CreateImageUploadPartUrlRequest

## Example Usage

```typescript
import { CreateImageUploadPartUrlRequest } from "@sfcompute/sdk/models/operations";

let value: CreateImageUploadPartUrlRequest = {
  id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  body: {
    partId: 252976,
  },
};
```

## Fields

| Field                                                           | Type                                                            | Required                                                        | Description                                                     | Example                                                         |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `id`                                                            | *string*                                                        | :heavy_check_mark:                                              | Image ID                                                        | image_k3R-nX9vLm7Qp2Yw5Jd8F                                     |
| `body`                                                          | [models.UploadPartRequest](../../models/upload-part-request.md) | :heavy_check_mark:                                              | N/A                                                             |                                                                 |