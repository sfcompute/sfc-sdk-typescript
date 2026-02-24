# BadRequestErrorError

## Example Usage

```typescript
import { BadRequestErrorError } from "@sfcompute/sdk/models";

let value: BadRequestErrorError = {
  type: "invalid_request_error",
  message: "<value>",
};
```

## Fields

| Field                                                             | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `type`                                                            | [models.BadRequestErrorType](../models/bad-request-error-type.md) | :heavy_check_mark:                                                | N/A                                                               |
| `message`                                                         | *string*                                                          | :heavy_check_mark:                                                | N/A                                                               |
| `details`                                                         | [models.ErrorDetail](../models/error-detail.md)[]                 | :heavy_minus_sign:                                                | N/A                                                               |