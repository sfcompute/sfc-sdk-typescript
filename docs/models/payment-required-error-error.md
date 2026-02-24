# PaymentRequiredErrorError

## Example Usage

```typescript
import { PaymentRequiredErrorError } from "@sfcompute/sdk/models";

let value: PaymentRequiredErrorError = {
  type: "payment_required",
  message: "<value>",
};
```

## Fields

| Field                                                                       | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `type`                                                                      | [models.PaymentRequiredErrorType](../models/payment-required-error-type.md) | :heavy_check_mark:                                                          | N/A                                                                         |
| `message`                                                                   | *string*                                                                    | :heavy_check_mark:                                                          | N/A                                                                         |
| `details`                                                                   | [models.ErrorDetail](../models/error-detail.md)[]                           | :heavy_minus_sign:                                                          | N/A                                                                         |