# VmorchNodeLogChunk

## Example Usage

```typescript
import { VmorchNodeLogChunk } from "@sfcompute/sdk/models";

let value: VmorchNodeLogChunk = {
  timestampRealtime: 1738972800,
  timestampMonotonicSecs: 643160,
  timestampMonotonicNanos: 538024,
  seqnum: 749596,
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