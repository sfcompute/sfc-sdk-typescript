# NodeTemplates

## Overview

### Available Operations

* [list](#list) - List node templates
* [create](#create) - Create node template
* [get](#get) - Get node template
* [delete](#delete) - Delete node template

## list

List all node templates.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="list_node_templates_handler" method="get" path="/v2/node_templates" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodeTemplates.list({
    startingAfter: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodeTemplatesList } from "@sfcompute/sdk/funcs/node-templates-list.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodeTemplatesList(sfc, {
    startingAfter: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "ntmplc_gqXR7s0Kj5mHvE2wNpLc4Q",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodeTemplatesList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListNodeTemplatesHandlerRequest](../../models/operations/list-node-templates-handler-request.md)                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiListNodeTemplatesResponse](../../models/market-api-list-node-templates-response.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.MarketApiUnauthorizedError        | 401                                      | application/json                         |
| errors.MarketApiUnprocessableEntityError | 422                                      | application/json                         |
| errors.MarketApiInternalServerError      | 500                                      | application/json                         |
| errors.SfcDefaultError                   | 4XX, 5XX                                 | \*/\*                                    |

## create

Create a reusable node configuration.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="create_node_template_handler" method="post" path="/v2/node_templates" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodeTemplates.create({
    name: "my-resource-name",
    image: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
    cloudInitUserData: "IyEvYmluL2Jhc2gKZWNobyBoZWxsbyB3b3JsZAo=",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodeTemplatesCreate } from "@sfcompute/sdk/funcs/node-templates-create.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodeTemplatesCreate(sfc, {
    name: "my-resource-name",
    image: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
    cloudInitUserData: "IyEvYmluL2Jhc2gKZWNobyBoZWxsbyB3b3JsZAo=",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodeTemplatesCreate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.MarketApiCreateNodeTemplateRequest](../../models/market-api-create-node-template-request.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiNodeTemplateResponse](../../models/market-api-node-template-response.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.MarketApiUnauthorizedError        | 401                                      | application/json                         |
| errors.MarketApiForbiddenError           | 403                                      | application/json                         |
| errors.MarketApiUnprocessableEntityError | 422                                      | application/json                         |
| errors.MarketApiInternalServerError      | 500                                      | application/json                         |
| errors.SfcDefaultError                   | 4XX, 5XX                                 | \*/\*                                    |

## get

Retrieve a node template by ID or name.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_node_template_handler" method="get" path="/v2/node_templates/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await sfc.nodeTemplates.get({
    id: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodeTemplatesGet } from "@sfcompute/sdk/funcs/node-templates-get.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodeTemplatesGet(sfc, {
    id: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("nodeTemplatesGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetNodeTemplateHandlerRequest](../../models/operations/get-node-template-handler-request.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.MarketApiNodeTemplateResponse](../../models/market-api-node-template-response.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.MarketApiUnauthorizedError   | 401                                 | application/json                    |
| errors.MarketApiNotFoundError       | 404                                 | application/json                    |
| errors.MarketApiInternalServerError | 500                                 | application/json                    |
| errors.SfcDefaultError              | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a node template. The template must not be in use by any capacity.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_node_template_handler" method="delete" path="/v2/node_templates/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  await sfc.nodeTemplates.delete({
    id: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { nodeTemplatesDelete } from "@sfcompute/sdk/funcs/node-templates-delete.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  const res = await nodeTemplatesDelete(sfc, {
    id: "ntmpl_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("nodeTemplatesDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteNodeTemplateHandlerRequest](../../models/operations/delete-node-template-handler-request.md)                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
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