# Images

## Overview

Custom machine images for nodes.

### Available Operations

* [list](#list) - List images
* [startUpload](#startupload) - Create image
* [get](#get) - Get image
* [completeUpload](#completeupload) - Complete image upload
* [download](#download) - Download image
* [uploadPart](#uploadpart) - Create image upload part URL

## list

List all machine images.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="list_images_v2" method="get" path="/v2/images" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { imagesList } from "@sfcompute/sdk/funcs/images-list.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await imagesList(sfc, {
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    startingAfter: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
    endingBefore: "imagec_gqXR7s0Kj5mHvE2wNpLc4Q",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("imagesList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListImagesV2Request](../../models/operations/list-images-v2-request.md)                                                                                            | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.ListImagesV2Security](../../models/operations/list-images-v2-security.md)                                                                                          | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.VmorchListImagesResponse](../../models/vmorch-list-images-response.md)\>**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| errors.VmorchUnauthorizedError        | 401                                   | application/json                      |
| errors.VmorchUnprocessableEntityError | 422                                   | application/json                      |
| errors.VmorchInternalServerError      | 500                                   | application/json                      |
| errors.SfcDefaultError                | 4XX, 5XX                              | \*/\*                                 |

## startUpload

Create an image and start a multipart upload.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="start_upload" method="post" path="/v2/images" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await sfc.images.startUpload({
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    name: "my-resource-name",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { imagesStartUpload } from "@sfcompute/sdk/funcs/images-start-upload.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await imagesStartUpload(sfc, {
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    name: "my-resource-name",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("imagesStartUpload failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.VmorchStartUploadRequest](../../models/vmorch-start-upload-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.StartUploadSecurity](../../models/operations/start-upload-security.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.VmorchImageResponse](../../models/vmorch-image-response.md)\>**

### Errors

| Error Type                       | Status Code                      | Content Type                     |
| -------------------------------- | -------------------------------- | -------------------------------- |
| errors.VmorchBadRequestError     | 400                              | application/json                 |
| errors.VmorchUnauthorizedError   | 401                              | application/json                 |
| errors.VmorchForbiddenError      | 403                              | application/json                 |
| errors.VmorchConflictError       | 409                              | application/json                 |
| errors.VmorchInternalServerError | 500                              | application/json                 |
| errors.SfcDefaultError           | 4XX, 5XX                         | \*/\*                            |

## get

Retrieve an image by ID.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_image" method="get" path="/v2/images/{id}" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await sfc.images.get({
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { imagesGet } from "@sfcompute/sdk/funcs/images-get.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await imagesGet(sfc, {
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("imagesGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetImageRequest](../../models/operations/get-image-request.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.GetImageSecurity](../../models/operations/get-image-security.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.VmorchImageResponse](../../models/vmorch-image-response.md)\>**

### Errors

| Error Type                       | Status Code                      | Content Type                     |
| -------------------------------- | -------------------------------- | -------------------------------- |
| errors.VmorchUnauthorizedError   | 401                              | application/json                 |
| errors.VmorchNotFoundError       | 404                              | application/json                 |
| errors.VmorchInternalServerError | 500                              | application/json                 |
| errors.SfcDefaultError           | 4XX, 5XX                         | \*/\*                            |

## completeUpload

Complete a multipart image upload after all parts have been uploaded.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="complete_upload" method="post" path="/v2/images/{id}/complete" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await sfc.images.completeUpload({
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {
      sha256: "<value>",
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
import { imagesCompleteUpload } from "@sfcompute/sdk/funcs/images-complete-upload.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await imagesCompleteUpload(sfc, {
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {
      sha256: "<value>",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("imagesCompleteUpload failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CompleteUploadRequest](../../models/operations/complete-upload-request.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.CompleteUploadSecurity](../../models/operations/complete-upload-security.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.VmorchImageResponse](../../models/vmorch-image-response.md)\>**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| errors.VmorchUnauthorizedError        | 401                                   | application/json                      |
| errors.VmorchForbiddenError           | 403                                   | application/json                      |
| errors.VmorchNotFoundError            | 404                                   | application/json                      |
| errors.VmorchUnprocessableEntityError | 422                                   | application/json                      |
| errors.VmorchInternalServerError      | 500                                   | application/json                      |
| errors.SfcDefaultError                | 4XX, 5XX                              | \*/\*                                 |

## download

Get a presigned URL to download an image.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="download_image_v2" method="get" path="/v2/images/{id}/download" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await sfc.images.download({
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SfcCore } from "@sfcompute/sdk/core.js";
import { imagesDownload } from "@sfcompute/sdk/funcs/images-download.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await imagesDownload(sfc, {
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("imagesDownload failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DownloadImageV2Request](../../models/operations/download-image-v2-request.md)                                                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.DownloadImageV2Security](../../models/operations/download-image-v2-security.md)                                                                                    | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.VmorchImageDownloadResponse](../../models/vmorch-image-download-response.md)\>**

### Errors

| Error Type                       | Status Code                      | Content Type                     |
| -------------------------------- | -------------------------------- | -------------------------------- |
| errors.VmorchUnauthorizedError   | 401                              | application/json                 |
| errors.VmorchNotFoundError       | 404                              | application/json                 |
| errors.VmorchConflictError       | 409                              | application/json                 |
| errors.VmorchInternalServerError | 500                              | application/json                 |
| errors.SfcDefaultError           | 4XX, 5XX                         | \*/\*                            |

## uploadPart

Get a presigned URL to upload a part of a multipart image upload.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="upload_part" method="post" path="/v2/images/{id}/parts" -->
```typescript
import { Sfc } from "@sfcompute/sdk";

const sfc = new Sfc({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await sfc.images.uploadPart({
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {
      partId: 417263,
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
import { imagesUploadPart } from "@sfcompute/sdk/funcs/images-upload-part.js";

// Use `SfcCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sfc = new SfcCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await imagesUploadPart(sfc, {
    vmorchBearerAuth: process.env["SFC_VMORCH_BEARER_AUTH"] ?? "",
  }, {
    id: "image_k3R-nX9vLm7Qp2Yw5Jd8F",
    body: {
      partId: 417263,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("imagesUploadPart failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UploadPartRequest](../../models/operations/upload-part-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.UploadPartSecurity](../../models/operations/upload-part-security.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.VmorchUploadPartResponse](../../models/vmorch-upload-part-response.md)\>**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| errors.VmorchUnauthorizedError        | 401                                   | application/json                      |
| errors.VmorchForbiddenError           | 403                                   | application/json                      |
| errors.VmorchNotFoundError            | 404                                   | application/json                      |
| errors.VmorchUnprocessableEntityError | 422                                   | application/json                      |
| errors.VmorchInternalServerError      | 500                                   | application/json                      |
| errors.SfcDefaultError                | 4XX, 5XX                              | \*/\*                                 |