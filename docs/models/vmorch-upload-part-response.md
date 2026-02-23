# VmorchUploadPartResponse

## Example Usage

```typescript
import { VmorchUploadPartResponse } from "@sfcompute/sdk/models";

let value: VmorchUploadPartResponse = {
  url: "https://murky-cop-out.net",
  expiresAt: 1738972800,
};
```

## Fields

| Field                             | Type                              | Required                          | Description                       | Example                           |
| --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- |
| `url`                             | *string*                          | :heavy_check_mark:                | Presigned URL to upload the part. |                                   |
| `expiresAt`                       | *number*                          | :heavy_check_mark:                | Unix timestamp.                   | 1738972800                        |