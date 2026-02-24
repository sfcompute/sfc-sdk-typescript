# NotFoundErrorError

## Example Usage

```typescript
import { NotFoundErrorError } from "@sfcompute/sdk/models";

let value: NotFoundErrorError = {
  type: "not_found",
  message: "<value>",
};
```

## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `type`                                                        | [models.NotFoundErrorType](../models/not-found-error-type.md) | :heavy_check_mark:                                            | N/A                                                           |
| `message`                                                     | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `details`                                                     | [models.ErrorDetail](../models/error-detail.md)[]             | :heavy_minus_sign:                                            | N/A                                                           |