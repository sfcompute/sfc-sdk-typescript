# VmorchUnauthorizedErrorError

## Example Usage

```typescript
import { VmorchUnauthorizedErrorError } from "@sfcompute/sdk/models";

let value: VmorchUnauthorizedErrorError = {
  message: "<value>",
};
```

## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `type`                                                         | *"authentication_error"*                                       | :heavy_minus_sign:                                             | N/A                                                            |
| `message`                                                      | *string*                                                       | :heavy_check_mark:                                             | N/A                                                            |
| `details`                                                      | [models.VmorchErrorDetail](../models/vmorch-error-detail.md)[] | :heavy_minus_sign:                                             | N/A                                                            |