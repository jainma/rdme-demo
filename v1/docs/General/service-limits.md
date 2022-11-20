---
title: "Service limits"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb662255dd00016e0b208"
---

# Service limits

Service limits establish sensible, safe constraints on data returned by the API. These limits play an important role in preserving the health of our ecosystem and help ensure all users experience consistently high performance.

Generally, service limits constrain the number of employees and the time range that can be specified in a single request to ensure each request does not exceed reasonable limits. You cannot retrieve more data than the limits specified by these constraints in a single call.

The HTTP status code for service limits is 413. Refer to the [HTTP status codes](C:ab842096-366f-496f-a471-e73ac58b8540) topic for more information about HTTP status codes.

Refer to the [Best practices and tips](C:c32c06e7-365a-4cd4-a836-1845a3d56f41) topic for information about batching requests to stay within service limits.

Service limits are listed at the operation level whenever possible.

The following general service limits are defined by domain:

* [Attendance service limits](#AttendanceServiceLimits)
* [Business Structure service limits](#BusinessStructure)
* [Hyperfind service limits](#HyperfindServiceLimits)
* [Information Access service limits](#IAServiceLimits)
    * [Date-limited example](#DateLimitedRequestExample)
    * [Employee-based example](#EmployeeBasedRequestExample)
    * [Location-based example](#LocationBasedExample)
    * [Data provider example](#DataProviderExample)
* [Leave service limits](#LeaveServiceLimits)
* [People service limits](#PeopleServiceLimits)

## Attendance service limits {#AttendanceServiceLimits}

Attendance request service limits for Actions, Balances, Balance Resets, Balance Adjustments, Discipline Levels, Markers, Events, Perfect Attendance, Perfect Attendance Deductions, Profile Assignments, Execute Rules, and Audit Records are as follows:

* The **Number of Employees** multiplied by the **Number of Days** must be **less than or equal to** 84,000.

Request service limit definition:

```
$employees * $days <= 84,000
```

Example service limit values:

`2000 * 42 <= 84,000`

### Example error response

``` json
{
    "errorCode": "WFP-90001",
    "message": "Service Limits are exceeded for operation on Attendance Events for 2000 employees and 50 days.",
    "details": {
        "limits": [
            {
                "actual": 100000,
                "maximum": 84000
            }
        ]
    }
}
```

Attendance request service limits for Complete Actions, Action Documents, and Balance Expirations are as follows:

* The **Number of Employees** multiplied by the **Number of Days** must be **less than or equal to** 42,000.

Request service limit definition:

```
$employees * $days <= 42,000
```

Example service limit values:

`1000 * 42 <= 42,000`

## Business Structure service limits {#BusinessStructure}

All API operations that return jobs are limited by the Business Structure jobs service limit, which constrains the number of jobs that can be processed in a single request.

* The **Number of Jobs** cannot exceed 5,000.

Response service limit definition:

`$jobs <= 5,000`

## Hyperfind service limits {#HyperfindServiceLimits}

Hyperfind request service limits include days, employees, and locations:

* The **Number of Days** cannot exceed 365. The **Number of Employees** cannot exceed 10,000. The **Number of Locations** cannot exceed 10,000. 

Request service limit definitions and values:

```
$days <= 365
$employees <= 10,000
$locations <= 10,000
```

The Hyperfind response service limit represents the total number of employees included in the response:

* The **Combined Total (count)** returned in the response must be **less than or equal to** 50,000.

Response service limit definition and value:

```
$count <= 50,000
```

> **Note:** In the **Execute Hyperfind Query** (`POST /v1/commons/hyperfind/execute`) operation, the default `threshold` limits the number of returned employees to 3,500. Use the `threshold` property in the request payload to define a higher limit of up to 50,000 employees. The default limit helps ensure performance. Increasing the threshold may decrease performance.

## Information Access service limits {#IAServiceLimits}

Information Access request service limits include days, employees, and locations:

* The **Number of Days** cannot exceed 365. The **Number of Employees** cannot exceed 500. The **Number of Locations** cannot exceed 300. Requests that fall below these thresholds but exceed the service limits of other data providers are limited by the service limits of the called data providers.

If you need to request more data than allowed by the service limits, Information Access requests can be [chunked](#ChunkingRequests). 

Request service limit definitions and values:

```
$days <= 365
$employees <= 500
$locations <= 300
```

* [Date-limited example](#DateLimitedRequestExample)
* [Employee-based example](#EmployeeBasedRequestExample)
* [Location-based example](#LocationBasedExample)
* [Data provider example](#DataProviderExample)
* [Chunking requests](#ChunkingRequests)

### Date-limited example {#DateLimitedRequestExample}

The following example requests and error response illustrate employee-based requests where the **Number of Days** exceeds 365, but the **Number of Employees** does not exceed 500.

* [Example request with employee IDs](#ExampleRequestWithEmployeeIDs)
* [Example request with Hyperfind](#ExampleRequestWithHyperfind)
* [Example error response](#DateLimitedExampleErrorResponse)

#### Example request with employee IDs {#ExampleRequestWithEmployeeIDs}

``` json
{
  "select": [
    {
      "key": "EMP_COMMON_FULL_NAME"
    }
  ],
  "from": {
    "view": 0,
    "employeeSet": {
      "dateRange": { // Exceeds 365 days
        "startDate": "2017-01-01",
        "endDate": "2018-02-01"
      },
      "employees": {
        "ids": [
          "128"
        ]
      }
    }
  }
}
```

#### Example request with Hyperfind {#ExampleRequestWithHyperfind}

``` json
{
  "select": [
    {
      "key": "EMP_COMMON_FULL_NAME"
    }
  ],
  "from": {
    "view": 0,
    "employeeSet": {
      "dateRange": { // Exceeds 365 days
        "startDate": "2017-01-01",
        "endDate": "2018-02-01"
      },
      "hyperfind":{
               "id":"1" // Hyperfind resolves to less than 500 employees
      }
    }
  }
}
```

#### Example error response {#DateLimitedExampleErrorResponse}

The example requests above, one using employee IDs and the other using Hyperfind, both return the same error response when this service limit is reached:

``` json
HTTP status code : 400 (Bad request)
{
  "errorCode": "WCO-112010",
  "message": "Date range passed in request is above the threshold limit of 365 days."
}
```

### Employee-based example {#EmployeeBasedRequestExample}

The following example request and error response illustrate an employee-based request where the **Number of Employees** exceeds 500, but the **Number of Days** does not exceed 365.

* [Example request](#EmployeeExampleRequest)
* [Example error response](#EmployeeExampleResponse)

#### Example request {#EmployeeExampleRequest}

``` json
{
    "select": [
        {
            "key": "EMP_COMMON_FULL_NAME"
        }
    ],
    "from": {
        "view": 0,
        "employeeSet": {
            "dateRange": {
                "startDate": "2017-01-01",
        "endDate": "2017-02-01"
            },
            "hyperfind":{
               "id":"1" // Hyperfind resolves to more than 500 employees
            }
             
        }
    }
}
```

#### Example error response {#EmployeeExampleResponse}

``` json
HTTP status code : 413
{
  "errorCode": "WCO-106194",
  "message": "Number of employees in request (910) exceeds allowed limit (500).",
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

### Location-based example {#LocationBasedExample}

The following example response illustrates the response body returned when the **Number of Locations** exceeds 300.

#### Example error response {#LocationExampleResponse}

``` json
HTTP status code : 413
{
  "errorCode": "WCO-106195",
  "message": "Number of locations in request (310) exceeds allowed limit (300).",
  "details": {
    "limits": [
      {
        "actual": 310,
        "maximum": 300
      }
    ]
  }
}
```

### Data provider example {#DataProviderExample}

The following example request and response illustrate a request where the **Number of Days** is less than 365, the **Number of Employees** is less than 500, and the **Number of Locations** is less than 300, but the data requested exceeds a limit imposed by a data provider serving Information Access.

* [Example request](#DataProviderExampleRequest)
* [Example response](#DataProviderExampleResponse)

#### Example request {#DataProviderExampleRequest}

In this example, the request includes two columns. One is retrieved from the People data provider and the other from the Scheduling data provider. 

``` json
{
  "select": [
    {
      "key": "EMP_COMMON_FULL_NAME" // Data retrieved from People
    },
    {
      "key": "SCH_SHIFT_START_DATE" // Data retrieved from Scheduling
    }
  ],
  "from": {
    "view": 0,
    "employeeSet": {
      "dateRange": {
        "startDate": "2017-01-01",
        "endDate": "2018-01-01"
      },
      "hyperfind": {
        "id": "1"
      }
    }
  }
}
```

#### Example response {#DataProviderExampleResponse}

Since the People data provider does not impose any service limits, the data for the People column is retrieved. However, the data for the Scheduling column is not retrieved, as the request exceeds the [Scheduling service limits](#SchedulingServiceLimits).

``` json
HTTP status code : 200 OK
{
  "metadata": {
    "numNodes": "132",
    "errors": [
      {
        "code": "WFM-COMMON-1234",
        "message": "Failed to retrieve some data from the providers",
        "detail": [
          {
            "dataElement": {
              "key": "SCH_SHIFT_START_DATE"
            },
            "message": "Service Limits are exceeded for operation on Schedule for 132 employees and 365 days."
          }
        ]
      }
    ]
  },
  "data": {}
}
```

## Leave service limits {#LeaveServiceLimits}

Leave request service limits for Leave Cases and Leave Edits are as follows:

* The **Number of Employees** multiplied by the **Number of Days** must be **less than or equal to** 84,000.

Request service limit definition:

```
$employees * $days <= 84,000
```

Example service limit values:

`2000 * 42 <= 84,000`

### Example error response

``` json
{
    "errorCode": "WFP-90001",
    "message": "Service Limits are exceeded for operation on Leave Edits for 2000 employees and 50 days."
}
```

The Leave request service limit for Leave Cases, defined by Leave Case IDs, is as follows:

* The **Number of Leave Cases** cannot exceed 1,000.

Request service limit definition and value:

```
$leaveCases <= 1,000
```

### Example error response

``` json
{
    "errorCode": "WFP-90003",
    "message": "Service Limits are exceeded for operation on Leave Cases. No more than 1000 items are permitted."
}
```

The Leave request service limit for Leave Edits is as follows:

* The **Number of Leave Edits** cannot exceed 1,000.

Request service limit definition and value:

```
$leaveEdits <= 1,000
```

### Example error response

``` json
{
    "errorCode": "WFP-90003",
    "message": "Service Limits are exceeded for operation on Leave Edits. No more than 1000 items are permitted."
}
```

## People service limits {#PeopleServiceLimits}

The People request service limit for all multi_read operations is as follows:

* The **Number of Employees** must be **less than or equal to** 1,000.

Request service limit definition:

```
$employees <= 1,000
```

The People request service limit for all multi_create, multi_delete, multi_update, and multi_upsert operations is as follows:

* The **Number of Employees** must be **less than or equal to** 100.

Request service limit definition:

```
$employees <= 100
```