# @sfcompute/sdk

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *@sfcompute/sdk* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=@sfcompute/sdk&utm_campaign=typescript)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/the-san-francisco-compute-company/v2). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary


<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [@sfcompute/sdk](#sfcomputesdk)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!TIP]
> To finish publishing your SDK to npm and others you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).


The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add <UNSET>
```

### PNPM

```bash
pnpm add <UNSET>
```

### Bun

```bash
bun add <UNSET>
```

### Yarn

```bash
yarn add <UNSET>
```

> [!NOTE]
> This package is published with CommonJS and ES Modules (ESM) support.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

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

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name                  | Type | Scheme      | Environment Variable         |
| --------------------- | ---- | ----------- | ---------------------------- |
| `marketApiBearerAuth` | http | HTTP Bearer | `SFC_MARKET_API_BEARER_AUTH` |

To authenticate with the API the `marketApiBearerAuth` parameter must be set when initializing the SDK client instance. For example:
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

### Per-Operation Security Schemes

Some operations in this SDK require the security scheme to be specified at the request level. For example:
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await sfc.images.list({
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    startingAfter: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
  });

  console.log(result);
}

run();

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Capacities](docs/sdks/capacities/README.md)

* [list](docs/sdks/capacities/README.md#list) - List capacities
* [create](docs/sdks/capacities/README.md#create) - Create capacity
* [get](docs/sdks/capacities/README.md#get) - Get capacity
* [delete](docs/sdks/capacities/README.md#delete) - Delete capacity
* [update](docs/sdks/capacities/README.md#update) - Update capacity

### [Images](docs/sdks/images/README.md)

* [list](docs/sdks/images/README.md#list) - List images
* [startUpload](docs/sdks/images/README.md#startupload) - Create image
* [get](docs/sdks/images/README.md#get) - Get image
* [completeUpload](docs/sdks/images/README.md#completeupload) - Complete image upload
* [download](docs/sdks/images/README.md#download) - Download image
* [uploadPart](docs/sdks/images/README.md#uploadpart) - Create image upload part URL

### [Nodes](docs/sdks/nodes/README.md)

* [list](docs/sdks/nodes/README.md#list) - List nodes
* [get](docs/sdks/nodes/README.md#get) - Get node
* [getLogs](docs/sdks/nodes/README.md#getlogs) - Get node logs
* [replace](docs/sdks/nodes/README.md#replace) - Replace node
* [getSsh](docs/sdks/nodes/README.md#getssh) - Get node SSH info

### [NodeTemplates](docs/sdks/nodetemplates/README.md)

* [list](docs/sdks/nodetemplates/README.md#list) - List node templates
* [create](docs/sdks/nodetemplates/README.md#create) - Create node template
* [get](docs/sdks/nodetemplates/README.md#get) - Get node template
* [delete](docs/sdks/nodetemplates/README.md#delete) - Delete node template

### [Orders](docs/sdks/orders/README.md)

* [list](docs/sdks/orders/README.md#list) - List orders
* [create](docs/sdks/orders/README.md#create) - Create order
* [get](docs/sdks/orders/README.md#get) - Get order
* [cancel](docs/sdks/orders/README.md#cancel) - Cancel order

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`capacitiesCreate`](docs/sdks/capacities/README.md#create) - Create capacity
- [`capacitiesDelete`](docs/sdks/capacities/README.md#delete) - Delete capacity
- [`capacitiesGet`](docs/sdks/capacities/README.md#get) - Get capacity
- [`capacitiesList`](docs/sdks/capacities/README.md#list) - List capacities
- [`capacitiesUpdate`](docs/sdks/capacities/README.md#update) - Update capacity
- [`imagesCompleteUpload`](docs/sdks/images/README.md#completeupload) - Complete image upload
- [`imagesDownload`](docs/sdks/images/README.md#download) - Download image
- [`imagesGet`](docs/sdks/images/README.md#get) - Get image
- [`imagesList`](docs/sdks/images/README.md#list) - List images
- [`imagesStartUpload`](docs/sdks/images/README.md#startupload) - Create image
- [`imagesUploadPart`](docs/sdks/images/README.md#uploadpart) - Create image upload part URL
- [`nodesGet`](docs/sdks/nodes/README.md#get) - Get node
- [`nodesGetLogs`](docs/sdks/nodes/README.md#getlogs) - Get node logs
- [`nodesGetSsh`](docs/sdks/nodes/README.md#getssh) - Get node SSH info
- [`nodesList`](docs/sdks/nodes/README.md#list) - List nodes
- [`nodesReplace`](docs/sdks/nodes/README.md#replace) - Replace node
- [`nodeTemplatesCreate`](docs/sdks/nodetemplates/README.md#create) - Create node template
- [`nodeTemplatesDelete`](docs/sdks/nodetemplates/README.md#delete) - Delete node template
- [`nodeTemplatesGet`](docs/sdks/nodetemplates/README.md#get) - Get node template
- [`nodeTemplatesList`](docs/sdks/nodetemplates/README.md#list) - List node templates
- [`ordersCancel`](docs/sdks/orders/README.md#cancel) - Cancel order
- [`ordersCreate`](docs/sdks/orders/README.md#create) - Create order
- [`ordersGet`](docs/sdks/orders/README.md#get) - Get order
- [`ordersList`](docs/sdks/orders/README.md#list) - List orders

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
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
  }, {
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
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
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`SfcError`](./src/models/errors/sfc-error.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                                                             |
| ------------------- | ---------- | --------------------------------------------------------------------------------------- |
| `error.message`     | `string`   | Error message                                                                           |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                                                      |
| `error.headers`     | `Headers`  | HTTP response headers                                                                   |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned.                                  |
| `error.rawResponse` | `Response` | Raw HTTP response                                                                       |
| `error.data$`       |            | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```typescript
import { Sfc } from "@sfcompute/sdk";
import * as errors from "@sfcompute/sdk/models/errors";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
  marketApiBearerAuth: process.env["SFC_MARKET_API_BEARER_AUTH"] ?? "",
});

async function run() {
  try {
    const result = await sfc.capacities.list({
      startingAfter: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
      endingBefore: "capc_gqXR7s0Kj5mHvE2wNpLc4Q",
    });

    console.log(result);
  } catch (error) {
    // The base class for HTTP error responses
    if (error instanceof errors.SfcError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);

      // Depending on the method different errors may be thrown
      if (error instanceof errors.MarketApiUnauthorizedError) {
        console.log(error.data$.error); // models.MarketApiUnauthorizedErrorError
      }
    }
  }
}

run();

```

### Error Classes
**Primary error:**
* [`SfcError`](./src/models/errors/sfc-error.ts): The base class for HTTP error responses.

<details><summary>Less common errors (19)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/http-client-errors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/http-client-errors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/http-client-errors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/http-client-errors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/http-client-errors.ts): Unrecognised or unexpected error.


**Inherit from [`SfcError`](./src/models/errors/sfc-error.ts)**:
* [`MarketApiUnauthorizedError`](./src/models/errors/market-api-unauthorized-error.ts): Unauthorized. Status code `401`. Applicable to 13 of 24 methods.*
* [`MarketApiInternalServerError`](./src/models/errors/market-api-internal-server-error.ts): Internal server error. Status code `500`. Applicable to 13 of 24 methods.*
* [`VmorchUnauthorizedError`](./src/models/errors/vmorch-unauthorized-error.ts): Unauthorized. Status code `401`. Applicable to 11 of 24 methods.*
* [`VmorchInternalServerError`](./src/models/errors/vmorch-internal-server-error.ts): Internal server error. Status code `500`. Applicable to 11 of 24 methods.*
* [`MarketApiUnprocessableEntityError`](./src/models/errors/market-api-unprocessable-entity-error.ts): Status code `422`. Applicable to 10 of 24 methods.*
* [`VmorchNotFoundError`](./src/models/errors/vmorch-not-found-error.ts): Status code `404`. Applicable to 9 of 24 methods.*
* [`MarketApiNotFoundError`](./src/models/errors/market-api-not-found-error.ts): Status code `404`. Applicable to 8 of 24 methods.*
* [`MarketApiForbiddenError`](./src/models/errors/market-api-forbidden-error.ts): Status code `403`. Applicable to 6 of 24 methods.*
* [`VmorchUnprocessableEntityError`](./src/models/errors/vmorch-unprocessable-entity-error.ts): Validation failed. Status code `422`. Applicable to 5 of 24 methods.*
* [`VmorchForbiddenError`](./src/models/errors/vmorch-forbidden-error.ts): Status code `403`. Applicable to 4 of 24 methods.*
* [`VmorchConflictError`](./src/models/errors/vmorch-conflict-error.ts): Status code `409`. Applicable to 2 of 24 methods.*
* [`VmorchBadRequestError`](./src/models/errors/vmorch-bad-request-error.ts): Validation failed. Status code `400`. Applicable to 1 of 24 methods.*
* [`MarketApiPaymentRequiredError`](./src/models/errors/market-api-payment-required-error.ts): Insufficient balance. Status code `402`. Applicable to 1 of 24 methods.*
* [`ResponseValidationError`](./src/models/errors/response-validation-error.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>

\* Check [the method documentation](#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to:
- route requests through a proxy server using [undici](https://www.npmjs.com/package/undici)'s ProxyAgent
- use the `"beforeRequest"` hook to add a custom header and a timeout to requests
- use the `"requestError"` hook to log errors

```typescript
import { Sfc } from "@sfcompute/sdk";
import { ProxyAgent } from "undici";
import { HTTPClient } from "@sfcompute/sdk/lib/http";

const dispatcher = new ProxyAgent("http://proxy.example.com:8080");

const httpClient = new HTTPClient({
  // 'fetcher' takes a function that has the same signature as native 'fetch'.
  fetcher: (input, init) =>
    // 'dispatcher' is specific to undici and not part of the standard Fetch API.
    fetch(input, { ...init, dispatcher } as RequestInit),
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new Sfc({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { Sfc } from "@sfcompute/sdk";

const sdk = new Sfc({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `SFC_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=@sfcompute/sdk&utm_campaign=typescript)
