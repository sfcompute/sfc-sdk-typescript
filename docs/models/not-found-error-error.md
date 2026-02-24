# NotFoundErrorError

## Example Usage

```typescript
import { NotFoundErrorError } from "@sfcompute/sdk/models";

let value: NotFoundErrorError = {
  message: "<value>",
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `type`                                            | *"not_found"*                                     | :heavy_minus_sign:                                | N/A                                               |
| `message`                                         | *string*                                          | :heavy_check_mark:                                | N/A                                               |
| `details`                                         | [models.ErrorDetail](../models/error-detail.md)[] | :heavy_minus_sign:                                | N/A                                               |