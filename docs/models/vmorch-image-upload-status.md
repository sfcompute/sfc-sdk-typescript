# VmorchImageUploadStatus

Multipart upload status. `started` on creation, `uploading` after first part URL requested, `completed` when finalized, or `failed` on size/checksum/storage error.

## Example Usage

```typescript
import { VmorchImageUploadStatus } from "@sfcompute/sdk/models";

let value: VmorchImageUploadStatus = "completed";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"started" | "uploading" | "completed" | "failed" | Unrecognized<string>
```