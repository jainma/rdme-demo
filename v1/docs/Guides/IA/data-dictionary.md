---
title: "The Data Dictionary"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# The Data Dictionary

The Data Dictionary is a collection of data elements from all domains in the suite. A particular set of data elements, known as gold data elements, are automatically loaded by the system and can be immediately used to create Dataviews.

* [Retrieve the Data Dictionary](#RetrieveTheDataDictionary)
    * [Retrieve all](#RetrieveAll)
    * [Retrieve by key](#RetrieveByKey)
* [Next steps](#NextSteps)
* [Table of Contents](#TableOfContents)

## Retrieve the Data Dictionary {#RetrieveTheDataDictionary}

You can retrieve the entire contents of the Data Dictionary in a single call, or you can specify a list of specific data elements you wish to retrieve from the Data Dictionary. 

* [Retrieve all](#RetrieveAll)
* [Retrieve by key](#RetrieveByKey)

### Retrieve all {#RetrieveAll}

To retrieve an array of all data elements within the Data Dictionary, send a **GET** request to the *Retrieve Data Element Definitions* URL: 
`https://<<hostName>>.mykronos.com/api/v1/commons/data_dictionary/data_elements`

This operation provides a summarized view of each data element's definition, structured as shown:

``` json
{
  "key": "PEOPLE_HIRE_DATE",
  "label": "Hire Date",
  "metadata": {
    "description": "Hire Date",
    "views": [
      0
    ],
    "dataType": "DATE",
    "displayPolicy": {
      "sort": "DEFAULT",
      "format": "LONGDATE"
    },
    "entity": "PEOPLE",
    "licenses": [
      "DEFAULT"
    ],
    "facp": [
      "HIRE_DATE:VIEW"
    ]
  },
  "active": true
}
```

__*Notes of interest*__

* `key` is a unique ID that maps to the keys passed in the `select` array in the *Retrieve Data* operation:

``` json
{
  "select": [
    {
      "key": "PEOPLE_HIRE_DATE"
    },
    {
      "key": "EMP_COMMON_FULL_NAME"
    }
  ]
}
```

* When `parameterized` appears in the `metadata` object, it indicates that the data element requires properties to be specified when it is invoked by a *Retrieve Data* call. The `parameterized` property only appears in the Data Dictionary JSON response when it is `true`. Parameterized data elements are structured as shown:

``` json
{
  "key": "LOCATION_NAME",
  "label": "Location Name",
  "metadata": {
    "description": "Location Name",
    "views": [
      1
    ],
    "dataType": "STRING",
    "displayPolicy": {
      "sort": "DEFAULT",
      "round": 6,
      "scale": 0,
      "format": "DEFAULT"
    },
    "entity": "LOCATION",
    "parameterized": true,
    "licenses": [
      "DEFAULT"
    ]
  },
  "active": true,
  "properties": [
    {
      "key": "0",
      "value": "Company"
    },
    {
      "key": "54",
      "value": "Country"
    },
    {
      "key": "4",
      "value": "Business"
    },
    ...
    {
      "key": "-999",
      "value": "EMPLOYEE"
    }
  ]
}
```

* Refer to the __Resource Details__ of the *Retrieve Data Element Definitions* __GET__ `/v1/commons/data_dictionary/data_elements` operation for descriptions of each object, array, and property.

### Retrieve by key {#RetrieveByKey}

When you have already identified a list of data elements, you can **POST** a call to the *Retrieve Data Element Definitions by Keys* URL to retrieve only those elements:
`https://<<hostName>>.mykronos.com/api/v1/commons/data_dictionary/data_elements/multi_read`

Include keys for all of the desired data elements in the request body:

``` json
[
  "LOCATION_ADDRESS","LOCATION_NAME"
]
```

The response schema is identical to the *Retrieve Data Element Definitions* response schema defined in [Retrieve all](#RetrieveAll).

## Next steps {#NextSteps}

Once you retrieve the Data Dictionary:

1. Parse the Data Dictionary for the keys needed to construct your __Retrieve Data__ request. 
2. For every call you build, retrieve the appropriate property keys for all `parameterized` data elements to incorporate into your call.

To learn more about using Data Dictionary keys to build basic Dataview-like queries using the *Retrieve Data* operation, proceed to the [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241) topic.

## Table of Contents {#TableOfContents}

1. YOU ARE HERE
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)
4. [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463)
5. [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33)
6. [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65)