<!-- Start SDK Example Usage [usage] -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.capacities.list({
    startingAfter: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });

  for await (const page of result) {
    console.log(page);
  }
}

run();

```
<!-- End SDK Example Usage [usage] -->