---
title: "Cache, count, and index"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# Cache, count, and index

Cache, count, and index work together to provide a mechanism for your application to cache and page through response data. 
 
For example, consider an application that provides a user interface in which you show a subset of the returned data but do not want to cache the entire result set in a browser. Your application's first API call specifies a `requestTag` which becomes the `cacheKey`, defines a `count` value equal to the number of elements returned in each set, and begins with `index` 0. For this example, assume a `count` of 25. 

Your application then displays the first set of data as rows 0 through 24 and provides a link to the next page, which in turn displays the next set. Selecting that link calls the API with the same call, but increments the `index` by one. On the next page, your application displays the next 25 results, 25 through 49, and so on.

* [Prerequisites](#Prerequisites)
* [Pagination from cache](#PaginationFromCache)
    * [First request](#FirstRequest)
    * [Subsequent requests](#SubsequentRequests)
    * [Understanding index and count](#UnderstandingIndexAndCount)
* [Table of Contents](#TableOfContents)

## Prerequisites {#Prerequisites}

Understand the concepts covered in the following topics:

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)

## Pagination from cache {#PaginationFromCache}

* [First request](#FirstRequest)
* [Subsequent requests](#SubsequentRequests)
* [Understanding index and count](#UnderstandingIndexAndCount)

### First request {#FirstRequest}

For this exercise, the initial API call builds on the [employee example](C:f9f05bdb-7586-4882-8dd8-54966a073241) by:

* adding `options` and specifying a `requestTag` within `options`
    * `requestTag` defines the `cacheKey` associated with the cached results
* including `index`, which always begins with 0 
* defining a `count` value equal to the number of elements returned in each set (in this example, the count is 25)

*__Note:__ If you do not specify a `requestTag` in your initial request, the system generates a `cacheKey` for you. You can access the cached results of your query in subsequent requests by providing the system-generated `cacheKey` value as the `requestTag`.*

**Example request**

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
        "id": 1
      },
      "dateRange": {
        "symbolicPeriod": {
          "qualifier": "Current_Payperiod"
        }
      }
    }
  },
  "options": {
    "requestTag": "myCache"
  },
  "index": 0,
  "count": 25
}
```

**Example response**

Note that the response:

* includes the `requestTag` you defined as `cacheKey`
* specifies the total number of elements in the results in `totalElements`

``` json
{
  "metadata": {
    "lastRefreshed": "2019-02-05T11:25:45.555802902",
    "cacheExpirationTime": "2019-02-05T16:30:45",
    "numNodes": "25",
    "metadataKey": "6abb090e-2148-445f-b3b5-35b57bc5692d",
    "cacheKey": "myCache",
    "totalNodes": "52",
    "totalElements": "52"
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
          "PEOPLE": "403"
        },
        "coreEntityKey": {
          "EMP": {
            "id": "403"
          }
        },
        "attributes": [
          {
            "key": "PEOPLE_MANAGER_NAME",
            "rawValue": "Maynard, Doris",
            "value": "Maynard, Doris"
          },
          {
            "key": "EMP_COMMON_FULL_NAME",
            "rawValue": "Armstrong-Collins, Heven",
            "value": "Armstrong-Collins, Heven"
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

### Subsequent requests {#SubsequentRequests}

For all subsequent calls, send an identical request body with one exception: increment the `index` by one each time. The API associates each additional call with the cache key you defined, which is "myCache" in this example. 

You can verify that each call is associating itself with the original cached data set by means of `lastRefreshed`, which should remain the same for all "myCache" requests. If at any time you wish to refresh the data set, include `"refresh": true` within `options`.

*__Note:__ In subsequent requests, do not change the `count` specified in the initial request body without considering the consequences and the additional logic required. Refer to [Understanding index and count](#UnderstandingIndexAndCount) for more information.*

**Example request**

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
        "id": 1
      },
      "dateRange": {
        "symbolicPeriod": {
          "qualifier": "Current_Payperiod"
        }
      }
    }
  },
  "options": {
    "requestTag": "myCache"
  },
  "index": 1,
  "count": 25
}
```

### Understanding index and count {#UnderstandingIndexAndCount}

There is a direct relationship between `index`, `count`, and `totalElements`. In this example, the response set includes 52 elements and a `count` of 25. As a result, `index` can be 0, 1, or 2. The first response with an `index` of 0 contains the first 25 results, the second with an `index` of 1 contains the next 25 results, and the final response with an `index` of 2 contains the last 2 results. 

If you change the `count`, the results returned by each `index` (and the number of valid indexes) changes appropriately. 

## Table of Contents {#TableOfContents}

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)
4. [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463)
5. [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33)
6. YOU ARE HERE