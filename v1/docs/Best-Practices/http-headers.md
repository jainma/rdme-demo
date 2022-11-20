---
title: "HTTP headers"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---

# HTTP headers

Our API supports a variety of [HTTP headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields).

**Key**

* {header name} (Request/Response)
	* {comment}

**Headers**

* `Accept` (Request)
    * By default, do not pass this header; text/csv can be passed only in supported API operations
* `Authorization` (Request)
    * Authentication and authorization data
* `Appkey` (Request)
    * Generated application key unique to each of your applications
* `api-version` (Request)
    * Major.minor: 1.0
* `kronos-tid` (Response)
    * UUID for tracking requests
* `Content-Type` (Request)
    * application/json or text/csv (for supported API operations)
* `Content-Location` (Response)
    * URI representing the current status of an asynchronous request
* `next-ping` (Response)
    * Retry in seconds for an asynchronous request
* `Retry-After` (Response)
    * Retry in seconds after status 429 or 503; if not present with 503, do not automatically retry
* `WWW-Authenticate` (Response)
    * For 401 (Unauthorized) responses
* `X-Currency` (Request/Response)
    * Standard currency codes