---
title: "Large data sets"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# Large data sets

You can batch Information Access requests based on the total number of employees or locations in order to process data sets that exceed the [service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5). These limits play an important role in preserving the health of our ecosystem and help ensure all users experience consistently high performance.

For example, if the request you need to submit contains 1000 employees, you can split that request into 2 sub-requests with each sub-request containing 500 employees.

* [Prerequisites](#Prerequisites)
* [Batching requests](#BatchingRequests)
    * [Generate and batch IDs](#GenerateAndBatchIDs)
    * [Retrieve Data in batches](#RetrieveDataInBatches)
* [Next steps](#NextSteps)
* [Table of Contents](#TableOfContents)

## Prerequisites {#Prerequisites}

Understand the concepts covered in the following topics:

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)

## Batching requests {#BatchingRequests}

This exercise calls the Hyperfind operation to generate the full list employee IDs, batches the results in groups of 500, and then calls the Retrieve Data operation in batches. 

*__Note:__ This exercise uses the Postman application.*

### Generate and batch IDs {#GenerateAndBatchIDs}

1. In Postman, change the **METHOD** to **POST** and add the URL: `https://<<hostName>>.mykronos.com/api/v1/commons/hyperfind/execute` 
2. Open the **Tests** tab and add the following:

```
var jsonData = JSON.parse(responseBody);
var personNumArray = [];
var batched = [];
for(var i = 0; i < jsonData.result.refs.length; i++) {
    personNumArray.push('"' + jsonData.result.refs[i].qualifier + '"');
}
var iterations = 0
var max_count = 500;  //service limit for data/multi_read
if(personNumArray.length < max_count) {
    iterations = 1;
} else {
    iterations = Math.ceil(personNumArray.length / max_count);
}
console.log("Total Results: " + jsonData.count)
console.log("Batch Iterations: " + iterations)
var index = 0;
for(var k = 0; k < iterations; k++) {
    var arr = []
    for(var j = 0; j < max_count; j++) {
        pn = personNumArray[index + j];
        if(pn) {
            arr.push(pn);
        }
        batched[k] = arr
    }
    index = index + max_count;
    
}
for(var x = 0; x < batched.length; x++) {
    postman.setEnvironmentVariable("batched_persons_" + x, batched[x]);
    console.log ("Created hyperfind batch with Postman Variable Name: batched_persons_" + x);
    console.log(batched[x]);
}
```
 
3. Call the Hyperfind operation in Postman. This exercise uses Hyperfind with ID 1, or "All Home". Select a Hyperfind that will return results that exceed the 500 employee limit.

**Request body**

``` json
{
	"dateRange": {
		"symbolicPeriod": {
			"id":1
		}
	},
	"hyperfind": {
		"qualifier": "All Home"
	}
}
```

4. Postman now has environment variables `{{batched_persons_0}}` to `{{batched_persons_n}}`. Each set contains up to 500 employees from the Hyperfind response. In this example, our system returned a response containing 1,458 employees batched in variables `{{batched_persons_0}}`, `{{batched_persons_1}}`, and `{{batched_persons_2}}`. `{{batched_persons_2}}` contains 458 employees, while the first two contain 500 each. 

### Retrieve Data in batches {#RetrieveDataInBatches}

After you batch your request into variables, call the Retrieve Data operation using each variable. After running all the batches, combine the results into a single file for import into a database, handoff to payroll processing, and so on.

1. Open the Retrieve Data operation in Postman, or open a new tab, ensure the **METHOD** is **POST**, and add the URL: `https://<<hostName>>.mykronos.com/api/v1/commons/data/multi_read`
2. Call the Retrieve Data operation for each batch variable `{{batched_persons_0}}` to `{{batched_persons_n}}`. For example, if you have 9 batches of data, you must call this operation 9 times.

**Request body**

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
      "employees": {
        "qualifiers": [
          {{batched_persons_0}}
        ]
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

**Response body**

``` json
{
    "metadata": {
        "lastRefreshed": null,
        "cacheExpirationTime": null,
        "numNodes": "500",
        "metadataKey": "578e57fd-f496-442a-b171-2502450fa255",
        "cacheKey": "cce8595f-90e9-46f9-8d86-97bf956ed0a2",
        "totalNodes": "500",
        "totalElements": "500"
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
                    "PEOPLE": "124"
                },
                "coreEntityKey": {
                    "EMP": {
                        "id": "124"
                    }
                },
                "attributes": [
                    {
                        "key": "PEOPLE_MANAGER_NAME",
                        "rawValue": "Mahajan, Manik",
                        "value": "Mahajan, Manik"
                    },
                    {
                        "key": "EMP_COMMON_FULL_NAME",
                        "rawValue": "Rain, Jasdeep",
                        "value": "Rain, Jasdeep"
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

## Next steps {#NextSteps}

Proceed to the [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65) topic. 

## Table of Contents {#TableOfContents}

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)
4. [Complex queries](C:db9be7d9-8712-4051-bbb7-184ab9bb4463)
5. YOU ARE HERE
6. [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65)