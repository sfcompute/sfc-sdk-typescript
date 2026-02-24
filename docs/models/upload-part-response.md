# UploadPartResponse

## Example Usage

```typescript
import { UploadPartResponse } from "@sfcompute/sdk/models";

let value: UploadPartResponse = {
  url: "https://self-reliant-hawk.info/",
  expiresAt: 1738972800,
};
```

## Fields

| Field                             | Type                              | Required                          | Description                       | Example                           |
| --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- |
| `url`                             | *string*                          | :heavy_check_mark:                | Presigned URL to upload the part. |                                   |
| `expiresAt`                       | *number*                          | :heavy_check_mark:                | Unix timestamp.                   | 1738972800                        |