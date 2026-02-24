# ImageDownloadResponse

## Example Usage

```typescript
import { ImageDownloadResponse } from "@sfcompute/sdk/models";

let value: ImageDownloadResponse = {
  url: "https://lavish-sideboard.info",
  expiresAt: 1738972800,
  sha256: "e3b0c44298fc1c149af...",
  size: 295165,
};
```

## Fields

| Field                       | Type                        | Required                    | Description                 | Example                     |
| --------------------------- | --------------------------- | --------------------------- | --------------------------- | --------------------------- |
| `url`                       | *string*                    | :heavy_check_mark:          | Presigned download URL.     |                             |
| `expiresAt`                 | *number*                    | :heavy_check_mark:          | Unix timestamp.             | 1738972800                  |
| `sha256`                    | *string*                    | :heavy_check_mark:          | For integrity verification. | e3b0c44298fc1c149af...      |
| `size`                      | *number*                    | :heavy_check_mark:          | Image size in bytes.        |                             |