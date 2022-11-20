---
title: "Global Multiple Manager Role switching"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---

# Global Multiple Manager Role switching

A logged-in manager who has two or more multi-manager roles (Role Assignments) can switch between assigned roles using the Dimensions API and the global `roleId` query parameter.

_**Important:** Once the logged-in manager's role is switched with the `roleId` query parameter, that role remains active until you pass a different `roleId` value or the logged-in manager's session expires._

## Procedure

1. The logged-in manager must have at least two or more roles assigned.
    * Use the Manager Role Assignments API resource (/v1/commons/persons/manager_role_assignments) to add or modify role assignments.
    * For example, call `POST /v1/commons/persons/manager_role_assignments/apply_upsert` with a request payload similar to the following example:

``` json
[
    {
        "personIdentity": {
            "personNumber": "10015"
        },
        "roleAssignmentChanges": {
            "add": [
                {
                    "name": "Secondary Role",
                    "description": "Used as a secondary role",
                    "attributes": [
                        {
                            "type": {
                                "qualifier": "FUNCTION_ACCESS_PROFILE"
                            },
                            "value": {
                                "qualifier": "Manufacturing Manager Using PE"
                            }
                        },
                        {
                            "type": {
                                "qualifier": "DISPLAY_PROFILE"
                            },
                            "value": {
                                "qualifier": "Manu Display Profile"
                            }
                        },
                        {
                            "type": {
                                "qualifier": "PAY_CODE_EDIT_PROFILE"
                            },
                            "value": {
                                "qualifier": "Manufacturing Pay Codes"
                            }
                        },
                        {
                            "type": {
                                "qualifier": "WORK_RULE_PROFILE"
                            },
                            "value": {
                                "qualifier": "Manufacturing Work Rules"
                            }
                        },
                        {
                            "type": {
                                "qualifier": "REPORT_PROFILE"
                            },
                            "value": {
                                "qualifier": "Manager"
                            }
                        },
                        {
                            "type": {
                                "qualifier": "EMPLOYEE_GROUP"
                            },
                            "value": {
                                "qualifier": "Empty Profile"
                            },
                            "effectiveDate": "1753-01-01",
                            "expirationDate": "2017-04-18"
                        },
                        {
                            "type": {
                                "qualifier": "EMPLOYEE_GROUP"
                            },
                            "value": {
                                "qualifier": "US Manufacturing Set"
                            },
                            "effectiveDate": "2017-04-18",
                            "expirationDate": "3000-01-01"
                        },
                        {
                            "type": {
                                "qualifier": "MANAGER_JOB_TRANSFER_SET"
                            },
                            "value": {
                                "qualifier": "Empty Profile"
                            },
                            "effectiveDate": "1753-01-01",
                            "expirationDate": "2017-04-18"
                        },
                        {
                            "type": {
                                "qualifier": "MANAGER_JOB_TRANSFER_SET"
                            },
                            "value": {
                                "qualifier": "US Mfg Metropolitan Plant Set"
                            },
                            "effectiveDate": "2017-04-18",
                            "expirationDate": "3000-01-01"
                        }
                    ],
                    "default": false
                }
            ]
        }
    }
]
```

2. Acquire the role assignment IDs for the different roles available to the logged-in manager using the Manager Role Assignments GET operation. For example:

`GET /v1/commons/persons/manager_role_assignments/?person_number=10015`

The response resembles the following example:

``` json
{
  "personIdentity": {
    "personId": 51,
    "personNumber": "10015"
  },
  "roleAssignments": [
    {
      "assignmentId": 631,
      "name": "Secondary Role",
      "description": "Used as a secondary role",
      "attributes": [
        ...
      ],
      "default": false
    },
    {
      "assignmentId": 221,
      "name": "Initial Role",
      "description": "Initial role assignment",
      "attributes": [
        ...
      ],
      "default": true
    }
  ]
}
```

_**Note:** The example response's `attributes` array is truncated in this example._

3. Using the `assignmentId` value associated with the desired manager role, pass the optional query parameter `roleId` with any API operation. For example:

`POST /v1/commons/persons/51?roleId=221`

`POST /v1/scheduling/schedule/pay_code_edits/multi_create?roleId=631`

_**Important:** Once the logged-in manager's role is switched with the `roleId` query parameter, that role remains active until you pass a different `roleId` value or the logged-in manager's session expires._

