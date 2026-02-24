# InternalServerErrorError

## Example Usage

```typescript
import { InternalServerErrorError } from "@sfcompute/sdk/models";

let value: InternalServerErrorError = {
  type: "api_error",
  message: "<value>",
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `type`                                                                    | [models.InternalServerErrorType](../models/internal-server-error-type.md) | :heavy_check_mark:                                                        | N/A                                                                       |
| `message`                                                                 | *string*                                                                  | :heavy_check_mark:                                                        | N/A                                                                       |
| `details`                                                                 | [models.ErrorDetail](../models/error-detail.md)[]                         | :heavy_minus_sign:                                                        | N/A                                                                       |