---
title: "Location-based queries"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# Location-based queries

This topic explains how to create requests for basic location-based information using the __Retrieve Data__ operation.

Example requests are **POST**ed to the *Retrieve Data* URL:
`https://<<hostName>>.mykronos.com/api/v1/commons/data/multi_read`

*Retrieve Data* operations aggregate data from across the suite using the Data Dictionary data elements defined in the request. Each response provides metadata that allows for caching and paging, which is covered in detail in the [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65) topic.

* [Prerequisites](#Prerequisites)
* [Example request](#Request)
* [Example response](#Response)
* [Next steps](#NextSteps)
* [Table of Contents](#TableOfContents)

## Prerequisites {#Prerequisites}

Understand the concepts covered in the following topics:

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e) 

## Example request {#Request}

In this location-based example, the request:

* selects location names and addresses from `parameterized` data elements using [Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e) keys and properties
* defines the data view as ORGANIZATION, which is similar to a Business Structure Dataview
* specifies a set of locations using location IDs
* establishes a date range for the requested data in the form of start and end dates and times

``` json
{
  "select": [
    {
      "key": "LOCATION_NAME",
      "properties": [
        {
          "key": "15"
        }
      ]
    },
    {
      "key": "LOCATION_ADDRESS",
      "properties": [
        {
          "key": "15"
        }
      ]
    }
  ],
  "from": {
    "view": "ORGANIZATION",
    "locationSet": {
      "locations": {
        "qualifiers": [
          "Organization/United States/Metropolitan Plant/Machine Shop/Machine Shop 256"
        ]
      },
      "dateRange": {
        "startDate": "2019-01-01T00:00:00.000",
        "endDate": "2019-01-09T00:00:00.000"
      }
    }
  }
}
```

__*Notes of interest*__

* In this example, the `key` within `properties` must match the location's `type` in order to display the selected node's name and address. The name and address of an ancestor node can be displayed by changing the `key` to a value that matches the type of the desired ancestor.
* Refer to the __Resource Details__ of the *Retrieve Data* __POST__ `/v1/commons/data/multi_read` operation for descriptions of each object, array, and property.

## Example response {#Response}

The request defined a set of locations and retrieved their names and addresses using the `parameterized` Data Dictionary keys `LOCATION_NAME` and `LOCATION_ADDRESS`.

``` json
{
    "metadata": {
        "lastRefreshed": null,
        "cacheExpirationTime": null,
        "numNodes": "3",
        "metadataKey": "7c082a3e-fc40-4adc-a6e8-40743766a14e",
        "cacheKey": "cab78a88-79d2-4320-b7a8-1c35f75c70d3",
        "totalNodes": "3",
        "totalElements": "3"
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
                    "LOCATION": "2001"
                },
                "coreEntityKey": {
                    "ORG": {
                        "id": "2001",
                        "qualifier": "Organization/United States/Metropolitan Plant/Machine Shop"
                    }
                },
                "attributes": [
                    {
                        "key": "LOCATION_NAME",
                        "rawValue": "Machine Shop 256",
                        "value": "Machine Shop 256"
                    },
                    {
                        "key": "LOCATION_ADDRESS",
                        "rawValue": "1234 West Main Street, West Boylston, MA 01234",
                        "value": "1234 West Main Street, West Boylston, MA 01234"
                    }
                ],
                "children": [],
                "summaryListDisplay": [],
                "rootEntity": "LOCATION",
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

## Next steps {#NextSteps}

Proceed to the [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463) topic for a look at more complex *Retrieve Data* requests.

## Table of Contents {#TableOfContents}

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. YOU ARE HERE
4. [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463)
5. [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33)
6. [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65)