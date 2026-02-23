# VmorchNodeSshHostKey

## Example Usage

```typescript
import { VmorchNodeSshHostKey } from "@sfcompute/sdk/models";

let value: VmorchNodeSshHostKey = {
  keyType: "ssh-ed25519",
  key: "AAAAC3NzaC1lZDI1NTE5AAAAI...",
};
```

## Fields

| Field                                                 | Type                                                  | Required                                              | Description                                           | Example                                               |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `keyType`                                             | *string*                                              | :heavy_check_mark:                                    | Key algorithm.                                        | **Example 1:** ssh-ed25519<br/>**Example 2:** ssh-rsa |
| `key`                                                 | *string*                                              | :heavy_check_mark:                                    | Base64-encoded public key.                            | AAAAC3NzaC1lZDI1NTE5AAAAI...                          |