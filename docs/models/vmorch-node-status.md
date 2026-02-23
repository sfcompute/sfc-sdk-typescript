# VmorchNodeStatus

`pending` on creation while waiting for hardware assignment, `running` once assigned (note: the node may still be booting or loading a custom image), `terminated` when destroyed, `failed` on hardware fault.

## Example Usage

```typescript
import { VmorchNodeStatus } from "@sfcompute/sdk/models";

let value: VmorchNodeStatus = "running";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"pending" | "running" | "terminated" | "failed" | Unrecognized<string>
```