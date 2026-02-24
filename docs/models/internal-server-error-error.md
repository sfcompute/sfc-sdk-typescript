# InternalServerErrorError

## Example Usage

```typescript
import { InternalServerErrorError } from "@sfcompute/sdk/models";

let value: InternalServerErrorError = {
  message: "<value>",
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `type`                                            | *"api_error"*                                     | :heavy_minus_sign:                                | N/A                                               |
| `message`                                         | *string*                                          | :heavy_check_mark:                                | N/A                                               |
| `details`                                         | [models.ErrorDetail](../models/error-detail.md)[] | :heavy_minus_sign:                                | N/A                                               |