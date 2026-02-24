# ForbiddenErrorError

## Example Usage

```typescript
import { ForbiddenErrorError } from "@sfcompute/sdk/models";

let value: ForbiddenErrorError = {
  type: "forbidden",
  message: "<value>",
};
```

## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `type`                                                         | [models.ForbiddenErrorType](../models/forbidden-error-type.md) | :heavy_check_mark:                                             | N/A                                                            |
| `message`                                                      | *string*                                                       | :heavy_check_mark:                                             | N/A                                                            |
| `details`                                                      | [models.ErrorDetail](../models/error-detail.md)[]              | :heavy_minus_sign:                                             | N/A                                                            |