# ReplaceNodeRequest

## Example Usage

```typescript
import { ReplaceNodeRequest } from "@sfcompute/sdk/models";

let value: ReplaceNodeRequest = {};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `nodeTemplate`                                                                                 | *string*                                                                                       | :heavy_minus_sign:                                                                             | Node template for the new node. Falls back to capacity default, then original node's template. |