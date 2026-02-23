# MarketApiListNodeTemplatesResponse

## Example Usage

```typescript
import { MarketApiListNodeTemplatesResponse } from "@sfcompute/sdk/models";

let value: MarketApiListNodeTemplatesResponse = {
  cursor: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
  hasMore: false,
  data: [
    {
      id: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
      name: "my-resource-name",
      image: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
      cloudInitUserDataUsed: true,
      createdAt: 1738972800,
      cloudInitUserData: "IyEvYmluL2Jhc2gKZWNobyBoZWxsbyB3b3JsZAo=",
    },
  ],
};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              | Example                                                                                  |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `object`                                                                                 | *"list"*                                                                                 | :heavy_minus_sign:                                                                       | N/A                                                                                      |                                                                                          |
| `cursor`                                                                                 | *string*                                                                                 | :heavy_minus_sign:                                                                       | N/A                                                                                      | ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q                                                            |
| `hasMore`                                                                                | *boolean*                                                                                | :heavy_check_mark:                                                                       | N/A                                                                                      |                                                                                          |
| `data`                                                                                   | [models.MarketApiNodeTemplateResponse](../models/market-api-node-template-response.md)[] | :heavy_check_mark:                                                                       | N/A                                                                                      |                                                                                          |