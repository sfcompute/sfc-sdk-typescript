# NodeLogChunk

## Example Usage

```typescript
import { NodeLogChunk } from "@sfcompute/sdk/models";

let value: NodeLogChunk = {
  timestampRealtime: 1738972800,
  timestampMonotonicSecs: 295556,
  timestampMonotonicNanos: 184340,
  seqnum: 501894,
  data: "SGVsbG8gV29ybGQK",
};
```

## Fields

| Field                                        | Type                                         | Required                                     | Description                                  | Example                                      |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `timestampRealtime`                          | *number*                                     | :heavy_check_mark:                           | Unix timestamp.                              | 1738972800                                   |
| `timestampMonotonicSecs`                     | *number*                                     | :heavy_check_mark:                           | Monotonic clock seconds.                     |                                              |
| `timestampMonotonicNanos`                    | *number*                                     | :heavy_check_mark:                           | Nanosecond component of the monotonic clock. |                                              |
| `seqnum`                                     | *number*                                     | :heavy_check_mark:                           | N/A                                          |                                              |
| `data`                                       | *string*                                     | :heavy_check_mark:                           | Base-64 encoded raw console output.          | SGVsbG8gV29ybGQK                             |