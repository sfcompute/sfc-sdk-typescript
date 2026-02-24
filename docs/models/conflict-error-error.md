# ConflictErrorError

## Example Usage

```typescript
import { ConflictErrorError } from "@sfcompute/sdk/models";

let value: ConflictErrorError = {
  message: "<value>",
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `type`                                            | *"conflict"*                                      | :heavy_minus_sign:                                | N/A                                               |
| `message`                                         | *string*                                          | :heavy_check_mark:                                | N/A                                               |
| `details`                                         | [models.ErrorDetail](../models/error-detail.md)[] | :heavy_minus_sign:                                | N/A                                               |