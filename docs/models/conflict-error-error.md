# ConflictErrorError

## Example Usage

```typescript
import { ConflictErrorError } from "@sfcompute/sdk/models";

let value: ConflictErrorError = {
  type: "conflict",
  message: "<value>",
};
```

## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `type`                                                       | [models.ConflictErrorType](../models/conflict-error-type.md) | :heavy_check_mark:                                           | N/A                                                          |
| `message`                                                    | *string*                                                     | :heavy_check_mark:                                           | N/A                                                          |
| `details`                                                    | [models.ErrorDetail](../models/error-detail.md)[]            | :heavy_minus_sign:                                           | N/A                                                          |