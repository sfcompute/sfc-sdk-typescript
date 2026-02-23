# VmorchNodeSshInfo

## Example Usage

```typescript
import { VmorchNodeSshInfo } from "@sfcompute/sdk/models";

let value: VmorchNodeSshInfo = {
  hostname: "24.125.89.203",
  port: 22,
  hostKeys: [],
  lastSuccessfulKeyUpdateAt: 1738972800,
  lastAttemptedKeyUpdateAt: 1738972800,
};
```

## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            | Example                                                                |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `hostname`                                                             | *string*                                                               | :heavy_check_mark:                                                     | N/A                                                                    | 24.125.89.203                                                          |
| `port`                                                                 | *number*                                                               | :heavy_check_mark:                                                     | N/A                                                                    | 22                                                                     |
| `hostKeys`                                                             | [models.VmorchNodeSshHostKey](../models/vmorch-node-ssh-host-key.md)[] | :heavy_check_mark:                                                     | N/A                                                                    |                                                                        |
| `lastSuccessfulKeyUpdateAt`                                            | *number*                                                               | :heavy_minus_sign:                                                     | Unix timestamp.                                                        | 1738972800                                                             |
| `lastAttemptedKeyUpdateAt`                                             | *number*                                                               | :heavy_minus_sign:                                                     | Unix timestamp.                                                        | 1738972800                                                             |