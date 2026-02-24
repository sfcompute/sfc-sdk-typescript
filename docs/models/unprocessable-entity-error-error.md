# UnprocessableEntityErrorError

## Example Usage

```typescript
import { UnprocessableEntityErrorError } from "@sfcompute/sdk/models";

let value: UnprocessableEntityErrorError = {
  message: "<value>",
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `type`                                            | *"unprocessable_entity"*                          | :heavy_minus_sign:                                | N/A                                               |
| `message`                                         | *string*                                          | :heavy_check_mark:                                | N/A                                               |
| `details`                                         | [models.ErrorDetail](../models/error-detail.md)[] | :heavy_minus_sign:                                | N/A                                               |