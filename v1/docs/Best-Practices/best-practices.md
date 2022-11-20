---
title: "Best practices and tips"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---
 
# Best practices and tips

## Contents

* [Batching](#Batching)
* [Create open shifts](#CreateOpenShifts)
* [Default request payload size limit](#DefaultPayloadLimit)
* [Error handling](#ErrorHandling)
* [HTTP status codes](#HTTPStatusCodes)
* [HTTP headers](#HTTPHeaders)
* [Integers](#Integers)
* [Object references](#ObjectReferences)
    * [Object reference lists](#ObjectReferenceLists)
* [Service limits](#ServiceLimits)
* [Timeouts](#Timeouts)
* [Transfer strings](#TransferStrings)

## Batching {#Batching}

*Best Practice:*

> To minimize response times for sustained batch operations, use 4 threads with 25 employees per batch in each thread.

This approach offers the best performance for bulk API operations. If you increase the number of employees in each batch, response times will increase.

Batching allows you to perform sustained operations to process large numbers of employees without exceeding [service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5). These limits play an important role in preserving the health of our ecosystem and help ensure all users experience consistently high performance. 

## Create open shifts {#CreateOpenShifts}

*Tip:*

Use the Update Schedule for Multiple Employees (POST /v1/scheduling/schedule/multi_update) API operation to create multiple open shifts in a single request. In the request payload, omit the `employee` property from `shifts` to create an open shift:

``` json
[
  {
    "shifts": {
      "create": [
        {
          "startDateTime": "2021-01-15T08:00:00",
          "endDateTime": "2021-01-15T16:00:00",
          "label": "Morning",
          "segments": [
            {
              "startDateTime": "2021-01-15T08:00:00",
              "endDateTime": "2021-01-15T16:00:00",
              "type": "REGULAR_SEGMENT",
              "orgJobRef": {
                "qualifier": "Organization/United States/Metropolitan Plant/Administration/Manufacturing Manager"
              }
            }
          ]
        },
        {
          "startDateTime": "2021-01-16T08:00:00",
          "endDateTime": "2021-01-16T16:00:00",
          "label": "Morning",
          "segments": [
            {
              "startDateTime": "2021-01-16T08:00:00",
              "endDateTime": "2021-01-16T16:00:00",
              "type": "REGULAR_SEGMENT",
              "orgJobRef": {
                "qualifier": "Organization/United States/Metropolitan Plant/Administration/Manufacturing Manager"
              }
            }
          ]
        }
      ]
    }
  }
]
```

## Error handling {#ErrorHandling}

*Tip:*

> Implement error handling in a way that utilizes the information provided by the standard and partial success error response bodies. 

Error and partial success responses conform to standards that allow you to interpret what went wrong and, often, provide a path for resubmitting the request correctly.

The body of a standard error includes the following fields:

* **code:** a fixed-length code associated with the error
* **message:** a description of the error
* **detail:** an optional JSON object with specific data about the error. This field enables sophisticated error handling, including multiple errors and partial results

Partial Success pertains primarily to bulk operations made of multiple individual requests, each of which can fail or succeed.

Refer to the [Error handling](C:5337497a-fc55-4f05-95a3-9d0cadee52cd) topic for more information.

## HTTP status codes {#HTTPStatusCodes}

*Tip:*

> Implement handling for the particular HTTP status codes used in the Dimensions API.

The Dimensions API uses a subset of the conventional HTTP response codes to indicate a request's success or failure. 

The HTTP status maps to client errors (4XX) and server errors (5XX) per [IETF standards](https://www.ietf.org/about/standards-process.html). Codes in the 2xx range indicate success, codes in the 4xx range indicate an error that failed due to information provided by the client (for example, a required parameter was omitted, authentication failed, and so on), and codes in the 5xx range indicate an error with the Dimensions servers.

Refer to the [HTTP status codes](C:ab842096-366f-496f-a471-e73ac58b8540) topic for more information.

## HTTP headers {#HTTPHeaders}

Our API supports a variety of [HTTP headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields).

Refer to the [HTTP headers](C:4dc8ebe0-067a-4a90-b82d-6f4692bdd534) topic for more information.

## Integers {#Integers}

You must provide integers for request properties with the `integer` data type. If you provide floating point numbers then the fractional portion of the number is silently discarded and only the integer is submitted.

## Object references {#ObjectReferences}

*Tip:*

> Use the standard object reference and object reference list formats to encapsulate references to objects in requests.

Object references contain one or at the most two keys identifying the referenced object. This format helps ensure solid API composition, which allows the output of one operation to serve as part or all of the input for another operation without any further processing. 

The JSON structure for object reference keys takes the following forms:

* `{"id": "…"}` 
* `{"qualifier": "…"}`
* `{"id": "…", "qualifier": "…"}`

When both keys are present, `id` takes precedence over `qualifier`. If both keys are present and `id` is invalid, an error is thrown.

Refer to the [Object references](C:3aeac7eb-3330-46ba-8606-ab4d269afc91) topic for more information.

### Object reference lists {#ObjectReferenceLists}

Object reference lists are composed of one of three parts: a list of `ids`, a list of `qualifiers`, or a list of object references (`refs`), each serving as a list of object reference keys.

In the following example, the "employees" key's `ids`, `qualifiers`, and `refs` are mutually exclusive. The key for an object reference list uses the plural name of a resource. Note that the key name does not include the "Ref" suffix. The key name in the example below is `employees`.

``` json
"employees": {
         "ids": […],
         "qualifiers": […],
         "refs":  [
              { "id": "",
                "qualifier": "…"},
               {"id": "…",
               "qualifier": "…"}
         ]
     }
```

Refer to the [Object references](C:3aeac7eb-3330-46ba-8606-ab4d269afc91) topic for more information.

## Service limits {#ServiceLimits}

*Best practice:*

> Use [batching](#Batching) to remain within service limits.

Service limits establish sensible, safe constraints on data returned by the API. These limits play an important role in preserving the health of our ecosystem and help ensure all users experience consistently high performance.

Generally, service limits constrain the number of employees and the time range that can be specified in a single request to ensure each request does not exceed reasonable limits. You cannot retrieve more data than the limits specified by these constraints in a single call.

The HTTP status code for service limits is 413.

Refer to the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic for more information.

## Timeouts {#Timeouts}

*Best Practice:*

> Set a client-side timeout of 5 minutes or longer.

Setting a timeout on the client side is important for ensuring your system's stability, but do not set a client timeout to a lower value than the Dimension API's default timeout of 5 minutes. Undesirable behavior can occur if your client times out and retries a call before a successful API call finishes executing, which can (in extreme cases) take as long as 5 minutes.

## Transfer strings {#TransferStrings}

*Tip:*

> Use the standard transfer string format whenever you need to pass a transfer string using the Dimensions API.

Transfer strings consist of an ordered, semi-colon separated list of transfer types, including business structure, work rule, cost center, and labor categories. Each transfer type is separated by a semicolon, and the transfer string ends with a semicolon. There can be 0 to 6 labor categories, each separated by commas.

For example:

```
Business Structure;Work Rule;Cost Center;Labor Category1,2,...,6;
```

Refer to the [Transfer strings](C:bb238c15-a8dc-41d7-be61-03487052f81e) topic for more information.

## Default request payload size limit {#DefaultPayloadLimit}

*Tip:*

> By default, request payload JSONs are limited to 1 megabyte in size. Some operations allow for a larger request payload. The increased size is documented in the operation's description. For example, see the Import Labor Budgets (POST /v1/forecasting/labor_budget/import) API operation.