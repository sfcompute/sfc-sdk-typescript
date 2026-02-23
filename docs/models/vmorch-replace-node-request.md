# VmorchReplaceNodeRequest

## Example Usage

```typescript
import { VmorchReplaceNodeRequest } from "@sfcompute/sdk/models";

let value: VmorchReplaceNodeRequest = {};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `nodeTemplate`                                                                                 | *string*                                                                                       | :heavy_minus_sign:                                                                             | Node template for the new node. Falls back to capacity default, then original node's template. |