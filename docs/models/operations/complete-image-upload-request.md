# CompleteImageUploadRequest

## Example Usage

```typescript
import { CompleteImageUploadRequest } from "@sfcompute/sdk/models/operations";

let value: CompleteImageUploadRequest = {
  id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  body: {
    sha256: "<value>",
  },
};
```

## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `id`                                                                    | *string*                                                                | :heavy_check_mark:                                                      | Image ID                                                                | image_k3R-nX9vLm7Qp2Yw5Jd8F                                             |
| `body`                                                                  | [models.CompleteUploadRequest](../../models/complete-upload-request.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |