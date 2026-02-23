<!-- Start SDK Example Usage [usage] -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.capacities.list({
    startingAfter: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->