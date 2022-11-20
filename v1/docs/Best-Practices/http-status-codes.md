---
title: "HTTP status codes"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---

# HTTP status codes

The Dimensions API uses a subset of the conventional HTTP response codes to indicate a request's success or failure. 

The HTTP status maps to client errors (4XX) and server errors (5XX) per [IETF standards](https://www.ietf.org/about/standards-process.html). Codes in the 2xx range indicate success, codes in the 4xx range indicate an error that failed due to information provided by the client (for example, a required parameter was omitted, authentication failed, and so on), and codes in the 5xx range indicate an error with the Dimensions servers.

Not all errors fit easily into HTTP status code categories. Always check the error response `message` and `detail` fields for more information.

* [Structure](#Structure)
	* [HTTP status codes](#HTTPStatusCodes)
		* [Success codes](#SuccessCodes)
		* [Error codes](#ErrorCodes)

## Structure {#Structure}

When the API returns an error, it consists of an HTTP status code and a JSON body. 

### HTTP status codes {#HTTPStatusCodes}

#### Success codes {#SuccessCodes}

**Key**

* **{HTTP code}** : {HTTP code message}
	* {semantics}

**Codes**

* **200** : OK
	* A successful call with a response body
	* **Note:** The Dimensions API returns status code **200**, not **201**, for successful create operations
* **202** : Accepted
	* Status of an asynchronous request
* **204** : Success 
	* Success after DELETE or MULTI_DELETE with no response body
* **207** : Partial Success 
	* A partially successful call with a response body; refer to the Partial success section in the [Error handling](C:5337497a-fc55-4f05-95a3-9d0cadee52cd) topic for more information

#### Error codes {#ErrorCodes}

**Key**

* **{HTTP code}** : {HTTP code message}
	* {semantics}

**Codes**

* **400** : Bad request
	* A syntax or validation error in the request, such as:
		* Invalid JSON
		* Invalid parameters, including missing data
		* Referenced data is not available
		* Failed business validation
* **403** : Forbidden
	* Unauthorized; failed Function Access Profile (FAP) or License validation
* **404** : Not Found
	* For `/{id}` paths where the ID is not found; not used for multi_* operations
* **409** : Conflict
	* The operation resulted in an optimistic locking error; refer to the error body for more information
* **413** : Service limit violation; request entity too large
	* Either the request payload is larger than the server is willing or able to process or a service limit has been violated; see the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic for more information on service limits. By default, request payload JSONs are limited to 1 megabyte in size. Some operations allow for a larger request payload. The increased size is documented in the operation's description. For example, see the Import Labor Budgets (POST /v1/forecasting/labor_budget/import) API operation.
* **429** : Throttling violation; rate or daily limit exceeded
	* The request exceeds the load level the server is willing or able to process
* **500** : Server error
	* Internal server error; if this error occurs unexpectedly, it is possible the Dimensions servers are down. Check the Dimensions Trust Site or the Community forums
* **503** : Service unavailable
	* Timeout processing request, exceeded allocated resources, and so on; this should not indicate that Dimensions servers are unavailable
* **504** : Gateway Timeout
	* The request couldn’t be completed due to an internal problem or gateway timeout; this should not indicate that Dimensions servers are unavailable