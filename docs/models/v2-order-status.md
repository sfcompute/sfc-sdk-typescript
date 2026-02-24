# V2OrderStatus

`pending` = not resolved/processed yet.

`filled` = order executed.

`standing` = the order is waiting for a match.

`cancelled` = the order was cancelled either automatically (not a standing
order and didn't immediately fill, or current time past `end_at`) or by
explicit cancellation.

`rejected` = validation/system error occurred.

## Example Usage

```typescript
import { V2OrderStatus } from "@sfcompute/sdk/models";

let value: V2OrderStatus = "filled";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"pending" | "filled" | "rejected" | "cancelled" | "standing" | Unrecognized<string>
```