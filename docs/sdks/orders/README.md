# Orders

## Overview

Place orders targeting a capacity to increase your reserved compute balance during some time period.

### Available Operations

* [list](#list) - List orders
* [create](#create) - Create order
* [get](#get) - Get order
* [cancel](#cancel) - Cancel order

## list

List all orders.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="list_orders" method="get" path="/v2/orders" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.orders.list({
    capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    createdAfter: 1738972800,
    createdBefore: 1738972800,
    startingAfter: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });

  for await (const page of result) {
    console.log(page);
  }
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { ordersList } from "@sfcompute/sdk/funcs/orders-list.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await ordersList(sfc, {
    capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    createdAfter: 1738972800,
    createdBefore: 1738972800,
    startingAfter: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "ordrc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });
  if (res.ok) {
    const { value: result } = res;
    for await (const page of result) {
    console.log(page);
  }
  } else {
    console.log("ordersList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListOrdersRequest](../../models/operations/list-orders-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ListOrdersResponse](../../models/operations/list-orders-response.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.SfcDefaultError          | 4XX, 5XX                        | \*/\*                           |

## create

Place a buy or sell order. Orders fill completely or not at all. All nodes fill in a single zone. Order filling is asynchronous; poll `GET /v2/orders/{id}` to check status.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="create_order" method="post" path="/v2/orders" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.orders.create({
    body: {
      capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
      side: "sell",
      nodeCount: 387888,
      startAt: 1738972800,
      endAt: 1738972800,
      limitPriceDollarsPerNodeHour: "2.500000",
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
import { ordersCreate } from "@sfcompute/sdk/funcs/orders-create.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await ordersCreate(sfc, {
    body: {
      capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
      side: "sell",
      nodeCount: 387888,
      startAt: 1738972800,
      endAt: 1738972800,
      limitPriceDollarsPerNodeHour: "2.500000",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ordersCreate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateOrderRequest](../../models/operations/create-order-request.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.V2OrderResponse](../../models/v2-order-response.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.PaymentRequiredError     | 402                             | application/json                |
| errors.ForbiddenError           | 403                             | application/json                |
| errors.NotFoundError            | 404                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.SfcDefaultError          | 4XX, 5XX                        | \*/\*                           |

## get

Retrieve an order by ID.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_order" method="get" path="/v2/orders/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.orders.get({
    id: "ordr_xyz789",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { ordersGet } from "@sfcompute/sdk/funcs/orders-get.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await ordersGet(sfc, {
    id: "ordr_xyz789",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ordersGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetOrderRequest](../../models/operations/get-order-request.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.V2OrderResponse](../../models/v2-order-response.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.UnauthorizedError   | 401                        | application/json           |
| errors.NotFoundError       | 404                        | application/json           |
| errors.InternalServerError | 500                        | application/json           |
| errors.SfcDefaultError     | 4XX, 5XX                   | \*/\*                      |

## cancel

Request cancellation of an order. This is asynchronous — poll `GET /v2/orders/{id}` to confirm the status has changed to cancelled.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="cancel_order" method="delete" path="/v2/orders/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  await sfc.orders.cancel({
    id: "ordr_xyz789",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { ordersCancel } from "@sfcompute/sdk/funcs/orders-cancel.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await ordersCancel(sfc, {
    id: "ordr_xyz789",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("ordersCancel failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CancelOrderRequest](../../models/operations/cancel-order-request.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.NotFoundError            | 404                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.SfcDefaultError          | 4XX, 5XX                        | \*/\*                           |