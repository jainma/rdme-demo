---
title: "A Guide to Information Access"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# A Guide to Information Access

The Information Access domain provides programmatic access to data from various sources in a manner similar to the way a database is accessed. The resources within this domain allow ad hoc queries, dynamic definition and execution of data views, and access to a data dictionary.

* [Retrieve Data syntax](#Queries)
* [Hello, world example](#Example)
    * [Example request](#ExampleRequest)
    * [Example response](#ExampleResponse)
* [Table of Contents](#TableOfContents)

## Retrieve Data syntax {#Queries}

*Retrieve Data* requests are executed using a SQL-like syntax encoded in JSON with the following clauses:

* `select` _[Required]_ contains an array of properties that define which data elements to include from the Data Dictionary.
* `from` _[Optional]_ contains properties and objects that define the sources contributing to and span of time constraining the returned data. 
* `where` _[Optional]_ contains an array with an object that defines a list of data elements and applies filters to each element.
* `groupBy` _[Optional]_ contains an array with an object that defines a list of columns for grouping the data elements in the request.
* `sortBy` _[Optional]_ contains an array with an object that defines sorting behavior for each data element in the request.
* `options` _[Optional]_ contains an object with properties that allow you to further customize the query.

## Hello, world example {#Example}

In this example, a Healthcare manager requests data about her Registered Nurse employees. 

The request:

* retrieves the full name, job, organization, and hire date for employees using Data Dictionary keys
* defines the data view as EMP for employee, which is similar to an Employee Dataview
* selects the set of employees using a Hyperfind query
* establishes a date range for the requested data in the form of a symbolic period
* filters the results to include only employees with jobs that start with "RN" (for Registered Nurses)
* limits the response to only the first 100 results

### Example request {#ExampleRequest}

``` json
{
  "select": [
    {"key": "EMP_COMMON_FULL_NAME"},
    {"key": "EMP_COMMON_PRIMARY_JOB"},
    {"key": "EMP_COMMON_PRIMARY_ORG"},
    {"key": "PEOPLE_HIRE_DATE"}],
  "from": {
    "view": "EMP",
    "employeeSet": {
      "hyperfind": {
        "qualifier": "All Home"
      },
      "dateRange": {
         "symbolicPeriod": {
          "qualifier": "Current_Payperiod"
        }
      }
    }
  },
  "where": [
    {
      "key": "EMP_COMMON_PRIMARY_JOB",
      "operator": "STARTS_WITH",
      "values": [
        "RN"
      ]
    }
  ],
  "count": 100
}
```

### Example response {#ExampleResponse}

This example response omits the `metadata` object and displays only the first employee's results. For more information about `metadata`, refer to the [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65) topic.

``` json
{
  "data": {
    "key": {
      "ROOT": "-1"
    },
    "coreEntityKey": {},
    "attributes": [],
    "children": [
      {
        "key": {
          "PEOPLE": "408"
        },
        "coreEntityKey": {
          "EMP": {
            "id": "408"
          }
        },
        "attributes": [
          {
            "key": "EMP_COMMON_PRIMARY_ORG",
            "rawValue": "Organization/Metropolitan Hospital/Clin Op/WMNB/Labor/Nurse",
            "value": "Organization/Metropolitan Hospital/Clin Op/WMNB/Labor/Nurse"
          },
          {
            "key": "PEOPLE_HIRE_DATE",
            "rawValue": "2016-08-14",
            "value": "8/14/2016"
          },
          {
            "key": "EMP_COMMON_FULL_NAME",
            "rawValue": "Williams, Lynne",
            "value": "Williams, Lynne"
          },
          {
            "key": "EMP_COMMON_PRIMARY_JOB",
            "rawValue": "RN",
            "value": "RN"
          }
        ],
        "children": [],
        "summaryListDisplay": [],
        "rootEntity": "PEOPLE",
        "customProperties": {}
      },
      ...
    ],
    "summaryListDisplay": [],
    "rootEntity": "ROOT",
    "customProperties": {}
  }
}
```

## Table of Contents {#TableOfContents}

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)
4. [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463)
5. [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33)
6. [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65)