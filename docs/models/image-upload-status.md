# ImageUploadStatus

## Example Usage

```typescript
import { ImageUploadStatus } from "@sfcompute/sdk/models";

let value: ImageUploadStatus = "failed";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"started" | "uploading" | "completed" | "failed" | Unrecognized<string>
```