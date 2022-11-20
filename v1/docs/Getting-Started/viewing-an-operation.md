---
title: "Viewing an operation"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
---

# Viewing an operation

When you navigate to a specific operation against an API resource, the name, HTTP method, and URL appear at the top of the pane. These are followed by a text description of the operation and a number of possible subsections, such as **Query Parameters** or **Resource Details**.

## Resource Details

The Resource Details subsection may contain tabs named **Request**, **Response**, and **Errors**. 

In the Request and Response tabs, you can switch between three views represented by the set of three icons to the right of the Request, Response, and Errors tabs. These icons only appear when viewing the Request or Response tabs and represent, from left to right, the **Default** view, the **Properties view**, and the **Combined view**.

* The Default view displays only the JSON model of the request or response body. 
* The Properties view displays information about each of the properties in the JSON model of the request or response body.
* The Combined view combines the Default and Properties views into a single view, allowing you to view both the JSON model and corresponding property information at the same time.

> **Note:** In the JSON model viewer of the Default and Combined views, you can switch between **tree** or **code** view. Code view allows you to easily select and copy the JSON template of a request.

The order of the properties displayed in the Properties and Combined views follows the hierarchy and order of those properties in the JSON model body. These views provide three columns: **Property Name**, **Type**, and **Description**.

* Property Name provides the full name of each property. This column includes a `(required)` tag below a property's name when that property is always required.
* Type provides the type of a property and enumerates valid values, when applicable.
* Description provides detailed information about the use of that property. Certain valid values may be enumerated in this column, especially for qualifiers.

For example, consider the Update Attendance Admin—Multiple Employees operation, located under the Common Resources, People, Person Assignments, Attendance Administrator Assignment resource. 

The request body contains two top-level arrays named `administration` and `personIdentity`. You can easily see these arrays in the tree view of the JSON model viewer, which is visible when using the Default or the Combined view.

The Properties and Combined views list those two top-level array property descriptions first, as they are the two entities that exist at the top level of the hierarchy. 

These views then begin listing the properties within `administrator` first and `personIdentity` second, in hierarchical order matching the JSON model body.

> **Note:** The **Type** of each array clarifies which properties belong to it as children. The listed Type is included in each child property's name as a prefix. For `administrator`, the type listed is `adminProfileDetail`. That is the prefix for all subsequent child properties of that array: `adminProfileDetail.aoid`, `adminProfileDetail.badgeNumber`, and so on.
