# UnprocessableEntityErrorError

## Example Usage

```typescript
import { UnprocessableEntityErrorError } from "@sfcompute/sdk/models";

let value: UnprocessableEntityErrorError = {
  type: "unprocessable_entity",
  message: "<value>",
};
```

## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `type`                                                                              | [models.UnprocessableEntityErrorType](../models/unprocessable-entity-error-type.md) | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `message`                                                                           | *string*                                                                            | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `details`                                                                           | [models.ErrorDetail](../models/error-detail.md)[]                                   | :heavy_minus_sign:                                                                  | N/A                                                                                 |