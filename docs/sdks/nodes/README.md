# Nodes

## Overview

Spin up nodes in a capacity to use your available compute.

### Available Operations

* [list](#list) - List nodes
* [fetch](#fetch) - Get node
* [getLogsForNode](#getlogsfornode) - Get node logs
* [replace](#replace) - Replace node
* [getSSHInfoForNode](#getsshinfofornode) - Get node SSH info

## list

List all nodes.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="list_nodes" method="get" path="/v2/nodes" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodes.list({
    id: [
      "n",
      "o",
      "d",
      "e",
      "_",
      "k",
      "3",
      "R",
      "-",
      "n",
      "X",
      "9",
      "v",
      "L",
      "m",
      "7",
      "Q",
      "p",
      "2",
      "Y",
      "w",
      "5",
      "J",
      "d",
      "8",
      "F",
    ],
    capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    startingAfter: "nodec_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "nodec_gqXR7s0Kj5mHvE2wNpLc4Q",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodesList } from "@sfcompute/sdk/funcs/nodes-list.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodesList(sfc, {
    id: [
      "n",
      "o",
      "d",
      "e",
      "_",
      "k",
      "3",
      "R",
      "-",
      "n",
      "X",
      "9",
      "v",
      "L",
      "m",
      "7",
      "Q",
      "p",
      "2",
      "Y",
      "w",
      "5",
      "J",
      "d",
      "8",
      "F",
    ],
    capacity: "cap_k3R-nX9vLm7Qp2Yw5Jd8F",
    startingAfter: "nodec_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "nodec_gqXR7s0Kj5mHvE2wNpLc4Q",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodesList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListNodesRequest](../../models/operations/list-nodes-request.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ListNodesResponse](../../models/list-nodes-response.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.NotFoundError            | 404                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.SfcDefaultError          | 4XX, 5XX                        | \*/\*                           |

## fetch

Retrieve a node by ID.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="fetch_node" method="get" path="/v2/nodes/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodes.fetch({
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodesFetch } from "@sfcompute/sdk/funcs/nodes-fetch.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodesFetch(sfc, {
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodesFetch failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.FetchNodeRequest](../../models/operations/fetch-node-request.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.NodeResponse](../../models/node-response.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.UnauthorizedError   | 401                        | application/json           |
| errors.NotFoundError       | 404                        | application/json           |
| errors.InternalServerError | 500                        | application/json           |
| errors.SfcDefaultError     | 4XX, 5XX                   | \*/\*                      |

## getLogsForNode

Retrieve logs for a node.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_node_logs" method="get" path="/v2/nodes/{id}/logs" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodes.getLogsForNode({
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
    realtimeTimestampBefore: 1738972800,
    realtimeTimestampAfter: 1738972800,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodesGetLogsForNode } from "@sfcompute/sdk/funcs/nodes-get-logs-for-node.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodesGetLogsForNode(sfc, {
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
    realtimeTimestampBefore: 1738972800,
    realtimeTimestampAfter: 1738972800,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodesGetLogsForNode failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetNodeLogsRequest](../../models/operations/get-node-logs-request.md)                                                                                              | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.NodeLogsResponse](../../models/node-logs-response.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.NotFoundError            | 404                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.SfcDefaultError          | 4XX, 5XX                        | \*/\*                           |

## replace

Replace a node by destroying it and creating a new one in the same capacity.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="replace_node" method="post" path="/v2/nodes/{id}/replace" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodes.replace({
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {},
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodesReplace } from "@sfcompute/sdk/funcs/nodes-replace.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodesReplace(sfc, {
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodesReplace failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ReplaceNodeRequest](../../models/operations/replace-node-request.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.NodeResponse](../../models/node-response.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.UnauthorizedError   | 401                        | application/json           |
| errors.ForbiddenError      | 403                        | application/json           |
| errors.NotFoundError       | 404                        | application/json           |
| errors.InternalServerError | 500                        | application/json           |
| errors.SfcDefaultError     | 4XX, 5XX                   | \*/\*                      |

## getSSHInfoForNode

Retrieve SSH connection details for a node.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_node_ssh" method="get" path="/v2/nodes/{id}/ssh" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodes.getSSHInfoForNode({
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodesGetSSHInfoForNode } from "@sfcompute/sdk/funcs/nodes-get-ssh-info-for-node.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  bearerAuth: process.env["SFC_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodesGetSSHInfoForNode(sfc, {
    id: "node_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodesGetSSHInfoForNode failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetNodeSshRequest](../../models/operations/get-node-ssh-request.md)                                                                                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.NodeSshInfo](../../models/node-ssh-info.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.UnauthorizedError   | 401                        | application/json           |
| errors.NotFoundError       | 404                        | application/json           |
| errors.InternalServerError | 500                        | application/json           |
| errors.SfcDefaultError     | 4XX, 5XX                   | \*/\*                      |