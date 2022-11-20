---
title: "Error handling"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---

# Error handling

The Dimensions API uses a subset of the conventional HTTP response codes to indicate a request's success or failure. 

The HTTP status maps to client errors (4XX) and server errors (5XX) per [IETF standards](https://www.ietf.org/about/standards-process.html). Codes in the 4xx range indicate an error that failed due to information provided by the client (for example, a required parameter was omitted, authentication failed, and so on), and codes in the 5xx range indicate an error with the Dimensions servers.

Not all errors fit easily into HTTP status code categories. Always check the error response `message` and `detail` fields for more information.

## Table of Contents

* [Standard errors](#standardError)
* [Partial successes](#partialSuccess)
    * [Basic response structure](#BasicResponseStructure)
    * [Identifying elements](#IdentifyingElements)
        * [Element structure](#ElementStructure)
    * [generatedIds](#generatedIds)
    * [Preexisting unique IDs](#PreexistingUniqueIDs)

## Standard errors {#standardError}

The body of a standard error includes the following fields:

* **code:** a fixed-length code associated with the error
* **message:** a description of the error
* **detail:** an optional JSON object with specific data about the error. This field enables sophisticated error handling, including multiple errors and partial results

For example, the following error is returned with an HTTP status code **413** error:

``` json
{
  "errorCode": "WCO-106194",
  "message": "The number of employees in the request (910) exceeds the allowed limit (500).",
  "details": {
    "limits": [
      {
        "actual": 910,
        "maximum": 500
      }
    ]
  }
}
```

## Partial successes {#partialSuccess}

Partial Success pertains primarily to bulk operations made of multiple individual requests, each of which can fail or succeed.

> **Note:** The Dimensions API partial success standard has evolved over time and now covers additional scenarios that were not covered by the previous standard.

In general, multi_* operations that use a flat array structure for their payload where the top level index can identify each loading entity continue to use the older standard, while operations with other behaviors use the new standard.

The partial success standard described in this topic consists of a response structure, generated IDs, and a set of structures for various types of partial success responses. This updated standard covers a wider variety of API operation structures.

* [Basic response structure](#BasicResponseStructure)
* [Identifying elements](#IdentifyingElements)
    * [Element structure](#ElementStructure)
* [generatedIds](#generatedIds)
* [Preexisting unique IDs](#PreexistingUniqueIDs)

### Basic response structure {#BasicResponseStructure}

Operations resulting in a partial success return an HTTP status code 207 response.

The response body contains:

* An "umbrella" error containing an errorCode, a message, and a details object
* The details object contains both successes and errors, as follows:
    * "results": a list of wrapper objects, each representing either a success or an error. This allows for processing successes and errors in the same order as the inputs
        * "success" normally returns complete models for all of the objects which succeed. However, if the objects are large enough that it becomes a performance concern, the operation may return only an [object reference list](C:3aeac7eb-3330-46ba-8606-ab4d269afc91).
    * "error-offsets": a list of offsets of errors in the results list, which allows for processing the errors quickly without looping through excessive results

**Basic Partial Success Structure**

``` json
{
  "errorCode": "…",
  "message": "Multiple validation errors occurred….",
  "details": {
    "error-offsets": [
      2
    ],
    "results": [
      {
        "success": {
          "id": 101,
          "name": "location1"
        }
      },
      {
        "success": {
          "id": 1010,
          "name": "location10"
        }
      },
      {
        "error": {
          "errorCode": "…",
          "message": "Time out of range:….",
          "details": {
            "errors": [],
            "input": {}
          }
        }
      }
    ]
  }
}
```

### Identifying elements {#IdentifyingElements}

Each element in a partial success error structure can be uniquely identified. Many elements have existing unique IDs, but others do not. To identify those elements for reporting, the system generates a unique, temporary ID.

**Example Error Structure for Generated ID**

```json
{
  "errorCode": "WFM-1234",
  "message": "Invalid Paycode",
  "reportingAttribute": "generatedId",
  "reportingValue": "egdwd-sedws-jbskjsw"
}
```

**Example Error Structure for Preexisting ID**

``` json
{
  "errorCode": "WFM-1234",
  "message": "Invalid Paycode",
  "reportingAttribute": "id",
  "reportingValue": "15998"
}
```

#### Element structure {#ElementStructure}

The error structure follows the following format:

* `"errorCode"`: the WFD error code associated with the error
* `"message"`: the human-readable message associated with the error
* `"reportingAttribute"`: the attribute which uniquely identifies the object containing the error, either a system-generated ID or another unique ID
* `"reportingValue"`: the value of the uniquely identifying attribute

> **Note:** `reportingAttribute` and `reportingValue` are optional for payloads that do not require generated IDs. Operations with flat structures in the request follow the standard error object structure without using these two attributes.

### generatedIds {#generatedIds}

A `generatedId` is a temporary, unique ID included in response bodies when a JSON object cannot be identified using a single attribute of that object.

Each `generatedId` identifies an object for error reporting. Generated IDs allows you to correlate specific errors with JSON objects.

API operations supporting partial success generate IDs for all objects that cannot otherwise be uniquely identified. The value of each generated ID are unique across the entire request body.

Generated IDs are:

* temporary
* only used for processing errors
* not part of success responses
* not stored in the system
* never displayed in the Dimensions UI

### Preexisting unique IDs {#PreexistingUniqueIDs}

The system does not generate an ID for objects that already have associated unique IDs:

``` json
{
  "errorCode": "WFM-12345",
  "message": "Invalid Paycode",
  "reportingAttribute": "id",
  "reportingValue": "5673456"
}
```