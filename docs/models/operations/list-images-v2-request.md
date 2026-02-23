# ListImagesV2Request

## Example Usage

```typescript
import { ListImagesV2Request } from "@sfcompute/sdk/models/operations";

let value: ListImagesV2Request = {
  startingAfter: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
  endingBefore: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                | Example                                                    |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `limit`                                                    | *number*                                                   | :heavy_minus_sign:                                         | N/A                                                        |                                                            |
| `startingAfter`                                            | *string*                                                   | :heavy_minus_sign:                                         | Set to the response's `cursor` to fetch the next page.     | imagec_gqXR7s0Kj5mHvE2wNpLc4Q                              |
| `endingBefore`                                             | *string*                                                   | :heavy_minus_sign:                                         | Set to the response's `cursor` to fetch the previous page. | imagec_gqXR7s0Kj5mHvE2wNpLc4Q                              |