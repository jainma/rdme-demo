---
title: "Employee-based queries"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# Employee-based queries

This topic explains how to create requests for basic employee-based information using the __Retrieve Data__ operation.

Example requests are **POST**ed to the *Retrieve Data* URL:
`https://<<hostName>>.mykronos.com/api/v1/commons/data/multi_read`

*Retrieve Data* operations aggregate data from across the suite using the Data Dictionary data elements defined in the request. Each response provides metadata that allows for caching and paging, which is covered in detail in the [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65) topic. 

* [Prerequisites](#Prerequisites)
* [Example request](#Request)
* [Example response](#Response)
* [Next steps](#NextSteps)
* [Table of Contents](#TableOfContents)

## Prerequisites {#Prerequisites}

Understand the concepts in the following topic:

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)

## Example request {#Request}

In this example, the request:

* retrieves employee names and the names of their supervisors using [Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e) keys
* defines the data view as EMP for employee, which is similar to an Employee Dataview
* selects the set of employees using a Hyperfind query
* establishes a date range for the requested data in the form of a symbolic period

``` json
{
  "select": [
    {
      "key": "EMP_COMMON_FULL_NAME"
    },
    {
      "key": "PEOPLE_MANAGER_NAME"
    }
  ],
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
  }
}
```

__*Notes of interest*__

* Use qualifiers instead of IDs when your object references point to gold data. Gold data consists of queries, Dataviews, reports, and other such entities that are included with your tenant and are not changeable. 
* Refer to the __Resource Details__ of the *Retrieve Data* __POST__ `/v1/commons/data/multi_read` operation for descriptions of each object, array, and property.

## Example response {#Response}

The request defined a set of employees and retrieved their names and the names of their supervisors using the Data Dictionary keys `EMP_COMMON_FULL_NAME` and `PEOPLE_MANAGER_NAME`.

``` json
    {
    "metadata": {
        "lastRefreshed": null,
        "cacheExpirationTime": null,
        "numNodes": "8",
        "metadataKey": "df063aee-17da-4575-a0c4-7c325c183edd",
        "cacheKey": "8b080708-4452-41d0-80bd-5a2644085b9c",
        "totalNodes": "8",
        "totalElements": "8"
    },
    "data": {
        "key": {
            "ROOT": "-1"
        },
        "coreEntityKey": {},
        "attributes": [],
        "children": [
            {
                "key": {
                    "PEOPLE": "208"
                },
                "coreEntityKey": {
                    "EMP": {
                        "id": "208"
                    }
                },
                "attributes": [
                    {
                        "key": "PEOPLE_MANAGER_NAME",
                        "rawValue": "Russel, Beverly",
                        "value": "Russel, Beverly"
                    },
                    {
                        "key": "EMP_COMMON_FULL_NAME",
                        "rawValue": "Leavitt, Caitlin",
                        "value": "Leavitt, Caitlin"
                    }
                ],
                "children": [],
                "summaryListDisplay": [],
                "rootEntity": "PEOPLE",
                "customProperties": {}
            },
            ...
            ]
        }
    }

```

## Next steps {#NextSteps}

Proceed to the [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804) topic.

## Table of Contents {#TableOfContents}

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. YOU ARE HERE
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)
4. [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463)
5. [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33)
6. [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65)