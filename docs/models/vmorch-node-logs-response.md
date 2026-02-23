# VmorchNodeLogsResponse

## Example Usage

```typescript
import { VmorchNodeLogsResponse } from "@sfcompute/sdk/models";

let value: VmorchNodeLogsResponse = {
  data: [
    {
      timestampRealtime: 1738972800,
      timestampMonotonicSecs: 489574,
      timestampMonotonicNanos: 121551,
      seqnum: 110700,
      data: "SGVsbG8gV29ybGQK",
    },
  ],
};
```

## Fields

| Field                                                             | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `object`                                                          | *"list"*                                                          | :heavy_minus_sign:                                                | N/A                                                               |
| `data`                                                            | [models.VmorchNodeLogChunk](../models/vmorch-node-log-chunk.md)[] | :heavy_check_mark:                                                | N/A                                                               |