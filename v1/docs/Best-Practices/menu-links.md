---
title: "Context parameters for menu links"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---

## Context parameters for menu links

When developing an app that links to various Dimensions menu pages, the approach differs depending on whether the user is an employee or manager.

* [Employees](#Employees)
* [Managers](#Managers)
* [Implementation details](#ImpDetails)
* [Context parameter values](#ContextParameterValues)

When an employee or a manager is logged in to the Dimensions UI, the variable `ngStorage-currentContext` stores values that define the user context.

### Employees {#Employees}

To execute on a link to a menu page with an employee, all context parameters are set to `null` and only the target page is required. 

The value of `ngStorage-currentContext` resembles the following example:

``` json
{
  "timeframeId": null,
  "hyperfind": {
    "id": null,
    "type": null
  },
  "peopleIdList": null,
  "dateSpan": {
    "startDate": null,
    "endDate": null
  },
  "otherContext": {}
}
```

For employees, your app must:

* set the target URL to the menu link
* set the default `null` values for `ngStorage-currentContext`

After the values for the `ngStorage-currentContext` variable are set, `pageContextService` functions accordingly.

#### App Sequence for Employee Menu Links

1. Employee successfully logs in to the app
2. Employee selects an option that launches a Dimensions menu link
3. The menu link is launched with the appropriate context parameters
4. The Dimensions menu link successfully opens in the app

### Managers {#Managers}

This example concerns a manager who has logged in to the app to view the timecards of direct reports. The manager navigates to the Timecard module in the app, sees a list of all direct reports, and selects a few of them. This is the point where the menu link to Dimensions occurs.

The value of `ngStorage-currentContext` resembles the following example:

``` json
{
  "timeframeId": 0,
  "hyperfind": {
    "id": null,
    "type": null
  },
  "peopleIdList": [
    234,
    235,
    236
  ],
  "dateSpan": {
    "startDate": "2020-03-05T05:00:00",
    "endDate": "2020-03-08T09:00:00"
  },
  "otherContext": {},
  "timestamp": "2020-03-05T05:45:14"
}
```

For managers, your app must:

* set the target URL to the menu link
* set the values for `ngStorage-currentContext` based on the selections the manager made in the app

After the values for the `ngStorage-currentContext` variable are set, `pageContextService` functions accordingly.

#### App sequence for manager menu links

1. Manager successfully logs in to the app
2. Manager views a list of direct reports and selects multiple employees and a date range and executes a task that launches a Dimensions menu link
3. The menu link is launched and includes the parameters selected by the manager
4. The Dimensions menu link successfully opens in the app and displays all of the selected data

### Implementation details {#ImpDetails}

For an external app to set context parameters for a Dimensions module, that app must set the proper values in `defaultContextService` through `PageContextService`. In Dimensions, the user's context is always read from `PageContextService` before a module is loaded.

The code for `defaultContextService.js` is listed below. When a user login in to Dimensions an object of `defaultContextService` is associated with that login event and is injected into `PageContextService`. 

When a user navigates from one module to another in Dimensions, such as from Employee Timecard to Scheduling, the context necessary to transfer the user to the Scheduling module is saved in an object of `defaultContextService` via `PageContextService`.

This object can save `timeframeId`, `hyperfind`, `peopleIdList` and `dateSpan` in `PageContextService`.

Before switching from the current module, all of the user's current selections are set in `PageContextService`. Before launching the new module, the contents of `PageContextService` are read and set in the page to be launched. This allows users to continue to view selections from one module to another.

The code for `defaultContextService.js` is as follows:

``` js
define(['angular', 'lodash', '../pageContext'], function (angular, _) {
  'use strict'

  angular.module('common.pageContext').factory('defaultContext', function () {
    var defaultContext = {
      timeframeId: null,
      hyperfind: {
        id: null,
        type: null, //can be 'hyperfind' or 'location'
      },
      peopleIdList: null,
      dateSpan: {
        startDate: null,
        endDate: null,
      },
      otherContext: {},
    }
    return {
      getDefaultContext: function getDefaultContext() {
        return _.cloneDeep(defaultContext)
      },
    }
  })
})
```

### Context parameter values {#ContextParameterValues}

#### timeframeId

The ID of the timeframe expressed as an integer ID. For example, if the user selected the Current Schedule Period in the Dimensions UI, that corresponds to an ID value of 4 that is captured in `timeframeId`.

#### peopleIdList

An array of person keys representing the employees selected by a manager. For example, if a manager selects three employees in an app, the person keys of those three employees is passed in `peopleIdList`.

#### dateSpan

The `dateSpan` object defines a start date and an end date of a date range selected by a user. For example, suppose a user selected the 5th of March 2020 as the start date and the 8th of March 2020 as the end date. Those dates (and times, if selected) are captured in `dateSpan` under `startDate` and `endDate`.

#### hyperfind

The `hyperfind` object defines a reference to a Hyperfind using `id` and `type`. 

The `type` parameter defines whether the filtering is based on a location or a Hyperfind query. Valid values include 1 for location and 4 for a Hyperfind query.

The `id` parameter contains the ID of the selected Hyperfind or location.