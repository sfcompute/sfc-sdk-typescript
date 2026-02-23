# VmorchCompleteUploadRequest

Complete a multipart image upload.

## Example Usage

```typescript
import { VmorchCompleteUploadRequest } from "@sfcompute/sdk/models";

let value: VmorchCompleteUploadRequest = {
  sha256: "<value>",
};
```

## Fields

| Field                                                              | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `sha256`                                                           | *string*                                                           | :heavy_check_mark:                                                 | Not verified on upload; used during node boot to verify integrity. |