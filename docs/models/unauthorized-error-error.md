# UnauthorizedErrorError

## Example Usage

```typescript
import { UnauthorizedErrorError } from "@sfcompute/sdk/models";

let value: UnauthorizedErrorError = {
  type: "authentication_error",
  message: "<value>",
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `type`                                                               | [models.UnauthorizedErrorType](../models/unauthorized-error-type.md) | :heavy_check_mark:                                                   | N/A                                                                  |
| `message`                                                            | *string*                                                             | :heavy_check_mark:                                                   | N/A                                                                  |
| `details`                                                            | [models.ErrorDetail](../models/error-detail.md)[]                    | :heavy_minus_sign:                                                   | N/A                                                                  |