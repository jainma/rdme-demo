---
title: "Submit Bulk Download examples"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb659316a1000880b4696"
---

# Submit Bulk Download examples

This topic contains request and response schemas and example bodies for the Submit Bulk Download (POST /v1/commons/exports/async) API operation.

> **Note:** Although the payload property accepts a model similar to the Retrieve Data request, certain elements of the Retrieve Data request payload are ignored by this operation. Refer to the request schema and example below for an accurate request model.

## Contents
* [Request schema](#requestSchema)
* [Response schema](#responseSchema)
* [Example request](#requestExample)
* [Example response](#responseExample)
* [Table of Contents](#TableOfContents)

## Schemas

### Request {#requestSchema}

``` json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "object",
  "properties": {
    "name": {
      "type": "string"
    },
    "type": {
      "type": "string"
    },
    "payload": {
      "type": "object",
      "properties": {
        "from": {
          "type": "object",
          "properties": {
            "view": {
              "type": "integer"
            },
            "locationSet": {
              "type": "object",
              "properties": {
                "rollupBy": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key"
                      ]
                    }
                  ]
                },
                "dateRange": {
                  "type": "object",
                  "properties": {
                    "options": {
                      "type": "object",
                      "properties": {
                        "timeIncrement": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "timeIncrement"
                      ]
                    },
                    "symbolicPeriod": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string"
                        },
                        "qualifier": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "id",
                        "qualifier"
                      ]
                    }
                  },
                  "required": [
                    "options",
                    "symbolicPeriod"
                  ]
                },
                "hyperfind": {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "string"
                    },
                    "qualifier": {
                      "type": "string"
                    }
                  },
                  "required": [
                    "id",
                    "qualifier"
                  ]
                }
              },
              "required": [
                "rollupBy",
                "dateRange",
                "hyperfind"
              ]
            },
            "viewPresentation": {
              "type": "string"
            }
          },
          "required": [
            "view",
            "locationSet",
            "viewPresentation"
          ]
        },
        "select": {
          "type": "array",
          "items": [
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                },
                "properties": {
                  "type": "array",
                  "items": [
                    {
                      "type": "object",
                      "properties": {
                        "key": {
                          "type": "string"
                        },
                        "value": {
                          "type": "string"
                        }
                      },
                      "required": [
                        "key",
                        "value"
                      ]
                    }
                  ]
                }
              },
              "required": [
                "key",
                "alias",
                "properties"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                }
              },
              "required": [
                "key",
                "alias"
              ]
            },
            {
              "type": "object",
              "properties": {
                "key": {
                  "type": "string"
                },
                "alias": {
                  "type": "string"
                }
              },
              "required": [
                "key",
                "alias"
              ]
            }
          ]
        },
        "options": {
          "type": "object",
          "properties": {
            "refresh": {
              "type": "null"
            },
            "extended": {
              "type": "null"
            },
            "requestTag": {
              "type": "null"
            },
            "metadataKey": {
              "type": "null"
            },
            "currencyType": {
              "type": "string"
            },
            "responseType": {
              "type": "null"
            },
            "isLegacyResponse": {
              "type": "boolean"
            },
            "includeColumnTotals": {
              "type": "null"
            },
            "secondaryRequestTag": {
              "type": "null"
            },
            "timeIncrementFormat": {
              "type": "string"
            }
          },
          "required": [
            "refresh",
            "extended",
            "requestTag",
            "metadataKey",
            "currencyType",
            "responseType",
            "isLegacyResponse",
            "includeColumnTotals",
            "secondaryRequestTag",
            "timeIncrementFormat"
          ]
        }
      },
      "required": [
        "from",
        "select",
        "options"
      ]
    }
  },
  "required": [
    "name",
    "type",
    "payload"
  ]
}
```

### Response {#responseSchema}

``` json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "object",
  "properties": {
    "status": {
      "type": "string"
    },
    "message": {
      "type": "string"
    },
    "nextPing": {
      "type": "string"
    },
    "executionKey": {
      "type": "integer"
    }
  },
  "required": [
    "status",
    "message",
    "nextPing",
    "executionKey"
  ]
}
```

## Example bodies 

## Request {#requestExample}

``` json
{
  "name": "OOAP Schedule Metrics - Leadership v1",
  "type": "DATA",
  "payload": {
    "from": {
      "view": 1,
      "locationSet": {
        "hyperfind": {
          "id": "-5001"
        },
        "dateRange": {
          "startDate": "2021-01-01",
          "endDate": "2021-01-15"
        },
        "rollupBy": [
          {
            "key": "6",
            "value": "Department"
          }
        ]
      },
      "viewPresentation": "Business Structure"
    },
    "count": null,
    "index": null,
    "select": [
      {
        "key": "LOCATION_NAME",
        "alias": "alias_241606923555628",
        "properties": [
          {
            "key": "-3",
            "value": "/"
          }
        ]
      },
      {
        "key": "LOCATION_NAME",
        "alias": "alias_261606923555667",
        "properties": [
          {
            "key": "4",
            "value": "Company"
          }
        ]
      },
      {
        "key": "LOCATION_NAME",
        "alias": "alias_281606923555697",
        "properties": [
          {
            "key": "54",
            "value": "Country"
          }
        ]
      },
      {
        "key": "LOCATION_NAME",
        "alias": "alias_301606923555727",
        "properties": [
          {
            "key": "7",
            "value": "Business"
          }
        ]
      },
      {
        "key": "LOCATION_NAME",
        "alias": "alias_300606923555727",
        "properties": [
          {
            "key": "8",
            "value": "Field"
          }
        ]
      },
      {
        "key": "LOCATION_NAME",
        "alias": "alias_421606923555903",
        "properties": [
          {
            "key": "6",
            "value": "Department"
          }
        ]
      },
      {
        "key": "LOCATION_PATH",
        "alias": "alias_681606923690648",
        "properties": [
          {
            "key": "7",
            "value": "Department"
          }
        ]
      },
      {
        "key": "KPI_METRIC_ACTUAL_HRS",
        "alias": "alias_261595447145974"
      },
      {
        "key": "KPI_FRESHNESS_LASTUPDATEDTS",
        "alias": "KPI_FRESHNESS_LASTUPDATEDTS_1"
      },
      {
        "key": "KPI_FRESHNESS_DATAFRESHNESS_INDICATOR",
        "alias": "KPI_FRESHNESS_DATAFRESHNESS_INDICATOR_1"
      }
    ],
    "options": {
      "currencyType": "PREFERRED_CURRENCY",
      "includeColumnTotals": true
    }
  }
}
```

## Response {#responseExample}

``` json
{
    "status": "PENDING",
    "message": "The request is being processed.",
    "nextPing": "60",
    "executionKey": 1
}
```

## Table of Contents {#TableOfContents}

* [Return to the Examples overview](C:aa656587-feba-4e9e-a0c4-f3d49d3a5ca9)