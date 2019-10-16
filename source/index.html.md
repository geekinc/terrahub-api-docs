---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='https://d375khndt1sbak.cloudfront.net/'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Terrahub Sync API! You can use our API to access API endpoints, which can get information on various individuals, organizations and assets in our Sync system.

We have language bindings in Shell and JavaScript. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

Authorization is handled using an authentication exchange with a token response

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: <authentication_token>"
```

```javascript
const sync = require('sync');

let api = sync.authorize('<authentication_token>');
```

> Make sure to replace `<authentication_token>` with your API key.

Sync uses API keys to allow access to the API. You can register a new Sync API key at our [developer portal](https://d375khndt1sbak.cloudfront.net/).

Sync expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: <authentication_token>`

<aside class="notice">
You must replace <code>&lt;authentication_token&gt;</code> with your personal API key.
</aside>

# Certificates

## Get a Specific Certificate

```shell
curl "https://api.terrahub-apps.com/certificates/certificates/<certificate_id>"
  -H "Authorization: <authentication_token>"
```

```javascript
const sync = require('sync');

let api = sync.authorize('<authentication_token>');
let max = api.certificates.get('<certificate_id>');
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific certificate.

### HTTP Request

`GET https://api.terrahub-apps.com/certificates/certificates/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the certificate to retrieve
