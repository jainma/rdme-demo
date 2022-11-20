---
title: "Object references"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb62d75a8640090601e17"
---

# Object references

Our API uses object references, sometimes referred to as Object Refs, to encapsulate a reference to an object. An object represents an instance of a business entity.

* [Overview](#Overview)
* [Object reference lists](#ObjectReferenceLists)

## Overview {#Overview}

Object references contain one or at the most two keys identifying the referenced object. This format helps ensure solid API composition, which allows the output of one operation to serve as part or all of the input for another operation without any further processing. 

The JSON structure for object reference keys takes the following forms:

* `{"id": "…"}` 
* `{"qualifier": "…"}`
* `{"id": "…", "qualifier": "…"}`

When both keys are present, `id` takes precedence over `qualifier`. If both keys are present and `id` is invalid, an error is thrown. 

The `id` key is an internally managed opaque ID. The `qualifier` key is externally managed and is defined by the API resource according to the following:

* For `employee`, the `qualifier` is person number
* For `location`, the `qualifier` is the path in the location (or org)
* For `symbolicPeriod`, the `qualifier` is the name of the period, such as `"current_scheduled_period"`
* For `hyperfind`, the `qualifier` is the Hyperfind name

The JSON key for an object reference uses the singular name of a resource. Note that the key name does not include the "Ref" suffix. The key names in the example below are `employee` and `location`. 

``` json
"employee": {
    "id": "100",
    "qualifier": "203338" }

"location": {
   "id": "10999", 
   "qualifier": "…" }
```

## Object reference lists {#ObjectReferenceLists}

Object reference lists are composed of one of three parts: a list of `ids`, a list of `qualifiers`, or a list of object references (`refs`), each serving as a list of object reference keys. 

In the following JSON example, the key's `ids`, `qualifiers`, and `refs` are mutually exclusive. The JSON key for an object reference list uses the plural name of a resource. Note that the key name does not include the "Ref" suffix. The key name in the example below is `employees`. 

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
