# Capacities

## Overview

A bucket of owned compute balance over time.

### Available Operations

* [list](#list) - List capacities
* [create](#create) - Create capacity
* [get](#get) - Get capacity
* [delete](#delete) - Delete capacity
* [update](#update) - Update capacity

## list

List all capacities.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="list_capacities_handler" method="get" path="/v2/capacities" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { capacitiesList } from "@sfcompute/sdk/funcs/capacities-list.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await capacitiesList(sfc, {
    startingAfter: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("capacitiesList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListCapacitiesHandlerRequest](../../models/operations/list-capacities-handler-request.md)                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiListCapacitiesResponse](../../models/market-api-list-capacities-response.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.MarketApiUnauthorizedError        | 401                                      | application/json                         |
| errors.MarketApiUnprocessableEntityError | 422                                      | application/json                         |
| errors.MarketApiInternalServerError      | 500                                      | application/json                         |
| errors.SfcDefaultError                   | 4XX, 5XX                                 | \*/\*                                    |

## create

Create a capacity to hold compute in specified zones.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="create_capacity_handler" method="post" path="/v2/capacities" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.capacities.create({
    name: "my-resource-name",
    zones: [
      "richmond",
    ],
    nodeTemplate: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
    startNodesAutomatically: false,
    scheduler: {
      desiredQuantity: 618495,
      managedWindowMinutes: 156920,
      minSellPriceDollarsPerNodeHour: "2.500000",
      maxBuyPriceDollarsPerNodeHour: "2.500000",
      enabled: false,
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { capacitiesCreate } from "@sfcompute/sdk/funcs/capacities-create.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await capacitiesCreate(sfc, {
    name: "my-resource-name",
    zones: [
      "richmond",
    ],
    nodeTemplate: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
    startNodesAutomatically: false,
    scheduler: {
      desiredQuantity: 618495,
      managedWindowMinutes: 156920,
      minSellPriceDollarsPerNodeHour: "2.500000",
      maxBuyPriceDollarsPerNodeHour: "2.500000",
      enabled: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("capacitiesCreate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.MarketApiCreateCapacityRequest](../../models/market-api-create-capacity-request.md)                                                                                    | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiCapacityResponse](../../models/market-api-capacity-response.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.MarketApiUnauthorizedError        | 401                                      | application/json                         |
| errors.MarketApiForbiddenError           | 403                                      | application/json                         |
| errors.MarketApiUnprocessableEntityError | 422                                      | application/json                         |
| errors.MarketApiInternalServerError      | 500                                      | application/json                         |
| errors.SfcDefaultError                   | 4XX, 5XX                                 | \*/\*                                    |

## get

Retrieve a capacity by ID or name, including its compute schedule and scheduler configuration.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_capacity_handler" method="get" path="/v2/capacities/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.capacities.get({
    id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { capacitiesGet } from "@sfcompute/sdk/funcs/capacities-get.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await capacitiesGet(sfc, {
    id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("capacitiesGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetCapacityHandlerRequest](../../models/operations/get-capacity-handler-request.md)                                                                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiCapacityResponse](../../models/market-api-capacity-response.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.MarketApiUnauthorizedError   | 401                                 | application/json                    |
| errors.MarketApiNotFoundError       | 404                                 | application/json                    |
| errors.MarketApiInternalServerError | 500                                 | application/json                    |
| errors.SfcDefaultError              | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a capacity. The capacity must be empty and the scheduler must be disabled or absent.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_capacity_handler" method="delete" path="/v2/capacities/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  await sfc.capacities.delete({
    id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { capacitiesDelete } from "@sfcompute/sdk/funcs/capacities-delete.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await capacitiesDelete(sfc, {
    id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("capacitiesDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteCapacityHandlerRequest](../../models/operations/delete-capacity-handler-request.md)                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.MarketApiUnauthorizedError        | 401                                      | application/json                         |
| errors.MarketApiForbiddenError           | 403                                      | application/json                         |
| errors.MarketApiNotFoundError            | 404                                      | application/json                         |
| errors.MarketApiUnprocessableEntityError | 422                                      | application/json                         |
| errors.MarketApiInternalServerError      | 500                                      | application/json                         |
| errors.SfcDefaultError                   | 4XX, 5XX                                 | \*/\*                                    |

## update

Update a capacity. Omitted fields are left unchanged.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="patch_capacity_handler" method="patch" path="/v2/capacities/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.capacities.update({
    id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {
      zones: [
        "richmond",
      ],
      scheduler: {
        desiredQuantity: 177158,
        managedWindowMinutes: 74838,
        minSellPriceDollarsPerNodeHour: "2.500000",
        maxBuyPriceDollarsPerNodeHour: "2.500000",
        enabled: true,
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { capacitiesUpdate } from "@sfcompute/sdk/funcs/capacities-update.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await capacitiesUpdate(sfc, {
    id: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {
      zones: [
        "richmond",
      ],
      scheduler: {
        desiredQuantity: 177158,
        managedWindowMinutes: 74838,
        minSellPriceDollarsPerNodeHour: "2.500000",
        maxBuyPriceDollarsPerNodeHour: "2.500000",
        enabled: true,
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("capacitiesUpdate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PatchCapacityHandlerRequest](../../models/operations/patch-capacity-handler-request.md)                                                                            | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiCapacityResponse](../../models/market-api-capacity-response.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.MarketApiUnauthorizedError        | 401                                      | application/json                         |
| errors.MarketApiForbiddenError           | 403                                      | application/json                         |
| errors.MarketApiNotFoundError            | 404                                      | application/json                         |
| errors.MarketApiUnprocessableEntityError | 422                                      | application/json                         |
| errors.MarketApiInternalServerError      | 500                                      | application/json                         |
| errors.SfcDefaultError                   | 4XX, 5XX                                 | \*/\*                                    |