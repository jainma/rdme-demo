---
title: "Complex queries"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb67b2ee1f50047267944"
---

# Complex queries

* [Prerequisites](#Prerequisites)
* [First query](#FirstQuery)
    * [First response](#FirstResponse)
* [Second query](#SecondQuery)
    * [Second response](#SecondResponse)
* [Next steps](#NextSteps)
* [Table of Contents](#TableOfContents)

## Prerequisites {#Prerequisites}

Understand the concepts covered in the following topics:

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)

## First query {#FirstQuery}

The following *Retrieve Data* request body represents an aggregation of data for use in preparing payroll for a set of employees.

In this example, the request:

* retrieves a collection of data elements from the Data Dictionary related to running payroll
* defines the data view as EMP for employee, which is similar to an Employee Dataview
* selects the set of employees using a Hyperfind query
* establishes a date range for the requested data in the form of a symbolic period 

``` json
{
  "select": [
    {
      "key": "TK_ACTUAL_APPLY_DATE",
      "alias": "Apply Date"
    },
    {
      "key": "TK_ACTUAL_JOB_TRANSFER",
      "alias": "Job Transfer"
    },
    {
      "key": "TK_ACTUAL_LABOR_TRANSFER",
      "alias": "Labor Transfer"
    },
    {
      "key": "TK_ACTUAL_PAYPERIOD_NUMBER",
      "alias": "Pay Period Number"
    },
    {
      "key": "TK_ACTUAL_PAYPERIOD_WEEK",
      "alias": "Pay Period Week"
    },
    {
      "key": "TK_ACTUAL_SIGNED_OFF",
      "alias": "Sign Off"
    },
    {
      "key": "TK_ACTUAL_WAGE_ADD",
      "alias": "Wage Add"
    },
    {
      "key": "TK_ACTUAL_WAGE_MULTIPLIER",
      "alias": "Wage Multiplier"
    },
    {
      "key": "TK_AVG_ACTUAL_AMOUNT",
      "alias": "Amount"
    },
    {
      "key": "TK_AVG_ACTUAL_THROUGH_SELECTED_DAY_HOURS",
      "alias": "Actual Through Selected Day Hours"
    },
    {
      "key": "TK_AVG_ACTUAL_THROUGH_SELECTED_DAY_HOURS_MINUS_AVG_TARGET_HOURS",
      "alias": "Actual Through Selected Day Hours Minus Avg Target Hours"
    },
    {
      "key": "TK_AVG_AVG_TARGET_HOURS_MINUS_ACTUAL_THROUGH_SELECTED_DAY_HOURS",
      "alias": "Avg Target Hours Minus Actual Through Selected Day Hours"
    },
    {
      "key": "TK_AVG_VAR_ACTUAL_HOURS_MINUS_TARGET_THROUGH_SELECTED_DAY_HOURS",
      "alias": "Var Actual Hours Minus Target Through Selected Day Hours"
    },
    {
      "key": "TK_AVG_VAR_TARGET_HOURS_MINUS_ACTUAL_THROUGH_SELECTED_DAY_HOURS",
      "alias": "Var Target Hours Minus Actual Through Selected Day Hours"
    },
    {
      "key": "TK_DAILY_ACTUAL_APPLY_DATE",
      "alias": "Daily Apply Date"
    },
    {
      "key": "TK_DAILY_ACTUAL_DURATION_IN_HOURS",
      "alias": "Daily Duration in Hours"
    },
    {
      "key": "CORE_PAYCODE_IS_COMBINED",
      "alias": "Paycode Is Combined"
    },
    {
      "key": "CORE_PAYCODE",
      "alias": "Paycode Name"
    },
    {
      "key": "CORE_PAYCODE_TYPE",
      "alias": "Paycode Type"
    },
    {
      "key": "TK_DAILY_ACTUAL_TOTAL_DAYS",
      "alias": "Daily Total Days"
    },
    {
      "key": "TK_DAILY_ACTUAL_TOTAL_WAGES",
      "alias": "Daily Total Wages"
    },
    {
      "key": "TK_SHIFT_ACTUAL_APPLY_DATE",
      "alias": "Shift Apply Date"
    },
    {
      "key": "TK_SHIFT_ACTUAL_DURATION_IN_HOURS",
      "alias": "Shift Duration in Hours"
    },
    {
      "key": "TK_SHIFT_ACTUAL_TOTAL_DAYS",
      "alias": "Shift Total Days"
    },
    {
      "key": "TK_SHIFT_ACTUAL_TOTAL_WAGES",
      "alias": "Shift Total Wages"
    }
  ],
  "options": {
    "extended": {
      "contributingWeekFlag": true
    }
  },
  "from": {
    "view": "EMP",
    "employeeSet": {
      "hyperfind": {
        "qualifier": "All Home"
      },
      "dateRange": {
        "symbolicPeriod": {
          "qualifier": "Previous_Payperiod"
        }
      }
    }
  }
}
```

### First response {#FirstResponse}

In this excerpt, the response:

* returns data associated with each data element's key for all dates within the specified date range
* identifies all relevant business entities involved in the request under `coreEntityKey`, such as:
    * the employee's ID and person number (the qualifier)
    * The paycode ID and qualifier
    * The specific date involved
    * The `ORGJOB`'s ID and qualifier, which is the organizational job's location within the Business Structure
* returns all of the relevant `attributes` associated with the data element, which in this particular excerpt includes:
    * the paycode name
    * total wages for the shift
    * a Boolean indicator of whether or not the paycode is a combined paycode
    * the apply date of the shift
    * the duration of the shift in hours
    * the total days of the shift
    * the paycode type

Each data element returns a unique set of attributes. Refer to [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e) topic for more information about accessing data elements and their attributes.

``` json
{
  "metadata": {
    "lastRefreshed": null,
    "cacheExpirationTime": null,
    "numNodes": "14",
    "metadataKey": "d683ca63-1b1b-4d75-952d-039917cfee21",
    "cacheKey": "f641b454-d26e-4f3a-b443-b4a136da54e3",
    "currencyCode": null,
    "totalNodes": "14",
    "totalElements": "14"
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
          "TKSHIFT_ACTUAL_TOTAL_SUMMARY": "2018-04-13"
        },
        "coreEntityKey": {
          "EMP": {
            "id": "239",
            "qualifier": "20331"
          },
          "PAYCODE": {
            "id": "114",
            "qualifier": "Regular"
          },
          "DAY": {
            "id": "2018-04-13",
            "qualifier": "2018-04-13"
          },
          "ORGJOB": {
            "id": "68",
            "qualifier": "Organization/United States/Metropolitan Plant/Machine Shop/Apprentice Welder"
          }
        },
        "attributes": [
          {
            "key": "CORE_PAYCODE",
            "alias": "Paycode Name",
            "rawValue": "Regular",
            "value": "Regular"
          },
          {
            "key": "TK_SHIFT_ACTUAL_TOTAL_WAGES",
            "alias": "Shift Total Wages",
            "rawValue": "368.0",
            "value": "368.00"
          },
          {
            "key": "CORE_PAYCODE_IS_COMBINED",
            "alias": "Paycode Is Combined",
            "rawValue": "false",
            "value": "false"
          },
          {
            "key": "TK_SHIFT_ACTUAL_APPLY_DATE",
            "alias": "Shift Apply Date",
            "rawValue": "2018-04-13",
            "value": "4/13/2018"
          },
          {
            "key": "TK_SHIFT_ACTUAL_DURATION_IN_HOURS",
            "alias": "Shift Duration in Hours",
            "rawValue": "8.0",
            "value": "8.00"
          },
          {
            "key": "TK_SHIFT_ACTUAL_TOTAL_DAYS",
            "alias": "Shift Total Days",
            "rawValue": "0.0",
            "value": "0.00"
          },
          {
            "key": "CORE_PAYCODE_TYPE",
            "alias": "Paycode Type",
            "rawValue": "Regular",
            "value": "Regular"
          }
        ],
        "children": [],
        "summaryListDisplay": [],
        "rootEntity": "TKSHIFT_ACTUAL_TOTAL_SUMMARY",
        "customProperties": {}
      }
    ],
    "summaryListDisplay": [],
    "rootEntity": "ROOT",
    "customProperties": {}
  }
}
```

## Second query {#SecondQuery}

The following *Retrieve Data* request body represents an aggregation of data for use in preparing payroll for a set of employees.

In this example, the request:

* retrieves a collection of data elements from the Data Dictionary related to running payroll
* defines the data view as EMP for employee, which is similar to an Employee Dataview
* selects the set of employees using a Hyperfind query
* establishes a date range for the requested data in the form of a symbolic period 
* sorts the results by employee name

``` json
{
  "select": [
    {
      "key": "PEOPLE_PERSON_NUMBER",
      "alias": "PersonNumber"
    },
    {
      "key": "PEOPLE_BADGE_NUMBER",
      "alias": "BadgeNumber"
    },
    {
      "key": "PEOPLE_PAYRULE",
      "alias": "Payrule"
    },
    {
      "key": "PEOPLE_HIRE_DATE",
      "alias": "HireDate"
    },
    {
      "key": "PEOPLE_EMP_TERM",
      "alias": "EmployeeTerm"
    },
    {
      "key": "EMP_COMMON_PRIMARY_ORG",
      "alias": "PrimaryOrg"
    },
    {
      "key": "EMP_COMMON_PRIMARY_JOB",
      "alias": "PrimaryJob"
    },
    {
      "key": "TK_MANAGER_SIGNOFF_THRU_DATE",
      "alias": "SignOffDate"
    },
    {
      "key": "TK_ACTUAL_SIGNED_OFF",
      "alias": "IsSignedOff"
    },
    {
      "key": "TK_ACTUAL_JOB_TRANSFER",
      "alias": "JobTransfer"
    },
    {
      "key": "TK_PREV_PAYPERIOD_STARTDATE",
      "alias": "PreviousPeriodStartDate"
    },
    {
      "key": "TK_PREV_PAYPERIOD_ENDDATE",
      "alias": "PreviousPeriodEndDate"
    },
    {
      "key": "TK_NEXT_PAYPERIOD_STARTDATE",
      "alias": "NextPeriodStartDate"
    },
    {
      "key": "TK_NEXT_PAYPERIOD_ENDDATE",
      "alias": "NextPeriodEndDate"
    },
    {
      "key": "TK_CURR_PAYPERIOD_STARTDATE",
      "alias": "CurrentPeriodStartDate"
    },
    {
      "key": "TK_CURR_PAYPERIOD_ENDDATE",
      "alias": "CurrentPeriodEndDate"
    },
    {
      "key": "TK_ACTUAL_PAYPERIOD_WEEK",
      "alias": "PayPeriodWeek"
    },
    {
      "key": "TK_ACTUAL_PAYPERIOD_NUMBER",
      "alias": "PayPeriodNumber"
    },
    {
      "key": "TK_LAST_TOTAL_TIME",
      "alias": "LastTotalTime"
    },
    {
      "key": "TK_LAST_TOTAL_CHANGE_TIME",
      "alias": "LastTotalChangeTime"
    },
    {
      "key": "TK_ACTUAL_WAGE_ADD",
      "alias": "WageAdd"
    },
    {
      "key": "TK_ACTUAL_APPLY_DATE",
      "alias": "ApplyDate"
    },
    {
      "key": "TK_ACTUAL_WAGE_MULTIPLIER",
      "alias": "WageMultiplier"
    },
    {
      "key": "PEOPLE_CUSTOM",
      "alias": "Custom 1",
      "properties": [
        {
          "key": "1"
        }
      ]
    },
    {
      "key": "EMP_COMMON_FULL_NAME",
      "alias": "EmployeeName"
    },
    {
      "key": "PEOPLE_EMP_STATUS",
      "alias": "EmpStatus"
    }
  ],
  "from": {
    "view": 0,
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
  "sortBy": [
    {
      "key": "EMP_COMMON_FULL_NAME",
      "alias": "EmployeeName",
      "sortDirection": "asc"
    }
  ]
}
```

### Second response {#SecondResponse}

In this excerpt, the response:

* returns data associated with each data element's key for all dates within the specified date range
* sorts the data by employee, with `coreEntityKey` identifying the employee by employee ID 
* returns all of the relevant `attributes` associated with the data element, which in this particular excerpt includes:
    * the start and end dates of the previous, current, and next pay periods
    * the employee's primary org, or assigned location within the Business Structure
    * the employee's:
        * full name and person number
        * hire date
        * employment status
        * primary job
        * badge number
        * default pay rule
        * employee term
    * the date through which a manager has signed off on the employee's time
    * the last time the employee generated activity that was totaled and the last time a total was changed
    * a custom field

__*Note:*__  The `rawValue` and `value` properties only appear in the response when the system has data to return for a given `key`. In the following example, the first entry has data and the second does not:

``` json
    {
      "key": "PEOPLE_PAYRULE",
      "alias": "Payrule",
      "rawValue": "Manufacturing Intern",
      "value": "Manufacturing Intern"
    },
    {
      "key": "PEOPLE_EMP_TERM",
      "alias": "EmployeeTerm"
    }
```

Each data element returns a unique set of attributes. Refer to [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e) topic for more information about accessing data elements and their attributes.

``` json
{
  "metadata": {
    "lastRefreshed": null,
    "cacheExpirationTime": null,
    "numNodes": "90",
    "metadataKey": "e1a1c4c6-8bd0-4397-91dd-a13abf6fdcfa",
    "cacheKey": "a71d7626-e6d2-4491-ac93-cebb027d8e1a",
    "currencyCode": null,
    "totalNodes": "90",
    "totalElements": "90"
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
          "TKPAYPERIOD": "243",
          "TKTOTALSTATUS": "243",
          "TKSIGNOFF": "243",
          "PEOPLE": "243"
        },
        "coreEntityKey": {
          "EMP": {
            "id": "243"
          }
        },
        "attributes": [
          {
            "key": "TK_NEXT_PAYPERIOD_ENDDATE",
            "alias": "NextPeriodEndDate",
            "rawValue": "2019-01-20",
            "value": "1/20/2019"
          },
          {
            "key": "EMP_COMMON_PRIMARY_ORG",
            "alias": "PrimaryOrg",
            "rawValue": "Organization/United States/Metropolitan Plant/Machine Shop",
            "value": "Organization/United States/Metropolitan Plant/Machine Shop"
          },
          {
            "key": "TK_PREV_PAYPERIOD_ENDDATE",
            "alias": "PreviousPeriodEndDate",
            "rawValue": "2019-01-06",
            "value": "1/06/2019"
          },
          {
            "key": "PEOPLE_PAYRULE",
            "alias": "Payrule",
            "rawValue": "Manufacturing Intern",
            "value": "Manufacturing Intern"
          },
          {
            "key": "PEOPLE_EMP_TERM",
            "alias": "EmployeeTerm"
          },
          {
            "key": "PEOPLE_HIRE_DATE",
            "alias": "HireDate",
            "rawValue": "2017-04-18",
            "value": "4/18/2017"
          },
          {
            "key": "TK_LAST_TOTAL_TIME",
            "alias": "LastTotalTime",
            "rawValue": "2018-04-24T06:53:42",
            "value": "4/24/2018 6:53 AM"
          },
          {
            "key": "TK_CURR_PAYPERIOD_ENDDATE",
            "alias": "CurrentPeriodEndDate",
            "rawValue": "2019-01-13",
            "value": "1/13/2019"
          },
          {
            "key": "TK_PREV_PAYPERIOD_STARTDATE",
            "alias": "PreviousPeriodStartDate",
            "rawValue": "2018-12-31",
            "value": "12/31/2018"
          },
          {
            "key": "PEOPLE_EMP_STATUS",
            "alias": "EmpStatus",
            "rawValue": "Active",
            "value": "Active"
          },
          {
            "key": "PEOPLE_BADGE_NUMBER",
            "alias": "BadgeNumber",
            "rawValue": "89883",
            "value": "89883"
          },
          {
            "key": "EMP_COMMON_PRIMARY_JOB",
            "alias": "PrimaryJob",
            "rawValue": "Apprentice Welder",
            "value": "Apprentice Welder"
          },
          {
            "key": "EMP_COMMON_FULL_NAME",
            "alias": "EmployeeName",
            "rawValue": "Adams, Eliza",
            "value": "Adams, Eliza"
          },
          {
            "key": "PEOPLE_PERSON_NUMBER",
            "alias": "PersonNumber",
            "rawValue": "20335",
            "value": "20335"
          },
          {
            "key": "TK_LAST_TOTAL_CHANGE_TIME",
            "alias": "LastTotalChangeTime",
            "rawValue": "2018-04-24T06:53:42",
            "value": "4/24/2018 6:53 AM"
          },
          {
            "key": "PEOPLE_CUSTOM",
            "alias": "Custom 1"
          },
          {
            "key": "TK_MANAGER_SIGNOFF_THRU_DATE",
            "alias": "SignOffDate"
          },
          {
            "key": "TK_NEXT_PAYPERIOD_STARTDATE",
            "alias": "NextPeriodStartDate",
            "rawValue": "2019-01-14",
            "value": "1/14/2019"
          },
          {
            "key": "TK_CURR_PAYPERIOD_STARTDATE",
            "alias": "CurrentPeriodStartDate",
            "rawValue": "2019-01-07",
            "value": "1/07/2019"
          }
        ],
        "children": [],
        "summaryListDisplay": [],
        "rootEntity": "PEOPLE",
        "customProperties": {}
      },
      ...
    ]
  },
  "summaryListDisplay": [],
  "rootEntity": "ROOT",
  "customProperties": {}
}
```

See the [full response here](example-full-response.json).

## Next steps {#NextSteps}

Proceed to the [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33) topic.

## Table of Contents {#TableOfContents}

1. [The Data Dictionary](C:a7a9ad1a-a59c-4e7b-921a-c14f9052fe4e)
2. [Employee-based queries](C:f9f05bdb-7586-4882-8dd8-54966a073241)
3. [Location-based queries](C:f1e421a0-62d6-4f69-867f-493c9e43e804)
4. YOU ARE HERE
5. [Large data sets](C:ee3c4c19-a469-4752-902c-0eb7da8ade33)
6. [Cache, count, and index](C:13750c3f-3dae-4a12-81f1-e7c0fb5aec65)