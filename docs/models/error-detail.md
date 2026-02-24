# ErrorDetail

## Example Usage

```typescript
import { ErrorDetail } from "@sfcompute/sdk/models";

let value: ErrorDetail = {
  code: "<value>",
  message: "<value>",
};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `field`                                                 | *string*                                                | :heavy_minus_sign:                                      | The field that caused the error (for validation errors) |
| `code`                                                  | *string*                                                | :heavy_check_mark:                                      | Specific error code for this detail                     |
| `message`                                               | *string*                                                | :heavy_check_mark:                                      | Human-readable error message                            |