# VmorchStartUploadRequest

Start a multipart image upload. Max image size is 128 GiB.

## Example Usage

```typescript
import { VmorchStartUploadRequest } from "@sfcompute/sdk/models";

let value: VmorchStartUploadRequest = {
  name: "my-resource-name",
};
```

## Fields

| Field              | Type               | Required           | Description        | Example            |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
| `name`             | *string*           | :heavy_check_mark: | N/A                | my-resource-name   |