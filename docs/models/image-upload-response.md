# ImageUploadResponse

## Example Usage

```typescript
import { ImageUploadResponse } from "@sfcompute/sdk/models";

let value: ImageUploadResponse = {
  object: "image",
  id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  name: "my-resource-name",
  uploadStatus: "completed",
  createdAt: 1738972800,
};
```

## Fields

| Field                                                                         | Type                                                                          | Required                                                                      | Description                                                                   | Example                                                                       |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `object`                                                                      | [models.ImageUploadResponseObject](../models/image-upload-response-object.md) | :heavy_check_mark:                                                            | N/A                                                                           | image                                                                         |
| `id`                                                                          | *string*                                                                      | :heavy_check_mark:                                                            | N/A                                                                           | image_k3R-nX9vLm7Qp2Yw5Jd8F                                                   |
| `name`                                                                        | *string*                                                                      | :heavy_check_mark:                                                            | N/A                                                                           | my-resource-name                                                              |
| `uploadStatus`                                                                | [models.ImageUploadStatus](../models/image-upload-status.md)                  | :heavy_check_mark:                                                            | N/A                                                                           |                                                                               |
| `sha256`                                                                      | *string*                                                                      | :heavy_minus_sign:                                                            | N/A                                                                           |                                                                               |
| `createdAt`                                                                   | *number*                                                                      | :heavy_check_mark:                                                            | Unix timestamp.                                                               | 1738972800                                                                    |