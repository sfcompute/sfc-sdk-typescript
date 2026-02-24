# Side

## Example Usage

```typescript
import { Side } from "@sfcompute/sdk/models";

let value: Side = "buy";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"sell" | "buy" | Unrecognized<string>
```