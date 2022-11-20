---
title: "Important notes"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb662255dd00016e0b208"
---

# Important notes

## Contents

* [R9 Update 2](#R9U2)
* [R9 Update 1](#R9U1)
* [R9](#R9)
* [R8 Update 3](#R8U3)
* [R8 Update 2](#R8U2)
* [R8 Update 1](#R8U1)
* [R8](#R8)
* [R7 Update 4](#R7U4)
* [R7 Update 3](#R7U3)
* [R7 Update 2](#R7U2)
* [R7 Update 1](#R7U1)
* [R7](#R7)
* [R6 Update 4](#R6U4)
* [R6 Update 3](#R6U3)

## Dimensions R9 Update 2 {#R9U2}

The following changes were made to the API and Developer Portal in Dimensions R9 Update 2.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* One

### Docs updates

The following changes were made to the conceptual documentation:

* Updated the [Certificate Assignments](C:d0673635-21b5-4241-b3d0-7d4880743e38) topic to include instructions for using the new __Delete Certification Assignments__ (`POST /v1/commons/persons/certifications/apply_delete`) API operation.
* Updated the [Skill Assignments](C:98b7b88d-f3e8-4ee8-bc74-a49037faa513) topic to include instructions for using the new __Delete Skill Assignments__ (`POST /v1/commons/persons/skills/apply_delete`) API operation.
* Updated the [HTTP status codes](C:ab842096-366f-496f-a471-e73ac58b8540) topic to include more details about HTTP status code 413, which is returned for service limit violations and for request payload JSONs that exceed the size limit. By default, request payload JSONs are limited to 1 megabyte in size. Some operations allow for a larger request payload. The increased size is documented in the operation's description. For example, see the Import Labor Budgets (POST /v1/forecasting/labor_budget/import) API operation.


### API updates {#APIUpdates}

The following changes were made to the reference documentation:

* Renamed the __Healthcare Analytics__ domain to __Healthcare Productivity__. This change only affects branding and is backwards compatible--URIs, ACP key names, and other such entities are unchanged.

## Dimensions R9 Update 1 {#R9U1}

The following changes were made to the API and Developer Portal in Dimensions R9 Update 1.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The __Update Job Preferences for Multiple Employees__ (`POST /v1/commons/persons/job_preferences/multi_update`) API operation could fail with an HTTP status code 504 Gateway Timeout error when 100 or more records were passed in the request payload. (WFD-142980)
* The __Retrieve Locations__ (`POST /v1/commons/locations/multi_read`) API operation did not always return the same business structure shown in the UI. (WFD-141624)
* The __Create or Update Location Set__ (`POST /v1/commons/location_sets/apply_upsert`) API operation returned improperly formatted JSON in the response bodies of HTTP status code 207 Partial Success responses. (WFD-138917)
* The __Create Batch Tasks__ (`POST /v1/platform/batch_processing/batch_tasks/multi_create`) API operation did not correct resolve object references using a qualifier instead of an ID and did not honor the required properties in the request payload, which could result in bad data saved to the system. (WFD-137642)
* The __Retrieve Schedule Rule Overrides__ (`POST /v2/commons/persons/schedule_rule_overrides/multi_read`) API operation incorrectly reported the time amount in seconds rather than HH:MM format in the HTTP status code 207 Partial Success response body. (WFD-144696)
* The __Retrieve Schedule Audits__ (`POST /v1/scheduling/audits/multi_read`) API operation would not accept the `EMPLOYEES` option within the `select` array. (WFD-142563)
* The __Create Time Off Request as Manager__ (`POST /v1/scheduling/timeoff`) API operation threw a null pointer exception when attempting to apply a time off request with auto approval. (WFD-142467)
* After R8 Update 3, the __Update Employment Term Assignments__ (`POST /v1/commons/persons/employment_terms/multi_upsert`) API operation became case sensitive to values in certain request payload properties. Those properties are no longer case sensitive. (WFD-138644)
* The __Create Time Off Request as Manager__ (`POST /v1/scheduling/timeoff`) API operation intermittently threw optimistic locking errors. (WFD-138468)
* Enhanced the __Retrieve Schedule__ (`POST /v1/scheduling/schedule/multi_read`) API operation's documentation to clarify the behavior of the `excludeBreaks` property in the request payload. (WFD-138344)
* The __Create or Update Labor Category Lists__ (`POST /v1/commons/labor_category_lists/multi_upsert`) API operation incorrect threw an HTTP status code 500 Internal Server Error when the laborCategory object was omitted from the request payload. The operation now returns a correct and informative error. (WFD-145073)
* The __Update Timecard as Manager__ (`POST /v1/timekeeping/timecard`) API operation incorrect threw an HTTP status code 500 Internal Server Error when passing a pay code edit object reference without also passing a paycode object reference in the request payload. The operation now returns a correct and informative error. (WFD-144024)
* The __Create Adjustment Rule__ (`POST /v1/timekeeping/setup/adjustment_rules`) API operation incorrectly used the locale policy to determine the number of decimal places to round certain employee data. This operation no longer uses the locale policy to make this determination and now behaves exactly like the UI. (WFD-142590)
* The __Bulk Import Punches__ (`POST /v1/timekeeping/punches/import`) API operation did not correct resolve object references to comments that used a qualifier instead of an ID.(WFD-141760)
* The __Bulk Accrual Reset__ (`POST /v1/timekeeping/accruals/resets`) API operation unnecessarily made a CT call during execution that could generate an error. This operation no longer makes an unnecessary CT call when executed. (WFD-141250)
* Updated the __Update Timecard as Manager__ (`POST /v1/timekeeping/timecard`) API operation's documentation to note that the `do` > `moveAmounts` > `updated` entity in the request payload is not supported. (WFD-139894)
* Enhanced the __Retrieve Percentage Allocation Rules__ (`POST /v1/timekeeping/setup/percentage_allocation_rules/multi_read`) API operation's performance to handle environments where the performance of the __Retrieve All Percentage Allocation Rules__ (`GET /v1/timekeeping/setup/percentage_allocation_rules`) operation is not sufficient. (WFD-138724)
* Enhanced the __Retrieve Timecard as Manager__ (`GET /v1/timekeeping/timecard`) and the __Retrieve Timecard as Employee__ (`GET /v1/timekeeping/employee_timecard`) API operations to add two new query parameters: (DIM-389665, WFD-132534)
    * `retrieve_full_labor_categories`: when true, the API returns a significantly more detailed labor category object. This parameter is optional, and the default value is false.
    * `return_true_cost_center_id`: when true, the API returns the correct cost center ID. This parameter is optional, and the default value is false.
* Enhanced the __Retrieve Timecards as Manager__ (`GET /v1/timekeeping/timecard/multi_read`) and the __Retrieve Timecards as Employee__ (`GET /v1/timekeeping/employee_timecard/multi_read`) API operations to add two new request properties: (DIM-389665, WFD-132534)
    * `retrieveFullLaborCategories`: when true, the API returns a significantly more detailed labor category object. This property is optional, and the default value is false.
    * `returnTrueCostCenterId`: when true, the API returns the correct cost center ID. This property is optional, and the default value is false.
* Enhanced the __Stage Payroll Asynchronously__ (`POST /v1/commons/payroll/staging/async`) API operation with a new `processBasedOn` `type` of `POSITION_ASSIGNMENT`. All associated conceptual documentation and examples have been updated with examples of the new functionality. (DIM-394054)
* Enhanced the __Create Scheduling Leave Edits with Options__ (`POST /v1/scheduling/schedule/leave_edits/apply_create`) API operation with a new `assignBreaks` Boolean property in the request payload. When true, breaks are automatically adjusted. This property is optional, and the default value is false. (WFD-133966)
* Enhanced the __Retrieve Locations__ (`POST /v1/commons/locations/multi_read`) API operation with a new `childrenOfDuring` request property, which allows the caller to retrieve first level child nodes of a specific parent node within a specified date range. This property is optional. (WFD-143883)
* Enhanced the __Retrieve Timecard Data for Multiple Employees__ (`POST /v1/timekeeping/timecard_metrics/multi_read`) API operation to support the upcoming Multiple Assignments feature by adding a new `position` property to the response payload that only appears when the Multiple Assignments feature is enabled. Refer to the operation's description for more details and an example request and response. (DIM-390428)
* Enhanced the following Request Subtype API operations with the `enableDurationSelectionInTile ` Boolean property in the response body, which defaults to false: (DIM-375226)
    * __Retrieve Request Subtype by ID__ (`GET /v1/scheduling/setup/request_subtypes/{id}`)
    * __Retrieve Request Subtype by Name__ (`GET /v1/scheduling/setup/request_subtypes?name=""`)
    * __Retrieve Request Subtypes__ (`POST /v1/scheduling/setup/request_subtypes/multi_read`)
* Enhanced the following Labor Category Profiles API operations with a `date` query parameter or request property, which allows the caller to retrieve versions on specific dates: (DIM-378061)
    * __Retrieve All Labor Category Profiles__ (`GET /v1/commons/labor_category_profiles`)
    * __Retrieve Labor Category Profile by ID__ (`GET /v1/commons/labor_category_profiles/{id}`)
    * __Retrieve Labor Category Profile for Current User__ (`GET /v1/commons/labor_category_profiles/current_user`)
    * __Retrieve Labor Category Profiles__ (`POST /v1/commons/labor_category_profiles/multi_read`)
    * __Retrieve Paginated List of Labor Category Profiles__ (`POST /v1/commons/labor_category_profiles/apply_read`)
* Enhanced the following API Labor Standards API operations with Access Control Point (ACP) validation when the following system setting is set to `true`: `site.forecasting.labor.standard.components.acp.enabled` (backwards compatibility on existing tenants is maintained): (DIM-342171)
    * __Create Labor Standard__ (`POST /v1/forecasting/labor_standards`)
    * __Create Labor Standards__ (`POST /v1/forecasting/labor_standards/multi_create`)
    * __Update Labor Standard__ (`POST /v1/forecasting/labor_standards/apply_update`)
    * __Update Labor Standards__ (`POST /v1/forecasting/labor_standards/multi_update`)
* Enhanced the __Retrieve Payroll Export Asynchronous Request Status by Key__ (`GET /v1/commons/payroll/{executionKey}/status`) API operation to add the `queued` and `queued_failed` statuses. (DIM-385345)
* Enhanced the following Labor Standards API operations to include the `laborStandardAdjustments` object in the response body: (DIM-372219)
    * __Retrieve Labor Standard by ID__ (`GET /v1/forecasting/labor_standards/{id}`)
    * __Retrieve All Labor Standards or by Specification__ (`GET /v1/forecasting/labor_standards`)
    * __Retrieve Labor Standards__ (`POST /v1/forecasting/labor_standards/multi_read`)
    * __Create Labor Standard__ (`POST /v1/forecasting/labor_standards`)
    * __Create Labor Standards__ (`POST /v1/forecasting/labor_standards/multi_create`)
    * __Update Labor Standard__ (`POST /v1/forecasting/labor_standards/apply_update`)
    * __Update Labor Standards__ (`POST /v1/forecasting/labor_standards/multi_update`)
* Enhanced the following Group Schedule Membership API operations with an optional property `refs` inside the `employeeRefs` object in the request payload: (DIM-386734)
    * __Add Group Membership__ (`POST /v1/scheduling/group_schedule/assignments/apply_create`)
    * __Remove Group Membership__ (`POST /v1/scheduling/group_schedule/assignments/apply_delete`)
* Enhanced the following Activities API operations with an optional property `dayDivideState` inside the `processedSegments` object in the request payload, which has the following options: 0=No Day Divide, 1=Before Day Divide, 2=After Day Divide, -1=Undetermined (WFD-141786)
    * __Retrieve Activity Shifts__ (`POST /v1/work/activity_shifts/multi_read`)
    * __Retrieve Net Changes for Activity Shifts__ (`POST /v1/work/activity_shifts/net_changes/multi_read`)
    * __Retrieve Activity Transactions__ (`POST /v1/work/activity_transactions/multi_read`)
* Enhanced the __Create Employment Term Schedule Pattern__ (`POST /v1/scheduling/employment_term_schedule_patterns/apply_create`) API operation with a `formatForTransactionAssistant` Boolean property in the request payload that, when true, formats the response so that it can be resubmitted by the Transaction Assistant in the event of an error. (WFD-140781)
* Enhanced the following API operations with an `updatePartial` property in the request payload that, when set to true, changes most mandatory request parameters to optional, allowing activities to be created or updated with only a name and a description: (DIM-376093, WFD-140902)
    * __Create or Update Activities__ (`POST /v1/work/activities/multi_upsert`)
    * __Create Activity__ (`POST /v1/work/activities`)
    * __Create Activities__ (`POST /v1/work/activities/multi_create`)
    * __Update Activity by ID__ (`PUT /v1/work/activities/{id}`)
    * __Update Activities__ (`POST /v1/work/activities/multi_update`)
* Enhanced the following Staffing Dashboard Settings API operations with an `automaticBreakPlacement` property in the request payload, which allows breaks to be adjusted automatically when shifts are added to the Staffing Dashboard: (WFD-133966)
    * __Retrieve Staffing Dashboard Settings by ID__ (`GET /v1/scheduling/setup/staffing_dashboard_settings/{id}`)
    * __Retrieve All Staffing Dashboard Settings or by Name__ (`GET /v1/scheduling/setup/staffing_dashboard_settings?name={name}`)
    * __Retrieve Staffing Dashboard Settings__ (`POST /v1/scheduling/setup/staffing_dashboard_settings/multi_read`)
    * __Update Staffing Dashboard Settings by ID__ (`PUT /v1/scheduling/setup/staffing_dashboard_settings/{id}`)
    * __Update Staffing Dashboard Settings__ (`POST /v1/scheduling/setup/staffing_dashboard_settings/multi_update`)
    * __Create Staffing Dashboard Settings__ (`POST /v1/scheduling/setup/staffing_dashboard_settings/multi_create`)
* Enhanced the following Paycode Edits for Scheduling API operations with an `assignBreaks` property in the request payload, which allows breaks to be adjusted automatically when pay code edits are added: (WFD-133966)
    * __Create PCE with Options__ (`POST /v1/scheduling/schedule/pay_code_edits/apply_create`)
    * __Create Paycode Edits with Options (Deprecated)__ (`POST /v1/scheduling/schedule/pay_code_edits/import`)
    * __Create Paycode Edits with Options__ (`POST /v1/scheduling/schedule/pay_code_edits/apply_import`)
* Enhanced the following Request Subtypes API operations with an `automaticBreakPlacement` query parameter or property in the request payload, which allows breaks to be adjusted automatically when pay code edits are added: (WFD-133966)
    * __Retrieve Request Subtype by ID__ (`GET /v1/scheduling/setup/request_subtypes/{id}`)
    * __Retrieve Request Subtype by Name__ (`GET /v1/scheduling/setup/request_subtypes/?name={name}`)
    * __Retrieve Request Subtypes__ (`POST /v1/scheduling/setup/request_subtypes/multi_read`)
* Altered the following Activity Profiles API operations to make the `multiStopVariance` property read-only in the request payload and always returns a fixed value of 3 in the response body. Backwards compatibility is maintained as the operation still accepts `multiStopVariance` in the request payload, but it continues to have no effect. (WFD-132346)
    * __Create Activity Profile__ POST (`/v1/work/activity_profiles`)
    * __Retrieve Activity Profile by ID__ (`GET /v1/work/activity_profiles/{id}`)
    * __Update Activity Profile by ID__ (`PUT /v1/work/activity_profiles/{id}`)
    * __Retrieve Activity Profiles__ (`POST /v1/work/activity_profiles/multi_read`)
    * __Create Activity Profiles__ (`POST /v1/work/activity_profiles/multi_create`)
    * __Update Activity Profiles__ (`POST /v1/work/activity_profiles/multi_update`)
* Enhanced the  __Retrieve Asynchronous Computed Pending Historical Corrections by Key__ (`GET /v1/timekeeping/pending_historical_corrections/compute/{id}/results`) API operation with a `position` object reference in the response body that appears only when the Multiple Assignments feature is enabled. (DIM-335522)
* Enhanced the __Retrieve Open Shift Requests as Manager__ (`POST /v1/scheduling/open_shift_requests/multi_read`) API operation to add an optional `statuses` parameter to the `employees` array that contains a list of statuses that filter the open shift requests. (WFD-137444)
* Enhanced the __Retrieve Generic Jobs by Reference__ (`POST /v1/commons/jobs/multi_read`) API operation with a `modifiedSince` property in the `multiReadOptions` object to filter generic jobs and location types that were changed after the date specified in the new property. (DIM-363726)
* Enhanced the following API operations with support for the `persistentId` property in their request and/or response bodies: (DIM-375015)
    * __Retrieve Cost Centers__ (`POST /v1/commons/cost_centers/multi_read`)
    * __Create Cost Centers__ (`POST /v1/commons/cost_centers/multi_create`)
    * __Update Cost Centers__ (`POST /v1/commons/cost_centers/multi_update`)
    * __Retrieve Paginated List of Cost Centers__ (`POST /v1/commons/cost_centers/apply_read`)
    * __Retrieve All Cost Centers__ (`GET /v2/commons/cost_centers`)
    * __Retrieve Cost Center by ID__ (`GET /v2/commons/cost_centers/{id}`)
    * __Retrieve Labor Category Entries__ (`POST /v1/commons/labor_entries/multi_read`)
    * __Create Labor Category Entries__ (`POST /v1/commons/labor_entries/multi_create`)
    * __Update Labor Category Entries__ (`POST /v1/commons/labor_entries/multi_update`)
    * __Retrieve Labor Category Entry by ID__ (`GET /v2/commons/labor_entries/{id}`)
    * __Retrieve Labor Category Entries by Category ID__ (`GET /v2/commons/labor_entries?categoryId`)
* Enhanced the __Retrieve All Labor Categories or by Criteria__ (`GET /v2/commons/labor_categories`) API operation with a `modified_since` query parameter to filter labor categories that were changed after the date specified in the new property. (DIM-375015)
* Enhanced the following Display Profiles API operations with an optional `hidePunchTileMobile` Boolean property in the request payload that defaults to `false`: (DIM-369188)
    * __Create Display Profile__ (`POST /v1/commons/display_profiles`)
    * __Create Display Profiles__ (`POST /v1/commons/display_profiles/multi_create`) 
    * __Update Display Profile by ID__ (`PUT /v1/commons/display_profiles/{id}`) 
    * __Update Display Profiles__ (`POST /v1/commons/display_profiles/multi_update`) 
* Enhanced the following Schedule Builder Settings API operations with an optional `blockingShiftRolloutType` property in the request payload and response body: (DIM-371647)
    * __Retrieve Schedule Builder Settings__ (`GET /scheduling/schedule_builder_settings`)
    * __Retrieve Schedule Builder Settings by ID__ (`GET /v1/scheduling/schedule_builder_settings/{id}`)
    * __Update Schedule Builder Settings by ID__ (`PUT /v1/scheduling/schedule_builder_settings/{id}`)
* Enhanced the following Labor Forecast Limits API operations with an optional `optimizeMinHeadCount` Boolean property in the request payload and response body: (DIM-371630)
    * __Retrieve Labor Forecast Limit by Name__ (`GET /v2/forecasting/labor_forecast_limits`)
    * __Retrieve Labor Forecast Limit by ID__ (`GET /v2/forecasting/labor_forecast_limits/{id}`)
    * __Create Labor Forecast Limit__ (`POST /v2/forecasting/labor_forecast_limits`)
    * __Create Labor Forecast Limits__ (`POST /v2/forecasting/labor_forecast_limits/multi_create`)
    * __Update Labor Forecast Limits__ (`POST /v2/forecasting/labor_forecast_limits/multi_update`)
    * __Retrieve Labor Forecast Limits by Criteria__ (`POST /v2/forecasting/labor_forecast_limits/apply_read`)
    * __Delete Labor Forecast Limits__ (`POST /v2/forecasting/labor_forecast_limits/multi_delete`)
    * __Delete Labor Forecast Limit Effective Version__ (`POST /v2/forecasting/labor_forecast_limits/versions/apply_delete`)
    * __Update Labor Forecast Limit by ID__ (`PUT /v2/forecasting/labor_forecast_limits/{id}`)
* Enhanced the following Report Data Objects API operations with a `timeframeType` property in the request payload and response body: (DIM-348894)
    * __Retrieve All Report Data Objects or by Name__ (`GET /v1/platform/report_dataobjects`)
    * __Retrieve Report Data Object by ID__ (`GET /v1/platform/report_dataobjects/{id}`)
    * __Update Report Data Object by ID__ (`PUT /v1/platform/report_dataobjects/{id}`)
    * __Create Report Data Object__ (`POST /v1/platform/report_dataobjects`)
    * __Delete Report Data Object by ID__ (`DELETE /v1/platform/report_dataobjects/{id}`)
* Enhanced the following Timecard Changes API operations with `position` and `userEnteredPosition` properties in the request payload and response body when the Multiple Assignments feature is enabled: (DIM-318018) 
    * __Retrieve Timecard Changes__ (`GET /v1/timekeeping/timecard/changes`)
    * __Retrieve Timecard Changes for Reports__ (`POST /v1/timekeeping/timecard/changes/reports/multi_read`)
* Enhanced the following API operations to accept a new `Perform-Translation` header that, when true, adds localized objects such as `localizedName`, `localizedDescription`, `localizedQualifier`, and `localizedValue` to the response body as appropriate and where supported: (DIM-339761, DIM-342060)
    * __Retrieve Open Shift Request by ID__ (`GET /v1/scheduling/open_shift_requests/{openShiftRequestId}`)
    * __Retrieve Employee Open Shift Request by ID__ (`GET /v1/scheduling/employee_open_shift_requests/{openShiftRequestId}`)
    * __Retrieve Request Submission Periods__ (`GET /v1/scheduling/employee_open_shift_requests/submission_periods`)
    * __Retrieve Open Request Subtypes__ (`GET /v1/scheduling/employee_open_shift_requests/request_subtypes`)
    * __Retrieve Similar Open Shift Requests by ID__ (`GET /v1/scheduling/open_shift_requests/similar_requests`)
    * __Update Open Shift Request__ (`POST /v1/scheduling/open_shift_requests/apply_update`)
    * __Retrieve Open Shift Requests as Manager__ (`POST /v1/scheduling/open_shift_requests/multi_read`)
    * __Create Employee Open Shift Request__ (`POST /v1/scheduling/employee_open_shift_requests`)
    * __Retrieve Employee Open Shift Requests__ (`POST /v1/scheduling/employee_open_shift_requests/multi_read`)
    * __Update Employee Open Shift Request__ (`POST /v1/scheduling/employee_open_shift_requests/apply_update`)
    * __Create Self-Schedule Request__ (`POST /v1/scheduling/employee_self_schedule_requests`)
    * __Update Self-Schedule Request by ID__ (`PUT /v1/scheduling/employee_self_schedule_requests/{id}`)
    * __Retrieve Self-Schedule Request by ID__ (`GET /v1/scheduling/employee_self_schedule_requests/{id}`)
    * __Retrieve Self-Schedule Requests__ (`POST /v1/scheduling/employee_self_schedule_requests/multi_read`)
    * __Retrieve Open Self-Scheduling Request Subtypes__ (`GET /v1/scheduling/employee_self_schedule_requests/request_subtypes`)
    * __Retrieve Self-Scheduling Request Submission Periods__ (`GET /v1/scheduling/employee_self_schedule_requests/submission_periods`)
    * __Create Shift Swap Request__ (`POST /v1/scheduling/employee_swap`)
    * __Retrieve Shift Swap Request by ID__ (`GET /v1/scheduling/employee_swap/{id}`)
    * __Update Shift Swap Request__ (`POST /v1/scheduling/employee_swap/apply_update`)
    * __Retrieve Shift Swap Requests__ (`POST /v1/scheduling/employee_swap/multi_read`)
    * __Create Shift Cover Request__ (`POST /v1/scheduling/employee_cover_requests`)
    * __Retrieve Shift Cover Request by ID__ (`GET /v1/scheduling/employee_cover_requests/{id}`)
    * __Update Shift Cover Request__ (`POST /v1/scheduling/employee_cover_requests/apply_update`)
    * __Retrieve Shift Cover Requests__ (`POST /v1/scheduling/employee_cover_requests/multi_read`)
    * __Retrieve Shift Cover Request Subtypes__ (`GET /v1/scheduling/employee_cover_requests/request_subtypes`)
    * __Retrieve Submission Periods__ (`GET /v1/scheduling/employee_cover_requests/submission_periods`)
    * __Retrieve Self-Schedule Requests as Manager__ (`POST /v1/scheduling/self_schedule_requests/multi_read`)
    * __Retrieve Shift Swap Request by ID as Manager__ (`GET /v1/scheduling/manager_swap/{id}`)
    * __Update Shift Swap Request as Manager__ (`POST /v1/scheduling/manager_swap/apply_update`)
    * __Retrieve Shift Swap Requests as Manager__ (`POST /v1/scheduling/manager_swap/multi_read`)
    * __Retrieve Shift Cover Request by ID as Manager__ (`GET /v1/scheduling/cover_requests/{id}`)
    * __Update Shift Cover Request as Manager__ (`POST /v1/scheduling/cover_requests/apply_update`)
    * __Retrieve Shift Cover Requests as Manager__ (`POST /v1/scheduling/cover_requests/multi_read`)
    * __Retrieve Employee Time Off Request by ID__ (`GET /v1/scheduling/employee_timeoff/{timeOffRequestId}`)
    * __Retrieve Time Off Request by ID as Manager__ (`GET /v1/scheduling/timeoff/{timeOffRequestId}`)
    * __Retrieve Employee Request Subtype__ (`GET /v1/scheduling/employee_timeoff/request_subtypes`)
    * __Retrieve Request Subtype as Manager__ (`GET /v1/scheduling/timeoff/request_subtypes`)
    * __Update Employee Time Off Request__ (`POST /v1/scheduling/employee_timeoff/apply_update`)
    * __Update Time Off Request as Manager__ (`POST /v1/scheduling/timeoff/apply_update`)
    * __Create Employee Time Off Request__ (`POST /v1/scheduling/employee_timeoff`)
    * __Create Time Off Request as Manager__ (`POST /v1/scheduling/timeoff`)
    * __Retrieve Employee Time Off Requests__ (`POST /v1/scheduling/employee_timeoff/multi_read`)
    * __Retrieve Time Off Requests as Manager__ (`POST /v1/scheduling/timeoff/multi_read`)
    * __Update Time Off Request by ID as Manager__ (`PUT /v1/scheduling/timeoff/{timeOffRequestId}`)
    * __Create Availability Request__ (`POST /v1/scheduling/employee_availability_requests`)
    * __Retrieve Availability Request by ID__ (`GET /v1/scheduling/employee_availability_requests/{id}`)
    * __Retrieve Request Subtypes by Availability Type__ (`GET /v1/scheduling/employee_availability_requests/request_subtypes`)
    * __Retrieve Submission Periods by Availability Type or Subtype__ (`GET /v1/scheduling/employee_availability_requests/submission_periods`)
    * __Update Availability Request State as Manager__ (`POST /v1/scheduling/manager_availability_requests/apply_update`)
    * __Retrieve Availability Requests as Manager__ (`POST /v1/scheduling/manager_availability_requests/multi_read`)
    * __Create Availability Pattern Request__ (`POST /v1/scheduling/employee_availability_pattern_requests`)
    * __Retrieve Availability Pattern Request by ID__ (`GET /v1/scheduling/employee_availability_pattern_requests/{id}`)
    * __Retrieve Request Subtypes by Availability Type for Pattern Requests__ (`GET /v1/scheduling/employee_availability_pattern_requests/request_subtypes`)
    * __Retrieve Submission Periods for Pattern Requests__ (`GET /v1/scheduling/employee_availability_pattern_requests/submission_periods`)
    * __Update Availability Pattern Request State as Manager__ (`POST /v1/scheduling/manager_availability_pattern_requests/apply_update`)
    * __Retrieve Availability Pattern Requests as Manager__ (`POST /v1/scheduling/manager_availability_pattern_requests/multi_read`)
    * __Retrieve Employee Visibility Period by ID__ (`GET /v1/scheduling/setup/employee_visibility_periods/{id}`)
    * __Retrieve All Employee Visibility Periods or by Name__ (`GET /v1/scheduling/setup/employee_visibility_periods`)
    * __Retrieve Employee Visibility Periods__ (`POST /v1/scheduling/setup/employee_visibility_periods/multi_read`)

### Docs updates

The following changes were made to the conceptual documentation:

* Added a new Integers tip to the [Best practices](C:c32c06e7-365a-4cd4-a836-1845a3d56f41) topic explaining that you must provide integers for request properties with the `integer` data type. If you provide floating point numbers then the fractional portion of the number is silently discarded and only the integer is submitted.
* Updated and enhanced [A Guide to Running Payroll](C:5454eb18-64db-4dc9-ba76-d23e34e43410) to incorporate all of the latest changes. The [Stage Payroll](C:e30f2777-ba20-41ca-bc78-4745c4416658) topic contains the most updates. 

### API updates {#APIUpdates}

The following changes were made to the reference documentation:

* Enhanced the __Retrieve Schedule__ (`POST /v1/scheduling/schedule/multi_read`) API operation with greatly expanded documentation for the `scheduleDayList` response property. (WFD-135947)
* Enhanced the __Retrieve Timecard Data for Multiple Employees__ (POST /v1/timekeeping/timecard_metrics/multi_read) API operation's documentation to include new `select` parameters and to describe support for the upcoming Multiple Assignments feature.
* Edits throughout to enhance clarity, add detail, and correct errors and omissions. Refer to the **Corrections and enhancements** section for more details.

## Dimensions R9 {#R9}

The following changes were made to the API and Developer Portal in Dimensions R9.

### General

#### Announcements

_**New authentication method for federated users**_

The [Authenticate with federated user accounts](C:32a1461e-be6d-40f4-a575-215f606d865f) topic has been updated to reflect the new, improved federated authentication process. The legacy federated authentication method described in the [Authenticate with federated user accounts](C:32a1461e-be6d-40f4-a575-215f606d865f) topic has been **deprecated**. 

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The __Create or Update Activities__ (`POST /v1/work/activities/multi_upsert`) API operation sometimes failed with an HTTP status code 500 Internal Server Error due to a race condition. (WFD-135957)
* Various __Persons__ API operations did not correctly process the changed license name from "Work" to "Activities." All affected operations can now consume both naming conventions for this license. (WFD-132608)
* The __Create or Update Persons__ (`POST /v1/commons/persons/multi_upsert`) API operation incorrectly returned an HTTP status code 500 Internal Server Error when the `employeeLaborCategoryProfileName` property was not passed with a valid value in the request payload. The operation now throws a descriptive error. (WFD-136090)
* __Scheduling__ API operations could return an incorrect `errorCode` for certain unknown errors. These operations now return an `errorCode` of WFS-100000 when unknown errors occur. (WFD-135566)
* Enhanced the __Retrieve Job Preferences by Person Number__ (`GET /v1/commons/persons/job_preferences`) API operation to add a new query parameter `full_job_path`, which is a Boolean indicator of whether or not the response returns the full job path for each job. (WFD-136319)
* The __Create Locations__ (`POST /v1/commons/locations/multi_create`) API operation could fail with an error claiming that the newly created revision lacked a unique externalId. (WFD-132447)
* The __Retrieve Locations__ (`POST /v1/commons/locations/multi_read`) API operation returned old Business Structure node names even after the names were successfully updated. The logic now properly updates the locations cache when a nodeType is changed. (WFD-131397)
* The __Import Labor Standards, Tasks, and Task Groups (Deprecated)__ (`POST /v1/forecasting/labor_standard_tasks/import`) API operation allowed a user to alter generic departments in a harmful way. The operation now throws an error message if an API caller attempts to alter a generic department. (WFD-136858)
* The __Retrieve All Labor Standards or by Specification__ (`GET /v1/forecasting/labor_standards`) API operation would time out and throw an HTTP status code 504 error message if too many labor standards existed on a tenant. This operation has been deprecated. If you have a large number of labor standards, use `POST /v1/forecasting/labor_standards/multi_read` instead. (WFD-135769)
* Enhanced the __Retrieve Custom Drivers__ (`POST /v1/forecasting/custom_drivers/multi_read`) API operation to return all custom drivers if an empty object is passed in the request payload. (WFD-125423)
* The __Submit Bulk Download__ (`POST /v1/commons/exports/async`) API operation incorrectly required a Timekeeping license. (WFD-131561)
* Enhanced the model property documentation for the following operations against the __Leave Case Defaults__ API resource to include the following: __Note:__ Scheduled shifts are overridden when `overrideShiftType` is defined. If `overrideShiftType` is not defined then scheduled shifts are not overridden. This property is only applicable when `commitTo` is set to schedule. (WFD-134150)
    * __Update Leave Case Defaults__ (`PUT /v1/leave/leave_cases/defaults`)
    * __Retrieve Leave Case Defaults__ (`GET /v1/leave/leave_cases/defaults`)
    * __Retrieve Leave Case Defaults by ID__ (`GET /v1/leave/leave_cases/{id}/defaults`)
* Enhanced the __Update Leave Admin for Multiple Employees__ (`POST /v1/commons/persons/leave_admin/multi_update`) API operation to return a more descriptive and accurate error message when assigning leave administrators to employees in invalid scenarios. (WFD-133446)
* The __Create Batch Tasks__ (`POST /v1/platform/batch_processing/batch_tasks/multi_create`) API operation did not accept qualifiers when creating batch tasks and did not require some of the elements that are actually required to successfully create batch tasks. (WFD-137642)
* The __Retrieve All Batch Events__ (`GET /v1/platform/batch_processing/batch_events`) API operation did not return all of the batch events configured in the system. (WFD-136949)
* Enhanced the documentation for the __Retrieve Notifications__ (`GET /v1/commons/notifications`) API operation to clarify that the notifications returned are limited to the access privileges of the logged-in user even when specifying a list of users by including a Hyperfind as a query parameter. (WFD-136384)
* In rare circumstances, a user could encounter an authentication error when attempting to access the Developer Portal from the UI. (WFD-135654)
* The __Update Batch Events__ (`POST /v1/platform/batch_processing/batch_events/apply_update`) API operation did not accept qualifiers when updating batch events. (WFD-135425)
* The __Update Multiple Persons__ (`POST /v1/commons/persons/multi_update`) API operation incorrectly returned an HTTP status code 401 error when submitting an incorrectly formatted request payload. (WFD-135095)
* The __Update Schedule for Multiple Employees__ (`POST /v1/scheduling/schedule/multi_update`) API operation incorrectly returned a WCO-115003 error when creating multiple scheduled pay code edits. (WFD-135412)
* The __Update Schedule__ (`POST /v1/scheduling/schedule`) API operation intermittently threw incorrect errors when adding pay codes to the schedule. (WFD-134551)
* After R8 Update 2, the __Update Schedule__ (`POST /v1/scheduling/schedule`) API operation intermittently threw a WFS-102409 error when updating a pay code edit. (WFD-133834)
* Enhanced the __Retrieve Time Off Requests as Manager__ (`POST /v1/scheduling/timeoff/multi_read`) API operation to allow the caller to pass a Hyperfind query in the request payload. (WFD-121441)
* Enhanced the __Retrieve Timecard Data for Multiple Employees__ (`POST /v1/timekeeping/timecard_metrics/multi_read`) API operation to add ISR_DAILY and ISR_SUMMARY as possible values for the `select` request property. (WFD-139148)
* The __Retrieve Timecard Data for Multiple Employees__ (`POST /v1/timekeeping/timecard_metrics/multi_read`) API operation threw an HTTP status code 404 error when it encountered certain improperly configured pay codes. (WFD-137833)
* Enhanced the `snapshotDate` and `snapshotDateTime` property descriptions to clearly state which API operations accept these properties in their request payloads. (WFD-137657)
* In rare circumstances, the __Retrieve Timecard Data for Multiple Employees__ (`POST /v1/timekeeping/timecard_metrics/multi_read`) API operation would omit the Accrual Summary and the Daily Summary from the response. (WFD-136861)
* In certain circumstances, the __Retrieve Punches in Real Time__ (`POST /v1/timekeeping/punches/apply_read`) API operation did not return the correct override type for a punch. (WFD-136762)
* The __Create Time Off Request as Manager__ (`POST /v1/scheduling/timeoff`) API operation responded slowly when the request payload did not include a pay code edit from Schedule. (WFD-129520)
* The __Update Employment Term Versions__ (`POST /v1/timekeeping/setup/employment_terms/versions/apply_upsert`) API operation incorrectly threw an error when a valid but null pay code was included in the request payload. (WFD-132150)
* The `orderBy` property was incorrectly displayed in the following API operations' request payloads: (WFD-134629)
    * __Retrieve Timecard Data for Multiple Employees__ (`POST /v1/timekeeping/timecard_metrics/multi_read`)
    * __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`)
    * __Retrieve Timecards as Employee__ (`POST /v1/timekeeping/employee_timecard/multi_read`)
* Enhanced the __Apply Updates to Accrual Balances for Multiple Employees__ (`POST /v1/timekeeping/accruals/updates`) API operation to include a `formatForTransactionAssistant` request property to allow the transaction assistant to better parse this operation's partial success responses. (WFD-134877)
* The __Retrieve All Work Rules__ (`GET /v1/timekeeping/setup/full_work_rules`) API operation did not return Rest Between Shift rules in the response. (WFD-135421) 
* The __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`) API operation did not return overtime details when the request payload `select` property contained OVERTIME_DETAILS. (WFD-136166)
* Enhanced the following API operations to support the following entities: `laborCategories`, `costCenter`, `workRule`, `orgJob`, and `emptyTransfer`: (DIM-282613)
    * __Retrieve Timecard as Manager__ (`GET /v1/timekeeping/timecard`) (applicable only when the `select` query parameter is `ACTIVITY_SEGMENTS` or `ACTIVITY_SHIFTS`)
    * __Retrieve Timecard as Employee__ (`GET /v1/timekeeping/employee_timecard`) (applicable only when the `select` query parameter is `ACTIVITY_SEGMENTS` or `ACTIVITY_SHIFTS`)
    * __Update Timecard as Manager__ (`POST /v1/timekeeping/timecard`)
    * __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`)
    * __Update Timecard as Employee__ (`POST /v1/timekeeping/employee_timecard`)
    * __Retrieve Timecards as Employee__ (`POST /v1/timekeeping/employee_timecard/multi_read`)
* Enhanced the __Create Team Definition__ (`POST /v1/scheduling/setup/team_definition`) API operation to allow null values to be passed for either the entire `absenceQuotas` object or for the `quota` object within `absenceQuotas`. Also enhanced the __Retrieve Guided Recommendations__ (`POST /v1/scheduling/time_off_request_guided_recommendations/apply_read`) API operation to allow the `thresholdStatus` property to accept a value of `NO_COLOR`. (DIM-334021)
* Enhanced the __Update Schedule for Multiple Employees__ (`POST /v1/scheduling/schedule/multi_update`) API operation to allow you to create paycode edits with options using the new `createWithOptions` request array. (DIM-322789)
* Enhanced the following __Forecast Planner Settings__ API operations to add the `defaultVolumeForecastInterval` property to the request and response models: (DIM-371376)
    * __Retrieve a Forecast Planner Setting by ID__ (`GET /v1/forecasting/forecast_planner_settings/{id}`)
    * __Retrieve All Forecast Planner Settings or by Name__ (`GET /v1/forecasting/forecast_planner_settings`)
    * __Retrieve Forecast Planner Settings__ (`POST /v1/forecasting/forecast_planner_settings/multi_read`)
    * __Create a Forecast Planner Setting__ (`POST /v1/forecasting/forecast_planner_settings/`)
    * __Create Forecast Planner Settings__ (`POST /v1/forecasting/forecast_planner_settings/multi_create`)
    * __Update a Forecast Planner Setting by ID__ (`PUT /v1/forecasting/forecast_planner_settings/{id}`)
    * __Update Forecast Planner Settings__ (`POST /v1/forecasting/forecast_planner_settings/multi_update`)
* Enhanced the __Create Team Definition__ (`POST /v1/scheduling/setup/team_definition`) and __Update Team Definition by ID__ (`PUT /v1/scheduling/setup/team_definition/{id}`) API operations to add a `quotaAsPercentage` Boolean request property that determines whether or not the team definition defines the quota as a percentage or a whole number. (DIM-155638)
* Enhanced the __Import Volume Forecast__ (`POST /v2/forecasting/volume_forecast/import`) API operation by adding the `intervalAmounts` property to the `volumeForecasts` array. This optional property contains a string of up to 96 comma-separated values representing each 15 minute interval in a day. (DIM-318085)
* Enhanced the following multi_upsert and the apply_upsert API operations with an `include_version` query parameter and the multi_read operation with an `includeVersion` property within `multiReadOptions` in the request payload. These new properties, when set to false, allow you to omit the `version` property from the request payload. (WFD-136715)
    * __Update Custom Driver Values__ (`POST /v1/forecasting/custom_driver_values/apply_upsert`)
    * __Update Values for Multiple Custom Drivers__ (`POST /v1/forecasting/custom_driver_values/multi_upsert`)
    * __Retrieve Custom Driver Values__ (`POST /v1/forecasting/custom_driver_values/multi_read`)
* Enhanced the following API operations with a new `badgeLoginMask` Boolean property to the request payload. This property allows you to mask the Kiosk display of badge ID in the same way a password is masked. (DIM-333097)
    * __Create Kiosk Configuration__ (`POST /v1/timekeeping/setup/kiosks`)
    * __Retrieve Kiosk Configuration by ID__ (`GET /v1/timekeeping/setup/kiosk/{id}`)
    * __Retrieve All Kiosk Configurations__ (`GET /v1/timekeeping/setup/kiosks`)
    * __Update Kiosk Configuration by ID__ (`PUT /v1/timekeeping/setup/kiosks/{id}`)
* Enhanced the following API operations with a new `overtimeRule` object reference in the work hour definition: (DIM-330417)
    * __Create Employment Term__ (`POST /v1/timekeeping/setup/employment_terms`)
    * __Update Employment Term Versions__ (`POST /v1/timekeeping/setup/employment_terms/versions/apply_upsert`)
    * __Retrieve Employment Terms__ (`POST /v1/timekeeping/setup/employment_terms/multi_read`)
    * __Update Employment Term by ID__ (`PUT /v1/timekeeping/setup/employment_terms/{id}`)
    * __Retrieve All Employment Terms__ (`GET /v2/timekeeping/setup/employment_terms`)
    * __Retrieve Employment Term by ID__ (`GET /v2/timekeeping/setup/employment_terms/{id}`)
* Enhanced the __Stage Payroll Asynchronously__ (`POST /v1/commons/payroll/staging/async`) API operation with a new `filterBy` property within the `processBasedOn` object. This property accepts `JOB`, `LABOR_CATEGORY`, or `COST_CENTER` when the `processBasedOn` `type` is `WORKED`. (DIM-334906)
* Enhanced the following API operations with a new `licenseTypeName` property within `employeeExtension` > `licenseTypeList`: (DIM-332112)
    * __Retrieve Persons__ (`POST /v1/commons/persons/extensions/multi_read`)
    * __Retrieve Person by Extension__ (`GET /v1/commons/persons/{extensionType}`)
    * __Retrieve All Extensions__ (`GET /v1/commons/persons/extensions`)
* Updated the following API operations to correctly return only the data for the specified date range (and to no longer include flanking days). These operations now behave consistently with the UI and the Activity Totals API operations: (WFD-132427)
    * __Retrieve Timecard as Manager__ (`GET /v1/timekeeping/timecard?select=ACTIVITY_TOTALS`)
    * __Retrieve Timecard as Employee__ (`GET /v1/timekeeping/employee_timecard?select=ACTIVITY_TOTALS`)
    * __Retrieve Timecards as Employee__ (`POST /v1/timekeeping/employee_timecard/multi_read`)
    * __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`)
* Enhanced the following API operations such that the `scheduleTagColor` property is now optional and, when omitted, inherits the color from the tag definition: (WFD-130158)
    * __Create Schedule Tag__ (`POST /v1/scheduling/schedule/schedule_tags`)
    * __Update Schedule Tag by ID__ (`PUT /v1/scheduling/schedule/schedule_tags/{id}`)

### Docs updates

The following changes were made to the conceptual documentation:

* Added the [People Editor Cross-Reference](C:29ee71dd-3567-43a2-998e-647233ea4fd5) topic, which contains a table with all People Information fields in the UI cross referenced with the specific API operation and property that allows you to update each field using the API. 
* The original federated authentication method described in the [Authenticate with federated user accounts](C:32a1461e-be6d-40f4-a575-215f606d865f) topic has been **deprecated**. Documentation has been updated to reflect the new, improved federated authentication process.
* Updated the **Hyperfind service limits** section of the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic to add a note about the `threshold` request property, which limits the number of employees that can be processed in a single request.
* Created [A Guide to Person Assignments](C:e7763b79-01c0-4e0c-bf0c-b7cffaded3c0) and added 11 new assigments to the [Aggregated Person Assignments](C:57f8f4ab-2dcf-4e21-95ce-0b6920af7e4c) guides:
    * [Certification Assignments](C:c98e0327-9b74-4e21-8c57-a48d4ab45109)
    * [Employee Job Preferences](C:bcd24b6f-7384-4726-9464-f9ffe4b2641f)
    * [Employee Preferences](C:b5f72c35-202d-4021-83ae-b1e44dafa8c4)
    * [Employee Tag Assignments](C:1de622fc-fed8-45d0-affe-7a2e152d120f)
    * [Employment Term Assignments](C:85255926-62b9-496c-8fb4-949b82a1f46e)
    * [Pattern Template Profile Assignments](C:4389e657-abd3-45f4-9682-bcaf90e64658)
    * [Schedule Group Profile Assignments](C:6ad65b99-c5e9-4b3a-b76b-6aeb368973a9)
    * [Schedule Rule Override Assignments](C:ebfc6bc0-c9e4-427e-b78a-e1c9442e9b13) 
    * [Shift Template Profile Assignments](C:555ce793-0ba7-4fa6-9da8-ba2982be76b7)
    * [Skill Assignments](C:f418163b-822e-4c0b-9266-9c50cdd4a573)    
    * [Worker Type Assignments](C:955e0f3a-06a1-48b4-a561-033e31e371e5)

### API updates {#APIUpdates}

The following changes were made to the reference documentation:

* Moved the following API resources to the new subdomain Labor Category Setup, which is located in Common Resources II:
    * Labor Categories
    * Labor Category Entries
    * Labor Category List Assignments
    * Labor Category Lists
    * Labor Category Profiles
    * Labor Entry Lists
* The Aggregated Person Assignments resource now supports 11 new assignments (refer to [Aggregated Person Assignments](C:57f8f4ab-2dcf-4e21-95ce-0b6920af7e4c) for details):
    * [Certification Assignments](C:c98e0327-9b74-4e21-8c57-a48d4ab45109)
    * [Employee Job Preferences](C:bcd24b6f-7384-4726-9464-f9ffe4b2641f)
    * [Employee Preferences](C:b5f72c35-202d-4021-83ae-b1e44dafa8c4)
    * [Employee Tag Assignments](C:1de622fc-fed8-45d0-affe-7a2e152d120f)
    * [Employment Term Assignments](C:85255926-62b9-496c-8fb4-949b82a1f46e)
    * [Pattern Template Profile Assignments](C:4389e657-abd3-45f4-9682-bcaf90e64658)
    * [Schedule Group Profile Assignments](C:6ad65b99-c5e9-4b3a-b76b-6aeb368973a9)
    * [Schedule Rule Override Assignments](C:ebfc6bc0-c9e4-427e-b78a-e1c9442e9b13) 
    * [Shift Template Profile Assignments](C:555ce793-0ba7-4fa6-9da8-ba2982be76b7)
    * [Skill Assignments](C:f418163b-822e-4c0b-9266-9c50cdd4a573)    
    * [Worker Type Assignments](C:955e0f3a-06a1-48b4-a561-033e31e371e5)

## Dimensions R8 Update 3 {#R8U3}

The following changes were made to the API and Developer Portal in Dimensions R8 Update 3.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The __Retrieve All Timekeeping Pay Rules (Deprecated)__ (`GET /v1/timekeeping/setup/payrules`) API operation incorrectly threw an error when the number of pay rules in the system exceeded 1,500. (WFD-129144)
* Added additional validation to the __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`) API operation to prevent rare combinations of request parameters from causing unusual behavior. (WFD-128997)
* When a historical correction's historical date was the same as its effective date, the __Save Pending Historical Corrections__ (`POST /v1/timekeeping/pending_historical_corrections/save/async`) API operation would incorrectly generate duplicate historical corrections. (WFD-130614)
* In certain rare circumstances, the __Retrieve Persons__ (`POST /v1/commons/persons/extensions/multi_read`) API operation returned the incorrect work rule associated with a pay rule. (WFD-130864)
* A code error caused the Developer Portal to display an incorrect JSON schema for the __Update Employment Term Version__ (`POST /v1/timekeeping/setup/employment_terms/versions/apply_upsert`) API operation. (WFD-131957)
* Enhanced the performance of processing large request batches in the __Create Schedule Tags__ (`POST /v1/scheduling/schedule/schedule_tags/multi_create`) API operation. (WFD-128742) 
* Enhanced the performance of the __Retrieve Schedule Audits__ (`POST /v1/scheduling/audits/multi_read`) API operation. (WFD-128088)
* The __Retrieve Locations__ (`POST /v1/commons/locations/multi_read`) API operation returned a generic error message when certain backend services failed. This operation now has enhanced logging to return more descriptive errors. (WFD-130616)
* __The Create or Update Known Places__ (`POST /v1/commons/known_places/multi_upsert`) API operation would indicate success even when some transactions failed when transactions failed due to improperly formatted JSON in the request payload. (WFD-130680)
* __The Update Employee Schedule Pattern__ (`POST /v1/scheduling/employee_schedule_patterns/apply_update`) API operation incorrectly threw a generic error message when certain validation errors occurred. (WFD-131181)
* The __Retrieve Punches in Real Time__ (`POST /v1/timekeeping/punches/apply_read`) API operation now has a datasource qualifier property that shows where punches originate. (WFD-123904, DIM-317898)
* Enhanced __all operations__ against the __Schedule Change Criteria API resource__ by adding the `shiftLocationChanged` and `locationType` properties to their request and response models. (DIM-207671)
* Enhanced the following API operations' partial success validation such that partial success is only processed for expected errors (locked day, expired job, and so on). If an unexpected error occurs during business validation, the entire operation fails and partial success is not processed. (WFD-128015)
    * __Create Employment Terms PCEs__ (`POST /v1/scheduling/employment_terms_schedule/pay_code_edits/apply_create`)
    * __Update Employment Terms PCEs__ (`POST /v1/scheduling/employment_terms_schedule/pay_code_edits/apply_update`)
    * __Create Group Shifts__ (`POST /v1/scheduling/schedule/groups/shifts/apply_create`)
    * __Update Group Shifts__ (`POST /v1/scheduling/schedule/groups/shifts/apply_update`)
    * __Create Group PCEs__ (`POST /v1/scheduling/schedule/groups/pay_code_edits/apply_create`)
    * __Update Group PCEs__ (`POST /v1/scheduling/schedule/groups/pay_code_edits/apply_update`)
* Enhanced the __Update Open Shift Request__ (`POST /v1/scheduling/open_shift_requests/apply_update`) API operation's `event` property to add a new enumeration, `comment_by_manager`, which allows a manager to add a comment to an open shift request. (DIM-300115)
* Enhanced the __Execute Hyperfind Query__ (`POST /v1/commons/hyperfind/execute`) API operation to add the `includeTerminatedInRangeForLocations` request property, which is a Boolean indicator of whether or not to include terminated employees in the date range for locations. (DIM-276188)
* Enhanced the __Retrieve Timecard Data for Multiple Employees__ (__POST /v1/timekeeping/timecard_metrics/multi_read__) API operation to add the `filterByAnchorDate` request property. When false, this Boolean allows an employee's Accrual Summary to be returned in a manner consistent with the existing report format. (WFD-128765)
* Enhanced the __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`) and __Retrieve Timecards as Employee__ (`POST /v1/timekeeping/employee_timecard/multi_read`) API operations by adding the `totalsRollupBy` request property, which allows you to specify the level by which totals are rolled up. Supported values are ALL, SHIFT, TIMEITEM, DAILY, PERIOD_TO_DATE, ACTIVITY_EVENT, and RAW. (WFD-131316)
* Enhanced the __Retrieve Payroll Data for HCM__ (`POST /v1/hcm/payroll/data/apply_read`) API operation by adding the `includeWorkedCostCenter` request property, which allows you to include the worked cost center in the aggregation key and in the cost center array. (DIM-279226)
* Enhanced all API operations that return the `punchGeoLocation` object (such as __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`) by adding `geofenceMethod` and `knownPlaceName` to the `punchGeoLocation` object. (DIM-277503)
* Enhanced the __Retrieve Net Changes for Activity Shifts__ (`POST /v1/work/activity_shifts/net_changes/multi_read`) API operation to include full object references for each of the following objects in the response: (WFD-129646)
    * `laborCategory`
    * `costCenter`
    * `orgJob`
    * `payCode`
    * `workRule`
* Enhanced the following API operations by increasing the JSON payload size from the default of 1 megabyte to 5 megabytes: (WFD-130391)
    * __Update Results Templates__ (`POST /v1/work/results_templates/multi_update`)
    * __Create Results Templates__ (`POST /v1/work/results_templates /multi_create`)
    * __Update Results Template by ID__ (`PUT /v1/work/results_templates/{id}`)
    * __Create Results Template__ (`POST /v1/work/results_templates`)
* Enhanced the following API operations by adding the PROCESSED_SEGMENTS option to the `select` query parameter and property: (DIM-326168)
    * __Retrieve Timecard as Employee__ (`GET /v1/timekeeping/employee_timecard`)
    * __Retrieve Timecard as Manager__ (`GET /v1/timekeeping/timecard`)
    * __Retrieve Timecards as Employee__ (`POST /v1/timekeeping/employee_timecard/multi_read`)
    * __Retrieve Timecards as Manager__ (`POST /v1/timekeeping/timecard/multi_read`)

### Docs updates

The following changes were made to the conceptual documentation:

* Added [A Guide to Payroll Extraction](C:5454eb18-64db-4dc9-ba76-d23e34e43410) to the [Guides](C:92b16358-756a-41bf-9204-b0aaf7262cfa) section.

### API updates {#APIUpdates}

The following changes were made to the reference documentation:

**Important New Content**

* The **Payroll Staging**, **Payroll Tables**, and **Payroll Export** subdomains have been added to the Dimensions API, greatly enhancing your ability to extract payroll and accruals from the system.

## Dimensions R8 Update 2 {#R8U2}

The following changes were made to the API and Developer Portal in Dimensions R8 Update 2.

### General

#### Announcements

_**FAQ about deprecated API operations**_

This release introduces a topic defining the way we use the term [Deprecated](C:d8b73947-648f-4361-bf1d-ffbd2eac795a) and answering a number of frequently asked questions about our deprecated API operations and their replacement operations.

_**Important updates in the [API updates](#APIUpdates) section**_

Check out the [API updates](#APIUpdates) section for important notes on the new top-level organization of the API reference documentation, significant new content, and for notes regarding our move to document service limits at the operation level whenever it is possible to do so.

_**Introducing a Hyperfind Query timeout limit**_

Hyperfind queries that consistently take more than 5 minutes to execute will be prevented from executing. 

* If a query group is deactivated for this reason, the following error message will display:

```
Execution of this Hyperfind query has been disabled. Simplify the query and try again.
```

* If a query group is consistently resulting in queries that take over 5 minutes, the following error message will display:

```
Execution of your Hyperfind query will exceed the limit of 5 minutes. Simplify the query and try again.
```

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* Enhanced the Bulk Enable Edits (POST /v1/timekeeping/enable_edits/import) and Bulk Timecard Signoffs (POST /v1/timekeeping/signoffs/import) API operations to add the `employeeResponseType` property inside the `options` object. When `detailedPartialSuccess` is true, this property controls whether to return IDs, qualifiers, or refs in partial success responses.
    * If `employeeResponseType` is null, the operation behaves as before and always returns IDs in partial success responses.
    * If `employeeResponseType` is `original`, the partial success response mimics what was passed in the originating request payload. For example, if employees were specified in the request payload using `refs`, the partial success response returns `refs`. If they are specified using `qualifiers`, the partial success response returns `qualifiers`.
    * If `employeeResponseType` is `ids`, `qualifiers`, or `refs`, the partial success response returns `ids`, `qualifiers`, or `refs`, respectively.
* Enhanced the Retrieve All Accrual Profiles (GET /v2/timekeeping/setup/accrual_profiles) API operation to add the `include_accrual_policies` query parameter, which is a Boolean indicator of whether or not to include accrual policies in the response.
* Enhanced the Update Timecard as Manager (POST /v1/timekeeping/timecard) and Update Timecard as Employee (POST /v1/timekeeping/employee_timecard) API operations to add the `onlyReturnChangedEntities` property inside the `do` object, which is a Boolean indicator of whether or not to only return changed entities in the response.
* Enhanced the following API operations to be consistent with the following Dimensions UI behavior: when licenses are assigned to terminated employees, the employment status of the employee changes from terminated to active as of the current date and the license is assigned to the employee. The employee's user account status is set to `Active` and a user role is assigned (employee or manager). Previously, when attempting to assign licenses to terminated employees, these API operations returned an HTTP status code 200 success response but did not actually assign the license or perform any of the actions described above.
    * Create or Update Persons (POST /v1/commons/persons/multi_upsert)
    * Update Multiple Persons (POST /v1/commons/persons/multi_update)
    * Update Person by ID (PUT /v1/commons/persons/{personId})
    * Create Person (POST /v1/commons/persons)
* The Retrieve Activity Totals for Multiple Employees (POST /v1/work/activity_totals/multi_read) API operation's response body did not always include the `processSegmentId` property, which caused integrations to fail.
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation returned "an unexpected non-SQL system error" in certain rare circumstances. The root cause was identified and corrected.
* In rare circumstances, the Retrieve Comments as Manager (GET /v1/commons/comments) API operation would return duplicate comment entries. The root cause was identified and corrected.
* Enhanced the Move Location (POST /v1/commons/locations/apply_update) API operation to add the `showDescendants` Boolean, which ensures the response always returns descendant nodes.
* Resolved a null pointer exception for the Create Locations (POST /v1/commons/locations/multi_create) API operation.
* The Update Multiple Adjustment Driver Settings (POST /v1/forecasting/adjustment_driver_settings/multi_update) API operation incorrectly threw an "ERROR-1007" during certain validation scenarios. The root cause was identified and corrected.
* The Retrieve Static Driver Assignments (POST /v1/forecasting/static_driver_assignments/multi_read) API operation's error messaging has been enhanced to more clearly inform the user when they specify a timeframe that includes locations that are divided in the middle of the week, which is considered a 'broken week.'
* The Retrieve Data (POST /v1/commons/data/multi_read) API operation failed with a "400 Bad Request" error when terminated employees were included in a Hyperfind in the request payload. The root cause was identified and validation logic was corrected.
* The Create PCE with Options (POST /v1/scheduling/schedule/pay_code_edits/apply_create) API operation did not write employee IDs to the transaction assistant when it encountered an error. The root cause was identified and corrected.
* The Apply Updates to Accrual Balances for Multiple Employees (POST /v1/timekeeping/accruals/updates) API operation did not write employee IDs to the transaction assistant when it encountered an error. The root cause was identified and corrected.
* When a null value caused an import of person records to fail, the Transaction Assistant and the Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation showed a generic, uninformative error message. The new message is "This field does not allow a null value. Field name: User Name."
* The Create Paycode Edits with Options (POST /v1/scheduling/schedule/pay_code_edits/apply_import) API operation incorrectly returned a text string for the `durationInMinutes` property instead of the numerical duration value.
* The Retrieve Open Shift Requests as Manager (POST /v1/scheduling/open_shift_requests/multi_read) API operation did not properly execute the statuses array in the request payload. The root cause was identified and corrected.
* In certain circumstances, the Create Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_create) API operation would delete a previous day's shift when applying a schedule pattern to a portion of a week. The root cause was identified and corrected.
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation was incorrectly generating a Hyperfind service limit error even though the number of employees processed in the request payload was under the service limit. The root cause was identified and corrected.
* The Update Shift Template Profile Assignments (POST /v1/commons/persons/shift_template_profiles/multi_update) API operation threw a null pointer exception error when `ShiftTemplateProfile` was null. The root cause was identified and corrected.
* The Update Schedule for Multiple Employees (POST /v1/scheduling/schedule/multi_update) API operation threw null pointer exceptions under certain conditions, which were identified and corrected.
* The Update Schedule (POST /v1/scheduling/schedule) API operation incorrectly required the employee node when specifying a paycode edit. The operation no longer requires the employee node when specifying a paycode edit.
* The Update Schedule for Multiple Employees (POST /v1/scheduling/schedule/multi_update) API operation threw an error when multiple availabilities were created for the same employee on the same day in a single request payload. The API now gracefully handles such requests.
* The Create Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_create) API operation incorrectly accepted values for the `anchorStartDay` property, which has always been documented and intended to be a read-only property. The API now correctly ignores this property in the request payload and instead reads the `anchorStartDay` in the locale policy.
* The Retrieve Timecards as Manager (POST /v1/timekeeping/timecard/multi_read) API operation incorrectly returned an HTTP 500 Internal Server Error when the request payload included terminated employees that met certain rare conditions. The API now gracefully handles these conditions.
* The Retrieve Timecard Data for Multiple Employees (POST /v1/timekeeping/timecard_metrics/multi_read) API operation did not correctly return end-dated but active jobs for historical corrections. The root cause was identified and corrected.
* Enhanced the Create Percentage Allocation Rule (POST /v1/timekeeping/setup/percentage_allocation_rules) and Update Percentage Allocation Rule (PUT /v1/timekeeping/setup/percentage_allocation_rules/{id}) API operations to validate the properties passed within the allocations array.
* The Update Paycode by ID (PUT /v1/timekeeping/setup/pay_codes/{id}) API operation did not correctly update the system with the data specified in the `scheduledHoursType` property. The API now correctly updates the scheduled hours type.
* The Retrieve Timecards as Manager (POST /v1/timekeeping/timecard/multi_read) API operation returned two worked shifts with the same ID when the shift was split at the day divide. The API now returns a single worked shift that crosses the divide and spans on each side of the divide.
* The Retrieve All Accrual Profiles (GET /v2/timekeeping/setup/accrual_profiles) API operation returned the accrual profile name and the accrual code but did not return the accrual policy details. Accrual policy details are now correctly returned.
* The Retrieve Punches in Real Time (POST /v1/timekeeping/punches/apply_read) API operation did not return punches created with a legacy timezone ID that concatenated a real timezone ID with a Daylight Savings Time flag. The API now gracefully handles punches created with a legacy timezone ID.
* Under rare conditions, the Retrieve Timecards as Manager (POST /v1/timekeeping/timecard/multi_read) API operation returned an HTTP status code 500 Internal Server Error. The root cause was identified and corrected via additional validation steps.
* The Create, Update, or Delete Manager Role Assignments (POST /v1/commons/persons/manager_role_assignments/apply_upsert) API operation did not correctly mirror the request payload in the input property of its HTTP Status Code 207 Partial Success response body, which caused issues when the response was consumed by the Transaction Assistant. The input property now correctly reflects the sequence provided in the request payload.
* The Bulk Accrual Reset (POST /v1/timekeeping/accruals/resets) API operation did not correctly process only the latest reset when multiple resets for the same employee, accrual code, and date were specified in the same request payload.

### Docs updates

The following changes were made to the conceptual documentation:

* Added [A Guide to Attestations](C:ac67ee79-7306-4f22-992d-ca6470b6ae79) to the [Guides](C:92b16358-756a-41bf-9204-b0aaf7262cfa) section.
* Removed operation-level service limits across all domains from the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic. Those limits now exist in the reference documentation at the operation level.
* Added information about the Business Structure jobs service limit to the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic.

### API updates {#APIUpdates}

The following changes were made to the reference documentation:

**New Organization**

* Moved the Forecasting setup operations into a new domain named **Forecasting Setup**.
* Moved the Timekeeping timecards operations into a new domain named **Timekeeping Timecards**.
* Moved the Timekeeping bulk operations into a new domain named **Timekeeping Bulk Operations**.
* Moved the person assignments operations out of the **Persons** domain and into a new domain named **Person Assignments**.

**Other Updates**

* Added service limits across all domains to each operation as applicable. Now, only general service limits that apply to whole domains or groups of operations are contained in the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic in the conceptual documentation.
* The **Change Indicators** subdomain has been added to the Dimensions API, greatly enhancing your ability to extract change-over-time data from the system.

## Dimensions R8 Update 1 {#R8U1}

The following changes were made to the API and Developer Portal in Dimensions R8 Update 1.

### General

#### Announcements

_**Version 2 API operations**_

The API has introduced the first set of version 2 API operations. We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality.

_**End-of-life API operations**_

The following API operations have reached end-of-life and have been removed entirely from the system:

* GET /v1/forecasting/hours_operation
* POST /v1/forecasting/hours_operation
* GET /v1/forecasting/hours_operation/{id}
* PUT /v1/forecasting/hours_operation/{id}
* DELETE /v1/forecasting/hours_operation/{id}
* POST /v1/forecasting/hours_operation/multi_create
* POST /v1/forecasting/hours_operation/multi_update
* POST /v1/forecasting/hours_operation/multi_read
* POST /v1/forecasting/hours_operation/multi_delete

If you are currently using any of these operations, the following now-deprecated replacements work in exactly the same way and can be used immediately as-is, aside from updating the URL:

* GET /v1/commons/hours_operation
* POST /v1/commons/hours_operation
* GET /v1/commons/hours_operation/{id}
* PUT /v1/commons/hours_operation/{id}
* DELETE /v1/commons/hours_operation/{id}
* POST /v1/commons/hours_operation/multi_create
* POST /v1/commons/hours_operation/multi_update
* POST /v1/commons/hours_operation/multi_read
* POST /v1/commons/hours_operation/multi_delete

_**Note:** As of R8 Update 1, you can update your implementations more fully to use the version 2 Hours of Operation resource. Refer to the [Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445) topic for more information._

_**Introducing effective dating support in version 2 Forecasting API operations**_

The following version 2 Forecasting API resources introduce effective dating support:

* Labor Forecast Limits (/v2/forecasting/labor_forecast_limits)
* Hours of Operation (/v2/commons/hours_operation)
* Labor Tasks (/v2/forecasting/tasks)
* Task Groups (/v2/forecasting/task_groups)

_**Note:** The deprecated version 1 operations against these API resources (for example, operations against /v1/commons/hours_operation) only work with entities containing a single effective version._

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* Enhanced the documentation for the Import Labor Standards, Tasks, and Task Groups (POST /v1/forecasting/labor_standard_tasks/import) API operation to better describe how to compress or truncate traffic pattern distribution using the StandardDistributionSettings.standardDistributionType property.
* Enhanced the Guides > A Guide to People Information > Person Assignments > Skill Assignments topic to indicate that only skill assignments with an effective date in the future can be deleted.
* The Retrieve Activity Transactions (POST /v1/work/activity_transactions/multi_read) API operation reported activity totals in whole hours only, which did not match the UI. This operation now reports activity totals at the same level of granularity provided by the UI.
* Enhanced certain operations against the Timecards API resource (/v1/timekeeping/employee_timecard and /v1/timekeeping/timecard) to include full object references to associated "activity" objects.
* The Create or Update Location Set (POST /v1/commons/location_sets/apply_upsert) API operation did not gracefully handle certain request payloads when passing the "removeNodeRefs" property. The operation will now correctly perform a removal of specified nodes or pass an explanatory error message.
* The Update Values for Multiple Adjustment Drivers (POST /v1/forecasting/adjustment_drivers/multi_upsert) API operation in some cases passed an HTTP status code 400 error code with an HTTP status code 207 response body. Also, this operation did not allow the caller to specify a version of the Adjustment Driver object. The operation now returns the correct HTTP status code for 207 "Partial Success" errors and has been enhanced with an "includeVersion" property that allows the caller to specify the version.  
* The Retrieve Volume Driver Assignments (POST /v1/forecasting/volume_driver_assignments/multi_read) API operation would sporadically time out due to a caching issue. The caching issue has been corrected.
* Updated numerous Forecasting API operations to support the standard "end of time" date in request payload specifications.
* The Retrieve Hyperfind Queries for Current User (GET /v1/commons/hyperfind) API operation did not return the home Hyperfind query when the "usage_type" query paramater was passed with "Home" specified. The operation now returns the correct results for all enumerations of the "usage_type" query parameter. 
* The Create or Update Delegate Profiles (POST /v1/commons/delegate_profiles/multi_upsert) API operation would incorrectly return an HTTP status code 200 response even when some of the specified delegates were not assigned to a profile. The operation now correctly passes an HTTP status code 207 "Partial Success" response when some delegate assignments failed and others succeeded.
* The Create Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_create) API operation returned an incorrect error message when the "timePeriodType" property was not specified. The operation now returns the correct error message.
* The Update Group Memberships for Multiple Employees (POST /v1/commons/persons/schedule_groups/multi_upsert) API operation did not correctly honor the "removeFromOtherGroups" Boolean property. The property now behaves as intended.
* The Create Shift Template (POST /v1/scheduling/shift_templates) API operation would sometimes take an unusually long time to complete. The root cause was identified and corrected.
* In rare circumstances, the Create PCE with Options (POST /v1/scheduling/schedule/pay_code_edits/apply_create) API operation could throw a nullPointerException error. The root cause was identified and corrected.
* The Modify Assignments for Multiple People (POST /v1/commons/persons/assignments/multi_upsert) API operation could not end-date a currently active, effective-dated Schedule Group assignment when that assignment's name matched an effective-dated assignment that already ended in the past. The root cause was identified and corrected.
* The Bulk Create or Update Workload Patterns (POST /v1/scheduling/workload_patterns/multi_upsert) API operation incorrectly returned a nullPointerException when an empty string or 'null' was passed into the "count" key of a workload object. The root cause was identified and corrected.
* Corrected an issue where the actions specified in a Create Group Schedule Pattern (POST /v1/scheduling/group_schedule_patterns/apply_create) API operation would not fully complete if it was immediately followed by an Update or Remove Group Schedule Patterns (POST /v1/scheduling/group_schedule_patterns/apply_update) API operation. 
* Due to a caching issue, the Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation could return incorrect Schedule Group assignments. The root cause was identified and corrected.
* The Retrieve Timecard Data for Multiple Employees (POST /v1/timekeeping/timecard_metrics/multi_read) API operation did not correctly filter the results based on the accrual code passed in the request payload. The operation now passes all results if no accrual code is specified or filters the result set by the specified accrual code. 
* The Retrieve All Overtime Rules (GET /v1/timekeeping/setup/overtime_rules) API operation displayed an incorrect response model on the Developer Portal. The root cause was identified and the Developer Portal now displays the correct response model.
* The Retrieve All Work Rules (GET /v1/timekeeping/setup/full_work_rules) API operation would sometimes return incorrect information when the majority or zone rules were changed in the UI. The root cause was identified and corrected.
* The Create Shift Templates (POST /v1/scheduling/shift_templates) API operation returned an incorrect error message when passing a read-only property in the request payload. The operation now gracefully handles such errors and has been enhanced with more descriptive error messaging.

### Docs updates

The following changes were made to the conceptual documentation:

* Added __Forecasting service limits__ to the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic.
* Added a version 2 subsection to each new release in the [Version history](C:2d250085-ed39-496b-92fd-5f6a66d3f357) topic.
* Added a [Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445) topic that correlates Version 2 resources and operations with the deprecated Version 1 resources and operations they replace.

### API updates

The following changes were made to the reference documentation:

* Deprecated the version 1 resources and operations that have been replaced by version 2 resources and operations. Deprecated operations note that they are deprecated and point to their replacements. Refer to the [Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445) topic for more information.
* Enhanced the Import Labor Standards, Tasks, and Task Groups (POST /v2/forecasting/labor_standard_tasks/import) and Import Labor Standards, Tasks, and Task Groups (Deprecated) (POST /v1/forecasting/labor_standard_tasks/import) API operations to support combined labor distribution.
* Restored the R7 Update 4 enhancements that dropped out of the first Dimensions R8 release.
* Updated the Employee Availability Requests and Manager Availability Requests resources to correct the allowable values for the "event" property in the request payload and to provide more details about how the states behave for create and update state operations.
* Enhanced the Predictive Scheduling Rules (operations against /v1/scheduling/setup/predictive_scheduling_rules) API resource to include a "priority" property. This field defaults to a value of 10 when not specified in the payload.
* Updated the documentation for several operations against the Timecards resource to clearly state that the dateRange object is required, and, for the GET operations, to note that either a symbolic period or a date range consisting of a start date and end date is required.
* Enhanced the Retrieve Data (POST /v1/commons/data/multi_read) API operation to support Healthcare Analytics data retrieval.
* To support primary job assignment by providing a Business Structure location's full name or persistent ID, added a new request payload property "orgPathByCriteria" to the following API operations:
    * Create or Update Persons (POST /v1/commons/persons/multi_upsert)
    * Create Multiple Persons (POST /v1/commons/persons/multi_create)
    * Update Multiple Persons (POST /v1/commons/persons/multi_update)
    * Create Person (POST /v1/commons/persons)
    * Update Person by ID (PUT v1/commons/persons/{personId})
* Enhanced the following API operations to allow retrieving employee and manager punches and approvals by the Associate Object ID (AOID) or a combination of the AOID and the Client Object ID (COID):
    * Retrieve Timecard as Employee (GET /v1/timekeeping/employee_timecard)
    * Retrieve Timecard as Manager (GET /v1/timekeeping/timecard)
    * Retrieve Timecard Approvals as Manager (GET /v1/timekeeping/timecard_approvals)

## Dimensions R8 {#R8}

The following changes were made to the API and Developer Portal in Dimensions R8.

### General

#### Announcements

**Enhanced Timecard Metrics Responses with Starting Balance For Accrual Periods**

The Retrieve Timecard Data for Multiple Employees (POST v1/timekeeping/timecard_metrics/multi_read) API operation has been enhanced with an additional object in the response body: `startingBalanceForPeriod`:

``` json
  "startingBalanceForPeriod": {
    "balanceDate": "2020-07-19T00:00:00",
    "vestedHoursAmount": 53.0667,
    "probationHoursAmount": 0
  }
```

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* Enhanced the documentation for the Create Labor Category Entries (POST /v1/commons/labor_entries/multi_create) API operation to note that entries are created as inactive by default unless the 'inactive' Boolean is set to 'false' for each entry.
* The Retrieve Location Sets by List (POST /v1/commons/location_sets/multi_read) API operation only supported the expandJobs Boolean when searching by types and did not support this Boolean when searching by locationSets. The expandJobs Boolean is now supported when searching by either types or locationSets.
* The Retrieve Locations (POST /v1/commons/locations/multi_read) API operation's example response model on the Developer Portal was missing the orgPath property. This property is now correctly reflected in the JSON model.
* The Retrieve All Hyperfind Profiles (GET /v1/commons/hyperfind_profiles) API operation did not return the correct list of Hyperfind queries assigned to each of the Hyperfind profiles in the response body. The response now correctly lists the hyperfind queries assigned to each Hyperfind profile.
* The Retrieve Engine Statuses (POST /v1/forecasting/engine_statuses/apply_read) API operation's documentation on the Developer Portal has been enhanced to clarify the type of date range needed for the request.
* The Submit Bulk Download (POST /v1/commons/exports/async) API operation returned an incorrect and misleading error message when the Hyperfind specified in the request body contained an empty employee set. The error message returned in this scenario now correctly describes the cause of the error state.
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation would intermittently fail when processing large batches of employees. The root cause was identified and corrected.
* The Retrieve User Preferences (GET /v1/commons/user_preferences) and Retrieve User Preferences for Current User (GET /v1/commons/user_preferences/locale_policy) API operations did not correctly return a user's locale policy when it differed from the tenant's default policy. These API operations now correctly return a user's default locale policy.
* Ensured a default display profile is present in the system to prevent the Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation from generating a nullPointerException error when passing persons with no defined preferenceProfileName in the request payload.
* The Update Rule Set Assignments for Multiple Employees (POST /v1/commons/persons/schedule_rule_sets/multi_upsert) API operation returned an HTTP status code 500 Internal Server Error when either effectiveDate or expirationDate was missing from the request payload. The operation now returns an error message with the details needed to correct the request.
* The Retrieve Schedule (POST /v1/scheduling/schedule/multi_read) API operation incorrectly triggered a service limit when requesting open shifts. The service limit no longer applies to calls against this operation that only request open shifts.
* Enhanced the Shift Template Profile Assignments and Pattern Template Profile Assignments API resources (operations against /v1/commons/persons/shift_template_profiles and /v1/commons/persons/pattern_template_profiles) to allow the caller to specify "Empty" as well as "Empty Profile" to remove assignments. This allows the caller to use the same word shown in the Dimensions UI when unassigning Shift Template Profiles and Pattern Template Profiles.
* Due to a caching issue, the Create Time Off Request as Manager (POST /v1/scheduling/timeoff) API operation incorrectly returned an error when certain valid calls were made. The root cause was identified and corrected.
* Bulk operations against the Labor Category Profiles API resource (POST /v1/commons/labor_category_profiles/multi_create, /v1/commons/labor_category_profiles/multi_update, and /v1/commons/labor_category_profiles/multi_delete) have been enhanced to include HTTP status code 207 Partial Success responses when activated with an optional query parameter.
* Enhanced the Update Multiple Persons (POST /v1/commons/persons/multi_update) API operation to allow the caller to specify "Empty" as well as "Empty Profile" to remove the manager work rule. This allows the caller to use the same word shown in the Dimensions UI when unassigning manager work rules.
* The Bulk Delete Paycode Edits (POST /v1/timekeeping/pay_code_edits/multi_delete) API operation would sometimes fail when passing a very large number of IDs. The root cause was identified and corrected.
* The Update Timecard as Manager (POST /v1/timekeeping/timecard) API operation incorrectly returned an HTTP status code 403 response even when certain calls successfully executed. The root cause was identified and corrected.
* In certain circumstances, the Create Employee Time Off Request (POST /v1/scheduling/employee_timeoff) API operation would take much longer than intended to process. The root cause was identified and steps were taken to enhance response times.
* Enhanced the following API operations to include a timeout query parameter:
    * Create Time Off Request as Manager (POST /v1/scheduling/timeoff)
    * Update Time Off Request as Manager (POST /v1/scheduling/timeoff/apply_update)
    * Update Employee Time Off Request (POST /v1/scheduling/employee_timeoff/apply_update)
* Due to a caching issue, the Update Certification Assignments (POST /v1/commons/persons/certifications/multi_upsert) API operation would intermittently fail and throw an error. The root cause was identified and corrected.

### Docs updates

The following changes were made to the conceptual documentation:

* Updated the [Authentication and security](C:a4943b5b-f44d-4eab-8ccd-24da43b26e64) topic to clarify revoke token behavior.
* Added the [External Identifier Assignments](C:d8b73947-648f-4361-bf1d-ffbd2eac795a) topic to the [Person Assignments](C:e7763b79-01c0-4e0c-bf0c-b7cffaded3c0) guide.
* Updated and enhanced the [Person Assignments](C:e7763b79-01c0-4e0c-bf0c-b7cffaded3c0) guide.
* Various edits and changes to improve the conceptual documentation

### API updates

The following changes were made to the reference documentation:

* Edits throughout to enhance clarity, add detail, and correct errors and omissions

## Dimensions R7 Update 4 {#R7U4}

The following changes were made to the API and Developer Portal in Dimensions R7 Update 4.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The Retrieve Activities (POST /v1/work/activities/multi_read) API operation's request payload model in the Developer Portal was missing the required 'where' property. The process used to generate this model has been corrected to ensure the missing property is now included.
* Enhanced the Submit Bulk Download (POST /v1/commons/exports/async) API operation's documentation to include a full request model as well as example requests and responses.
* Enhanced the Schedule Group Profile Assignments API resource (operations against /v1/commons/persons/schedule_group_profiles) to allow the caller to specify "Empty" as well as "Empty Profile" to remove assignments. This allows the caller to use the same word shown in the Dimensions UI when unassigning Schedule Group Profiles.
* The Bulk Accrual Reset (POST /v1/timekeeping/accruals/resets) API operation would intermittently fail with an HTTP status code 400 error. The root cause was identified and corrected.
* The Create or Update Persons (POST v1/commons/persons/multi_upsert) API operation did not accept employee hours between 0.01 and 1.0. This operation now accepts all employee hours greater than 0.01.
* The Create or Update Persons (POST v1/commons/persons/multi_upsert) API operation intermittently threw an "Illegal invocation of method" error. The root cause was identified and corrected.
* In certain circumstances, the Retrieve Schedule (POST /v1/scheduling/schedule/multi_read) API operation returned a Null Pointer Exception error. The root cause was identified and corrected.
* The Create or Update Wage and Work Rule Overrides (POST /v1/commons/persons/wage_work_rules/multi_upsert) API operation did not properly validate that the job passed for a wage override was a job and not a location on the Business Structure. The operation now properly validates that the nodes passed in this property are in fact jobs.
* The Update Shift Cover Request (POST /v1/scheduling/employee_cover_requests/apply_update) API operation incorrectly generated an 'invalid where parameter' error with certain request subtype configurations.
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation would sometimes incorrectly fail when including the 'predictiveSchedulingEligibilityList' property for a new person record. The root cause of the failure has been identified and corrected.
* The Retrieve Sorted or Eligible Employees (POST /v1/scheduling/staffing_assistant/apply_read) API operation has been enhanced with an optional parameter 'includeTransferEmployees' that allows this operation to include transfer employees as part of its search criteria.
* The Update Schedule for Multiple Employees (POST /v1/scheduling/schedule/multi_update) API operation would not generate a correct partial success response body (when the optional partial_success Boolean was set to 'true') when an incorrect shift segment type was specified in the request payload.
* The Create Labor Category Entries (POST /v1/commons/labor_entries/multi_create) API operation was updated to normalize trailing space handling between the UI and the API.
* The Retrieve All Percentage Allocation Rules (GET /v1/timekeeping/setup/percentage_allocation_rules) API operation was enhanced to improve performance for calls that return a large number of results.

### Docs updates

The following changes were made to the conceptual documentation:

* Added an [Examples](C:aa656587-feba-4e9e-a0c4-f3d49d3a5ca9) section containing request and response schemas and example request and response bodies.
    * Added the [Submit Bulk Download examples](C:02db1480-9844-475a-94da-5ea8823c76bd) topic to the new [Examples](C:aa656587-feba-4e9e-a0c4-f3d49d3a5ca9) section.

### API updates

The following changes were made to the reference documentation:

* Enhanced the documentation for the Submit Bulk Download (POST /v1/commons/exports/async) API operation to include additional enumerations, an example request body, to point out that the payLoad property wraps a Retrieve Data (POST /v1/commons/data/multi_read) request payload, and to point to the new conceptual topic [Submit Bulk Download examples](C:02db1480-9844-475a-94da-5ea8823c76bd), which provides request and response schemas and example request and response bodies.
* Enhanced the documentation for the Retrieve Currency Definition by ID (GET /v1/commons/currency/definitions/{id}) and Retrieve All Currency Definitions (GET /v1/commons/currency/definitions) API operations to add response body examples.
* Enhanced the documentation for the Retrieve Employee Schedule Changes (POST /v1/scheduling/schedule/changes/multi_read) API operation to add Best Practices and an example call.
* Deprecated the Import Labor Forecasts (POST /v1/forecasting/labor_forecast/import) API operation. Instead, use Create Labor Forecasts (POST /v1/forecasting/labor_forecast/multi_create).
* Enhanced the documentation of and added Best Practices to the following Forecasting operations:
    * Import Labor Standards, Tasks, and Task Groups (POST /v1/forecasting/labor_standard_tasks/import)
    * Create Labor Forecasts (POST /v1/forecasting/labor_forecast/multi_create)
    * Update Adjustment Drivers (POST /v1/forecasting/adjustment_drivers/multi_upsert)
    * Import Volume Forecast (POST /v1/forecasting/volume_forecast/import)
    * Import Labor Budgets (POST /v1/forecasting/labor_budget/import)
    * Import Volume Budgets (POST /v1/forecasting/volume_budget/import)
    * Import Actual Volume (POST /v1/forecasting/actual_volume/import)

## Dimensions R7 Update 3 {#R7U3}

The following changes were made to the API and Developer Portal in Dimensions R7 Update 3.

### General

#### Announcements

_**Spike arrest feature**_

UKG is enhancing Dimensions API authentication to improve service reliability in Dimensions R7 Update 3.

Dimensions API operations are controlled by a throttling limit which prevents clients from making too many requests in a short time. Dimensions API authentication is not currently constrained by these mechanisms, which has negatively impacted service reliability. When a customer application requests a new authentication token for every API call, it can overload the authentication servers and prevent authentication tokens from being issued to other customers.

UKG is implementing a REST-compliant spike arrest feature which temporarily blocks authentication requests when too many requests are received too quickly.

**How will this affect your applications?**

If your applications are coded to REST standards, they should correctly handle the spike arrest feature without any changes.

**How will the Dimensions API behave when a spike arrest occurs?**

The API will return an HTTP status code 503 "Service Unavailable" error when a spike arrest occurs.

```
HTTP 503
{
              "errorCode": "GTW-ERROR-012",
              "message": "The request was rejected due to a spike in requests for access tokens. Resubmit your request after a brief wait.”
}
```

This 503 response will include a “Retry-After” header that indicates the number of seconds to wait before resubmitting the request.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The Create or Update Hours of Operation Assignments API operation (POST /v1/commons/hours_operation_assignments/multi_upsert) would allow a new assignment to overlap and erase an existing assignment. Added a new Boolean 'allowOverlappingOverride' request parameter that, when set to false, allows the operation to behave like the UI and throw an error if the assignment specified in the request overlaps an existing assignment.
* The Delete Leave Edits API operation (POST /v1/leave/leave_edits/multi_delete) could cause the system to slow down when processing a Leave Case with no defined end date. Protections were added to ensure such leave cases are processed quickly.
* Enhanced the Minor Rule Sets API operations (GET /v1/scheduling/minor_rule_sets, GET /v1/scheduling/minor_rule_sets{id}, and POST /v1/scheduling/minor_rule_sets/multi_read) to return more information via an optional query parameter 'all_details' or request body property 'allDetails'. 
* The Bulk Retrieve Workload Patterns API operation (POST /v1/scheduling/workload_patterns/multi_read) would sometimes fail with an unknown error. The root cause of these errors was identified and corrected.
* Enhanced the Update Certification Assignments API operation (POST /v1/commons/persons/certifications/multi_upsert) to add a 'preserve_existing_assignments' query parameter, which allows the caller to optionally send only new and updated assignments rather than a full list of all assignments. 
* Enhanced the Retrieve Time Off Requests as Manager and the Retrieve Time Off Request by ID as Manager API operations (POST /v1/scheduling/timeoff/multi_read and GET /v1/scheduling/timeoff/{timeOffRequestId}) to add an 'includeOverriddenShifts' request property and an 'include_overridden_shifts' query parameter, respectively. These new Booleans allows the caller to include overridden shifts in the response.
* The Update Attestation Profile Assignments by Person Number API operation (POST /v1/commons/persons/attestation_profile_assignments/multi_update) would incorrectly throw a 500 Internal Server Error response if an effective date after the system-default "forever date" of 3000-01-01 was specified, preventing 207 Partial Success processing. The operation now provides graceful error handling of "after forever" effective dates.
* The Bulk Accrual Reset API operation (POST /v1/timekeeping/accruals/resets) returned a successful response body containing 'null' when an incorrect date format was supplied in the request payload. The operation now throws a detailed error message when an invalid date format is specified.
* The Retrieve Timecard Data—Multiple Employees API operation (POST /v1/timekeeping/timecard_metrics/multi_read) would, in certain circumstances, incorrectly apply transfer continuation logic, causing schedule totals that did not match the employee's schedule.
* In certain circumstances, changing the name of a primary labor category would not correctly populate the new name in People Information and the response body of the Retrieve Persons API operation (POST /v1/commons/persons/extensions/multi_read).
* Enhanced the Adjustment Rule Assignments API resource and all associated operations (all methods against /v1/commons/persons/adjustment_rule/\*) to accept -1 as an ID representing an Empty Profile, and added the property 'adjustmentRule' to the request bodies of POST operations that also accepts the new ID for Empty Profile.

### Docs updates

The following changes were made to the conceptual documentation:

* Added a __Create open shifts__ Tip to the [Best practices and tips](C:c32c06e7-365a-4cd4-a836-1845a3d56f41) topic demonstrating an efficient way to create multiple open shifts with a single API operation.

## Dimensions R7 Update 2 {#R7U2}

The following changes were made to the API and Developer Portal in Dimensions R7 Update 2.

### General

#### Announcements

* The Create Paycode Edits with Options (POST /v1/scheduling/schedule/pay_code_edits/import) API operation has been deprecated and replaced by the POST /v1/scheduling/schedule/pay_code_edits/apply_import operation.
* Updated the Retrieve Timecard Data—Multiple Employees (POST /v1/timekeeping/timecard_metrics/multi_read) API operation to add a new, optional 'rollUpByJobId' Boolean to the request body. When set to true, job totals are rolled up based only on the job ID and the operation will not take into account changes in the job path across the specified date range. This property defaults to false and is fully backwards compatible.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* Several Forecasting API operations, including Retrieve Labor Budgets (POST /v1/forecasting/labor_budget/apply_read), incorrectly threw a null pointer exception rather than a detailed error message when a location's expiration date occurred before the end date of the period specified in the request payload. These API operations now provide a descriptive error message.
* Enhanced the Retrieve Timezone (GET /v1/commons/setup/timezones) API operation to add the 'fullDisplayName' property to the response body. This property returns a longer timezone name format that is consistent with the timezone naming convention used elsewhere in the API.
* Enhanced the Retrieve Comments for Manager (GET /v1/commons/comments) and Retrieve Comments for Employee (GET /v1/commons/comments/employee_comments) API operations to support returning all category types when the user calling the API has the correct permissions.
* The Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation did not return home cost center information along with primary job and labor category information. This operation has been enhanced to include cost center information.
* The Create Paycode Edits (POST /v1/scheduling/schedule/pay_code_edits/multi_create) API operation did not correctly mark days as unavailable when using an appropriate paycode, such as "Time Off Unavailable." The operation now correctly marks such days as unavailable.
* When reviewing an employee's audit tab in Schedule Planner or calling the Retrieve Schedule Audits (POST /v1/scheduling/audits/multi_read) API operation, a "work rule not found" error could be incorrectly returned instead of valid audit data. The system now gracefully handles audit queries that include deleted work rules.
* In certain situations, the Bulk Accrual Reset (POST /v1/timekeeping/accruals/resets) API operation would return a CT Call error message that did not correctly replace the 'Message' variable with detailed error information. CT Call error messaging is now generated correctly.
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation did not have a parameter that allows a caller to unassign "Labor Category Profile - Manager Additions". The new parameter 'unassignMgrEmplLaborCategoryProfile' was added to enable this functionality.
* The Bulk Delete Paycode Edits (POST /v1/timekeeping/pay_code_edits/multi_delete) API operation incorrectly allowed edits to signed-off periods. Such edits are no longer allowed.

### Docs updates

The following changes were made to the conceptual documentation:

* Updated product language to conform to new naming guidelines for UKG products.
* Documented a significant number of new service limits for assignments, common resources, and Timekeeping operations. Refer to the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic for more information.

## Dimensions R7 Update 1 {#R7U1}

The following changes were made to the API and Developer Portal in Dimensions R7 Update 1.

### General

#### Announcements

**Global Multiple Manager Role Switching Support**

A logged-in manager who has two or more Multi-Manager Roles (Role Assignments) can switch between assigned roles using any API operation by adding the global, optional query parameter `roleId`. For example:

`POST /v1/commons/persons/51?roleId=221`
`POST /v1/scheduling/schedule/pay_code_edits/multi_create?roleId=221`

Refer to the [Global Multiple Manager Role Switching](C:667d4e51-d8bb-4848-b3b7-f2360e88aee2) topic for more information.

**Predictive Scheduling and the Persons API resource**

In R7, the Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation began validating the Predictive Scheduling System Setting when the predictiveSchedulingEligibilityList property was passed in the request payload. Prior to R7, this validation did not occur. To ensure backwards compatibility, the validation introduced in R7 has been removed, and request payloads with this property included will not fail when the Predictive Scheduling system is not enabled.

**Enhanced Accrual Warning Support in the Create Paycode Edits with Options operation**

The Create Paycode Edits with Options () API operation has been enhanced with a new optional Boolean request property: `errorOnAccrualWarning`. This Boolean defaults to `false`.

When this property is `true`, the operation throws an error if an accrual warning occurs. Note that this property interacts with the existing property: `bypassAccrualValidation`. If `bypassAccrualValidation` is `true`, the `errorOnAccrualWarning` property is ignored.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The Create Employment Terms PCEs (POST /v1/scheduling/employment_terms_schedule/pay_code_edits/apply_create) API operation incorrectly required a primary job to be specified in the request even when the employee already had a valid primary job.
* The Update Attendance Profile for Multiple Employees (POST /v1/commons/persons/attendance_profile/multi_update) API operation incorrectly generated an error when the consumer attempted to assign an Empty Profile. The ability to assign an Empty Profile has been restored.
* When the Update Values for Multiple Custom Drivers (POST /v1/forecasting/custom_driver_values/multi_upsert) API operation encountered an error while processing a record and generated an HTTP status code 400 or 207 Partial Success response, the error offsets were not specified in the response body. Error offsets are now included.
* In certain circumstances, the Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation failed to correctly return valid, existing employees. The operation now correctly returns all valid employees.
* In rare circumstances, the Submit Bulk Download (POST /v1/commons/exports/async) API operation could become stranded during execution of the asynchronous request and incorrectly respond with an HTTP status 413 error. The operation now handles these circumstances gracefully.
* The Create or Update Known Places (POST /v1/commons/known_places/multi_upsert) and Create Known Places (POST /v1/commons/known_places/multi_create) API operations incorrectly required the location ID to be specified when a valid qualifier for that location was included in the request payload. Calls specifying locations with valid qualifiers (and no IDs) now execute correctly.
* In R7, the Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation began validating the Predictive Scheduling System Setting when the predictiveSchedulingEligibilityList property was passed in the request payload. Prior to R7, this validation did not occur. To ensure backwards compatibility, the validation introduced in R7 has been removed, and request payloads with this property included will not fail when the Predictive Scheduling system is not enabled.
* The Retrieve Requestable Open Shifts (POST /v1/scheduling/employee_open_shift_requests/open_shifts/multi_read) API operation now returns a clear error message instead of a null pointer exception when a resource is not found.
* The Update Workload Weights or Update, Lock, or Unlock Workload Volumes (POST /v1/scheduling/volume/apply_update) API operation now handles certain error conditions gracefully and no longer throws a null pointer exception.
* The Retrieve Shift Cover Requests (POST /v1/scheduling/employee_cover_requests/multi_read) API operation incorrectly returned a null value for the recipient qualifier. The operation now returns the correct value.
* The Update Rule Set Assignments for Multiple Employees (POST /v1/commons/persons/schedule_rule_sets/multi_upsert) API operation incorrectly returned an error when the start of an assignmentSpan was equal to the effectiveDate. 
* The Create Employment Term Schedule Pattern (POST /v1/scheduling/employment_term_schedule_patterns/apply_create) and the Create Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_create) API operations did not provide resubmittable request payloads inside HTTP status code 207 Partial Success response bodies. These operations have been enhanced with an optional query parameter that allows fully resubmittable request payloads to be passed inside 207 responses.
* Harmonized behavior between the UI and the Update Certification Assignments (POST /v1/commons/persons/certifications/multi_upsert) API operation such that they both accept an end date of 3000-01-01.
* The Retrieve Schedule Audits (POST /v1/scheduling/audits/multi_read) API operation has been enhanced to include HTTP status code 207 Partial Success responses when activated with an optional query parameter.
* The Person API operations, such as Create or Update Persons (POST /v1/commons/persons/multi_upsert), incorrectly allowed inactive Labor Category Entries to be used as Primary Job assignments. Attempting to specify an inactive Labor Category Entry as a Primary Job assignment now results in a error.
* The Retrieve Timecard Data for Multiple Employees (POST /v1/timekeeping/timecard_metrics/multi_read) API operation now correctly rounds hoursAmount inside the actualTotals array.
* The Paycodes for Timekeeping API resource (including operations such as Retrieve Paycodes as Manager (GET /v1/timekeeping/setup/pay_codes)) did not return the analyticCategoryAssignments object in the response even though this object appeared in the response model on the Developer Portal. Operations against this API resource now correctly return this object.
* The Bulk Import Paycode Edits (POST /v1/timekeeping/pay_code_edits/import) API operation did not allow paycode edits to be imported without associating a time of day with the edit. This operation has been enhanced to allow the following:
    1. specify applyDate only
    2. specify startDateTime only
    3. specify both startDateTime and applyDate
    * If both startDateTime and applyDate are specified, they must be the same date or the request results in an error.
* The Retrieve Timecard as Employee (GET /v1/timekeeping/employee_timecard) and Retrieve Timecard as Manager (GET /v1/timekeeping/timecard) API operations incorrectly threw HTTP status code 500 Internal Server Error responses when an invalid selection was specified in the "select" query parameter. These API operations now throw the correct error.
* The Retrieve Employee Groups (POST /v1/commons/employee_groups/multi_read) API operation did not return the laborCategoryProfileRef and orgMapGroupRef properties in the response even though they appear in the response model on the Developer Portal. Operations against this API resource now correctly return these properties.
* Operations against the Timecard API resource, such as Retrieve Timecards as Manager (POST  /v1/timekeeping/timecard/multi_read), were not always correctly handling auto-resolved exceptions, and the operations would fail. These operations now correctly handle auto-resolved exceptions.
* The Create Labor Category List Assignments (POST /v1/commons/labor_category_list_assignments/multi_create) API operation incorrectly threw "An Internal Error Has Occurred" when the specific orgNode qualifier was not valid. The operation now responds with a specific error description.
* The Update Labor Category Lists (POST /v1/commons/labor_category_lists/multi_update) API operation incorrectly threw "An Internal Error Has Occurred" when the entryList array was ommitted from the request payload. The operation now responds with a specific error description.
* The Bulk Accrual Payout (POST /v1/timekeeping/accruals/payouts) API operation did not allow increments of less than 1, which does not match the way the Accrual Policy behaves. The API behavior now allows incremements of less than 1.
* The Retrieve Timecards as Manager (POST /v1/timekeeping/timecard/multi_read) API operation would refuse to return paycode edit data that involved end-dated business structure locations. The operation now correctly returns the data. 
* The Retrieve Activity Totals for Multiple Employees (POST /v1/work/activity_totals/multi_read) API operation did not always return all valid Work activity totals. Totals are now returned correctly. 

### Docs updates

The following changes were made to the conceptual documentation:

* Changed the format of the Important Notes and Version History topics. The releases are now sorted from newest to oldest.
* Added the [Global Multiple Manager Role Switching](C:667d4e51-d8bb-4848-b3b7-f2360e88aee2) topic, which allows any logged-in manager with more than one manager role to switch between those roles in any API call.
* Added [A Guide to Timekeeping](C:5ef69f27-42cb-4ecb-b088-3c0bf4dcfe7e) to the [Guides](C:92b16358-756a-41bf-9204-b0aaf7262cfa) section. 
* We are reworking the Quick Start tutorial to better serve the more mature API platform. More information will be available soon!

## Dimensions R7 {#R7}

The following changes were made to the API and Developer Portal in Dimensions R7.

### General

#### Announcements

**An Important Note on Correcting Insecure Token Generation**

An undocumented, insecure method for generating tokens for API calls has been identified and will be removed in a future release.

If you have any apps that are generating tokens for API calls by passing the required details as query parameters, you must update them to pass those details as form data in the request payload using the secure process described in the [Authentication and security](C:a4943b5b-f44d-4eab-8ccd-24da43b26e64) topic.

**An Important Note Concerning a Deprecated Boolean in Review Notifications by ID**

In the request payload model for the Review Notifications by ID (POST /v1/commons/notifications/multi_review) API operation, the Boolean property `reviewForAll` has been deprecated and no longer performs any function. Previously, this property could be used to review notifications for other managers. After review it was determined that this was not working as designed and posed a potential security issue, so the functionality has been removed.

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The Update Attendance Admin—Multiple Employees (POST /v1/commons/persons/attendance_admin/multi_update) API operation incorrectly returned an HTTP status code 500 Internal Server Error when an invalid Person Number is specified in the request. The API response now returns an informative error message that explicitly tells the caller than the passed Person Number is invalid.
* The Retrieve Persons (POST /v1/commons/person/extensions/multi_read) API operation incorrectly returned an HTTP status code 400 error mentioning an "Internal Server Error" in the message body when an employee is set to inactive for both the user account and employee status and the "onlyActivePerson" Boolean is set to true. This error prevented the API from continuing to process other employees in the request (if other valid employees exist) and producing an HTTP status code 207 Partial Success response. This API operation now correctly processes this error condition and allows HTTP status code 207 or 400 responses, as appropriate. 
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) and Update Person by ID (PUT /v1/commons/persons/{personId}) API operations incorrectly allowed a call to set the expiration date to a date before the effective date for the primary job. These API operations now throw an error if the caller attempts to set an expiration date prior to the effective date.
* The Retrieve Schedule Zone Set Assignments (POST /v1/scheduling/schedule_zone_sets/assignments/multi_read) API operation failed to return updated versions of certain location paths after those paths changed. The API operation now correctly returns updated location paths.
* The Update Location by ID (POST /v1/commons/locations/{id}) and Update Locations (POST /v1/commons/locations/multi_update) API operations did not always update the externalId property. This API operation now correctly updates the externalId when specified in an update request.
* The Update Schedule—Multiple Employees (POST v1/scheduling/schedule/multi_update/?partial_success=true) API operation with Partial Success enabled passed an incorrect error message when the call failed due to an overdrawn leave balance. The API now returns a correct and meaningful error.
* The Retrieve Tag Definitions with Criterion (POST /v1/scheduling/setup/tag_definitions/multi_read) API operation incorrectly returned deleted tags in the response. Deleted tags are no longer returned. 
* The Create Employee Time Off Request (POST /v1/scheduling/employee_timeoff) API operation in certain rare conditions would prevent an employee's time-off requests submitted via the API from displaying in a manager's control center notifications. Time off requests submitted through the API now consistently display in the control center.
* The Update Labor Forecasts (POST /v1/forecasting/labor_forecast/multi_update) API operation has been enhanced to include support for Partial Success responses when activated by means of a new query parameter.
* The Retrieve Unapproved Timecard Data (GET /v1/timekeeping/attestation_unapproved_timecard_data) API operation returned no data for an employee during any period approved by the employee's manager. The API operation now correctly returns relevant data when the timecard has not been approved by the employee.
* The Update Attestation Profile Assignments by Person Number (POST /v1/commons/persons/attestation_profile_assignments/multi_update) API operation incorrectly returned an HTTP status code 500 Internal Server Error in certain situations when an employee's attestation profile assignment is updated. The updated assignments not process correctly.
* The Move Accrual Balances—Multiple Employees (POST /v1/timekeeping/accruals/moves) API operation understands time in terms of minutes, not decimal values, and in situations where the passed decimal value of the accrual move amount does not correspond precisely to a minute value, the passed value is rounded down to the nearest decimal that corresponds to a minute. However, the API response was incorrectly returning the decimal value passed in the request body, not the rounded-down value actually processed by the system. The response body now correctly returns the rounded value, as appropriate.
* Updated the Retrieve Percentage Allocation Rules-Multiple Employees (POST /v1/commons/persons/percentage_allocation_rules/multi_read) API operation to add the Boolean property 'failOnNoAssignment'. When set to false, the operation does not send an HTTP status 400 error when the person queried has no assignments.
* In the unlikely event that you exceed throttling limits or the system is too busy to process a request, a `Retry-After` header has been added to HTTP status code 429 and 503 responses. 
    * When `Retry-After` is returned with an HTTP status code 503 (Service Too Busy) response, the header indicates how long the service is expected to be unavailable. Your app should only make an automatic attempt to retry if the `Retry-After` is present in the response; if it is absent, your app should not automatically retry.
    * When `Retry-After` is returned with an HTTP status code 429 (Too Many Requests) response, the header indicates how long to wait before making a new request.
* When a user's locale policy was set to Mexican Spanish, the following API operations did not accept localized strings for the "contactTypeName" property within the "emailAddresses" array. This property was updated to accept "Trabajo" or "Work".
    * Update Person by ID (PUT /v1/commons/persons/{personId})
    * Create Person (POST /v1/commons/persons)
    * Create or Update Persons (POST /v1/commons/persons/multi_upsert)
    * Create Multiple Persons (POST /v1/commons/persons/multi_create)
    * Update Multiple Persons (POST /v1/commons/persons/multi_update)
* The Update Availability Request State as Manager (POST /v1/scheduling/manager_availability_requests/apply_update), Update Shift Swap Request as Manager (POST /v1/scheduling/manager_swap/apply_update), and Update Open Shift Request (POST /v1/scheduling/open_shift_requests/apply_update) API operations now allow a manager to approve an employee's availability, shift swap, or open shift requests when that employee is part of that manager's Employee Group unless a reviewer list is set up for the applicable request subtype, in which case the manager must be part of the reviewer list.
* The Update Skill Assignments (POST /v1/commons/persons/skills/multi_upsert) API operation incorrectly generated an error when adding a skill to an employee who had been terminated but is configured in the system to be re-hired on the date that the configured termination time span ends. Such skill assignments can now be applied without error.
* When using the Create Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_create) API operation to create a schedule pattern with an override ("override" : true), the system incorrectly returned an HTTP status 200 success response code but a JSON body containing an error, and did not apply the pattern. The system now returns a correct response body and successfully applies the pattern.
* Added partial success support to the following API operations:
    * Retrieve Timecard Data–Multiple Employees (POST /v1/timekeeping/timecard_metrics/multi_read)
    * Retrieve Timecards–Manager (POST /v1/timekeeping/timecard/multi_read)
    * Retrieve Timecards–Employee (POST /v1/timekeeping/employee_timecard/multi_read)
* The Update Employment Term Assignments (POST /v1/commons/persons/employment_terms/multi_upsert) API operation generated an incorrect error message when the employment term referenced in the request payload did not exist. The API now passes a correct error message.
* Under certain conditions, the Retrieve Timecard Data–Multiple Employees (POST v1/timekeeping/timecard_metrics/multi_read) API operation would not correctly pass a vacation pay code edit even when that edit is visible on the timecard in the UI. The API now correctly displays such pay code edits.
* The Create or Update Location Set (POST /v1/commons/location_sets/apply_upsert) API operation incorrectly returned an HTTP status 400 instead of HTTP status 207 for a Partial Success response. This API operation now returns an HTTP status code 207 for Partial Success responses.
* In certain circumstances, the Revoke a Token (POST /authentication/token/revoke) API operation did not invalidate the specified token. This API operation now correctly invalidates tokens in all circumstances.
* The Evaluate Workload (POST /v1/scheduling/workload_coverage/workload/multi_read) API operation incorrectly returned an HTTP status 400 error when the number of processed IDs exceeded 32,768.
* The Retrieve Schedule Pattern by Name (GET /v1/scheduling/schedule_pattern_templates) and Retrieve Schedule Patterns (POST /v1/scheduling/schedule_pattern_templates/multi_read) API operations  occasionally returned HTTP status 200 SUCCESS with an empty array even when valid data existed. These API operations now consistently return the correct data.
* When creating or updating a report using the following API operations, the `reportOutputFormat` property did not correctly validate and use the passed ID before validating and using the qualifier. The API now correctly validates the ID and, if valid, the qualifier is not validated or used in any way.
    * Save Report (POST /v1/platform/reports)
    * Update Report by ID (POST /v1/platform/reports/{id})
* The Update Timecard—Manager (POST /v1/timekeeping/timecard) API operation did not recognize the property "reviewed". The API now accepts either "reviewed" or "isReviewed" in the request payload.
* The Create Labor Category Profiles (POST /v1/commons/labor_category_profiles/multi_create) API operation incorrectly returned an HTTP status code 404 response when a labor category that does not exist is specified in the request. Added a query parameter that, when set to true, converts HTTP status response code 404 to 400 when the error is a result of a missing labor category.
* The Retrieve Absence Spans (POST /v1/timekeeping/absence_spans/multi_read) API operation would not return the correct duration in certain cases.
* The Create Employment Term (POST /v1/timekeeping/setup/employment_terms) API operation would incorrectly require a paycode to be specified in the request payload when the same operation performed through the UI did not require a paycode.

### Docs updates

The following changes were made to the conceptual documentation:

* Added the [Aggregated Person Assignments](C:57f8f4ab-2dcf-4e21-95ce-0b6920af7e4c) topic to [A Guide to People Information](C:1c960ba9-60fc-4387-8f48-f9829e713d30). Don't miss this powerful new API resource.
* Added the [Manage Dimensions UI sessions](C:054cdf88-4a6d-49c7-ad22-c94787d999fa) topic to the [Authentication and security](C:a4943b5b-f44d-4eab-8ccd-24da43b26e64) section, including a new API that allows you to log out a specified Dimensions UI session.
* Updated the person assignment API topics to note that, for effective-dated person assignment updates, you must pass in the request payload any current forever-dated assignment with an explicit end date along with the new assignment with a defined start date. If you pass a new forever-dated assignment and a different forever-dated assignment already exists, the new assignment will replace the existing assignment. Refer to the [Person assignments](C:e7763b79-01c0-4e0c-bf0c-b7cffaded3c0) topic and subtopics for more information.
* Various edits and changes to improve usability of the Developer Portal content.

### API updates

The following changes were made to the reference documentation:

**New Organization**

* Moved the Timekeeping Setup API operations into a new top-level domain named **Timekeeping Setup**.
* Split the **Common Resources** top-level domain into two new top-level domains named **Common Resources I** and **Common Resources II**. 
    * **Common Resources I** contains all of the API resources that used to have Common Resources as their direct parent in the navigation tree.
    * **Common Resources II** contains all of the subdomains within Common Resources that have API resources as children in the navigation tree.

**Important New Content**

* Be sure to check out the powerful new [Aggregated Person Assignments](C:57f8f4ab-2dcf-4e21-95ce-0b6920af7e4c) API resource under People, which allows you to consolidate the management of most person assignments. You can retrieve one or more person's assignments, update, add, or delete assignments for multiple people, and retrieve the names of all available aggregated assignments.

**Other Updates**

* Updated the list of enumerations for the Retrieve Timecards `select` property. This update affects:
    * Retrieve Timecards-Manager (POST /v1/timekeeping/timecard/multi_read)
    * Retrieve Timecards-Employee (POST /v1/timekeeping/employee_timecard/multi_read)
* Added the full list of enumerations for the Retrieve Timecard `select` query parameter. This update affects:
    * Retrieve Timecard-Manager (GET /v1/timekeeping/timecard)
    * Retrieve Timecard-Employee (GET /v1/timekeeping/employee_timecard)
* Updated the Timecard Metrics resource by enhancing Retrieve Timecard Data—Multiple Employees API operation documentation and by adding descriptions of each possible `select` parameter.
* Enhanced the Process Leave Requests (POST /v1/leave/leave_requests/multi_action) and Process Leave Request by ID (POST /v1/leave/leave_requests/{id}) documentation to explicitly list all possible actions.
* Enhanced the Retrieve Location Sets by List (POST /v1/commons/location_sets/multi_read) documentation to explicitly list all available org map group types.
* Enhanced the Update Employee Open Shift Request (POST /v1/scheduling/employee_open_shift_requests/apply_update) documentation with all valid enumerations for the `event` property.
* Enhanced the documentation for the following two API operations to mention the new Test Mode feature, implemented by passing an ID of -1:
    * Update Integration Execution Details (POST /v1/platform/integrations/update_status)
    * Submit Integration Execution Additional Details (POST /v1/platform/integration_executions/{id}/additional_details)

## Dimensions R6 Update 4 {#R6U4}

The following changes were made to the API and Developer Portal in Dimensions R6 Update 4.

### General

#### Announcements

**An Important Note on startTime and endTime in Employee Extensions**

In the first public R6 Release of Dimensions (06.04.00), an enhancement was made to add `startTime` and `endTime` to the effective-dated entries for the `badgeDetails` object in the Retrieve Person by Extension (GET /v1/commons/persons/{extensionType}) operation.

As part of this work, a defect was introduced which caused `startTime` and `endTime` to be added to the response for all effective-dated entries across many of the extensions.

The invalid `startTime` and `endTime` returned are always "00:00:00" and "23:59:59" respectively. These values do not actually exist on the effective-dated properties in the employee extensions. They are erroneously added to the response body's JSON. They have no effect on any of the affected extension properties.

In Dimensions R6 Update 4 (06.08.00), we are removing the invalid `startTime` and `endTime` values from all extensions (with the exception of `badgeDetails`, where they are valid).

Any effective-dated entries included in these extensions will have these erroneous `startTime` and `endTime` properties removed. 

> **Important:** The `badgeDetails` object in `deviceExtension` is the only property where `startTime` and `endTime` are valid. `startTime` and `endTime` will not be removed from the `badgeDetails` object.

The invalid instances of `startTime` and `endTime` should not be consumed by any API-based application. These values should be ignored and any applications that have begun consuming these new values should be modified to ignore them.

**Affected API operations:**

* Retrieve Persons (POST /v1/commons/persons/extensions/multi_read)
* Retrieve Person by Extension (GET /v1/commons/persons/{extensionType})
* Retrieve All Extensions (GET /v1/commons/persons/extensions)

**Extensions Impacted:**

* `accountStatusDataExtension`
* `accrualProfilesDataExtension`
* `accrualProfilesDataExtensionNew`
* `accrualProfilesDataExtensionNew`
* `baseWageDataExtension`
* `dataAccessExtension`
* `employmentAnalyticsLaborTypeDataExtension`
* `employmentStatusDataExtension`
* `employmentTermDataExtension`
* `fullTimeEquivalencyDataExtension`
* `groupAssignmentDataExtension`
* `jobTransferDataExtension`
* `payRuleDataExtension`
* `predictiveSchedulingEligibilityDataExtension`
* `primaryJobAccountDataExtension`

**Example of Erroneous Entries:**

``` json
  "employeeExtension": {
    "effDatedAccountStatuses": [
      {
        "accountStatus": "Active",
        "accountStatusTypeId": 1,
        "effectiveDate": "2016-08-13",
        "endTime": "23:59:59",    // invalid endTime
        "expirationDate": "3000-01-01",
        "startTime": "00:00:00"    // invalid startTime
      }
    ],
    "effDatedPrimaryJobAccountEntries": [
      {
        "effectiveDate": "2016-08-13",
        "endTime": "23:59:59",    // invalid endTime
        "expirationDate": "2019-01-01",
        "primaryJob": "Organization/United States/Metropolitan Plant/Machine Shop/Apprentice Welder",
        "primaryLaborCategory": ",,Shift 1,,,",
        "primaryLaborCategoryId": 2,
        "primaryOrganizationId": 35,
        "startTime": "00:00:00"    // invalid startTime
      }
    ],
    "employmentStatuses": [
      {
        "effectiveDate": "2016-08-13",
        "employmentStatus": "Active",
        "employmentStatusTypeId": 1,
        "endTime": "23:59:59",    // invalid endTime
        "expirationDate": "3000-01-01",
        "startTime": "00:00:00"    // invalid startTime
      }
    ]
  }
```

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* Calling the Create or Update Volume Driver Assignments (POST /v1/forecasting/volume_driver_assignments/multi_upsert) API operation multiple times completed successfully for most of the specified records, but sporadically failed with a NullPointerException error. Repeated operations against this resource should now succeed without error.
* The Submit Bulk Downloads (POST /v1/commons/exports/async) API operation was incorrectly restricted by service limits implemented by other domains, but is now only restricted by the proper Information Access service limits. Refer to the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic for more information.
* When a Leave of Absence case was configured to commit the leave time to the schedule, the Create Leave Edits (POST /v1/leave/leave_edits) API operation still committed leave time in the timecard. 
* The Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation would sometimes return records without the firstName and lastName properties. The operation now consistently returns these properties.
* The Retrieve Locations API operation (POST /v1/commons/locations/multi_read) sometimes returned an error message instead of the requested root location.
* The Evaluate Metrics for Scheduling API operation (POST /v1/scheduling/schedule_metrics/multi_read) sometimes returned a value of 0 instead of the correct value.
* When the Bulk Import Punches API operation (POST /v1/timekeeping/punches/import) was called with an override specified only by qualifier, the call would fail. The call now works with either ID or qualifier for the override.
* The Update Attestation Profile Assignments by Person Number API operation (POST /v1/commons/persons/attestation_profile_assignments/multi_update) was not correctly processing request payloads in a way that allowed for partial successes when multiple entities were passed.
* During some calls to the Retrieve Data API operation (POST /v1/commons/data/multi_read), a multi-threading error occurred.
* The Create Employment Term API operation (POST /v1/timekeeping/setup/employment_terms) was not correctly validating properties in the request payload.
* The Create Employment Term and Update Employment Term API operations (POST /v1/timekeeping/setup/employment_terms and PUT /v1/timekeeping/setup/employment_terms/{id}) were missing three modifiable properties in the request body schema:
    * Minimum Wage
    * Contributing Pay Codes
    * Pay Code for Adjustment

### Docs updates

The following changes were made to the conceptual documentation:

* Added an **Access client ID and client secret** section to the [App keys, client ID, and client secret](C:a44a9f41-6442-42e3-91b1-9c946de54763) topic and added a reference to this topic in the [Getting started](C:636f581c-50a8-41a7-af43-e5057f9c20bd) topic.
* Added a [Context parameters for menu links](C:07dcbe7f-88e4-4aa2-9602-a25376e23aa4) topic to the [Best practices](C:c32c06e7-365a-4cd4-a836-1845a3d56f41) section.
* Moved the Authentication topic to the top level to increase visibility.
* Various edits and changes to improve usability of the Developer Portal content

### API updates

The following changes were made to the reference documentation:

* Removed the invalid startTime and endTime values from all Person extensions (with the exception of `badgeDetails`, where they are valid). Refer to the Announcements for more details.
* Added the `extend_all_activities_query` query parameter to Retrieve Activity by Name (GET /v1/work/activities)
* The existing Timekeeping > Paycodes—Timekeeping operations have been enriched with additional properties.

## Dimensions R6 Update 3 {#R6U3}

The following changes were made to the API and Developer Portal in Dimensions R6 Update 3.

### General

#### Announcements

**An Important Note on startTime and endTime in Employee Extensions**

In the first public R6 Release of Dimensions (06.04.00), an enhancement was made to add `startTime` and `endTime` to the effective-dated entries for the `badgeDetails` object in the Retrieve Person by Extension (GET /v1/commons/persons/{extensionType}) operation.

As part of this work, a defect was introduced which caused `startTime` and `endTime` to be added to the response for all effective-dated entries across many of the extensions.

The invalid `startTime` and `endTime` returned are always "00:00:00" and "23:59:59" respectively. These values do not actually exist on the effective-dated properties in the employee extensions. They are erroneously added to the response body's JSON. They have no effect on any of the affected extension properties.

In Dimensions R6 Update 4 (06.08.00), we are removing the invalid `startTime` and `endTime` values from all extensions (with the exception of `badgeDetails`, where they are valid).

Any effective-dated entries included in these extensions will have these erroneous `startTime` and `endTime` properties removed. 

> **Important:** The `badgeDetails` object in `deviceExtension` is the only property where `startTime` and `endTime` are valid. `startTime` and `endTime` will not be removed from the `badgeDetails` object.

The invalid instances of `startTime` and `endTime` should not be consumed by any API-based application. These values should be ignored and any applications that have begun consuming these new values should be modified to ignore them.

**Affected API operations:**

* Retrieve Persons (POST /v1/commons/persons/extensions/multi_read)
* Retrieve Person by Extension (GET /v1/commons/persons/{extensionType})
* Retrieve All Extensions (GET /v1/commons/persons/extensions)

**Extensions Impacted:**

* `accountStatusDataExtension`
* `accrualProfilesDataExtension`
* `accrualProfilesDataExtensionNew`
* `accrualProfilesDataExtensionNew`
* `baseWageDataExtension`
* `dataAccessExtension`
* `employmentAnalyticsLaborTypeDataExtension`
* `employmentStatusDataExtension`
* `employmentTermDataExtension`
* `fullTimeEquivalencyDataExtension`
* `groupAssignmentDataExtension`
* `jobTransferDataExtension`
* `payRuleDataExtension`
* `predictiveSchedulingEligibilityDataExtension`
* `primaryJobAccountDataExtension`

**Example of Erroneous Entries:**

``` json
  "employeeExtension": {
    "effDatedAccountStatuses": [
      {
        "accountStatus": "Active",
        "accountStatusTypeId": 1,
        "effectiveDate": "2016-08-13",
        "endTime": "23:59:59",    // invalid endTime
        "expirationDate": "3000-01-01",
        "startTime": "00:00:00"    // invalid startTime
      }
    ],
    "effDatedPrimaryJobAccountEntries": [
      {
        "effectiveDate": "2016-08-13",
        "endTime": "23:59:59",    // invalid endTime
        "expirationDate": "2019-01-01",
        "primaryJob": "Organization/United States/Metropolitan Plant/Machine Shop/Apprentice Welder",
        "primaryLaborCategory": ",,Shift 1,,,",
        "primaryLaborCategoryId": 2,
        "primaryOrganizationId": 35,
        "startTime": "00:00:00"    // invalid startTime
      }
    ],
    "employmentStatuses": [
      {
        "effectiveDate": "2016-08-13",
        "employmentStatus": "Active",
        "employmentStatusTypeId": 1,
        "endTime": "23:59:59",    // invalid endTime
        "expirationDate": "3000-01-01",
        "startTime": "00:00:00"    // invalid startTime
      }
    ]
  }
```

#### Corrections and enhancements

The following conditions were corrected or enhanced:

* The Retrieve Date Span Grouped by Symbol Type (POST /v1/commons/symbolicperiod/multi_read) API operation did not always return the start and end dates for the symbolic period.
* The Submit Bulk Download (POST /v1/commons/exports/async) asynchronous API operation would in rare situations remain in the Pending state until deleted.
* The Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation returned custom field properties that did not always match the ordinal position of the custom field, resulting in a JSON response body with a "customDataTypeId" that did not match the numerical sequence of each custom field.
* The Retrieve Timecard as Manager (GET /v1/timekeeping/timecard) API operation caused rare performance issues.
* The Create or Update Location Set (POST /v1/commons/location_sets/apply_upsert) API operation sometimes caused performance issues that resulted in a timeout error.
* Enhanced the following API operations with a query parameter that adds Partial Success error handling:
    * Create Employment Term Schedule Pattern (POST /v1/scheduling/employment_term_schedule_patterns/apply_create)
    * Update or Remove Employment Term Schedule Patterns (POST /v1/scheduling/employment_term_schedule_patterns/apply_update)
    * Create Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_create)
    * Update Employee Schedule Pattern (POST /v1/scheduling/employee_schedule_patterns/apply_update)
    * Create Schedule Group Pattern (POST /v1/scheduling/schedule_group_patterns/apply_create)
    * Update or Remove Schedule Group Patterns (POST /v1/scheduling/schedule_group_patterns/apply_update)
* Also added Partial Success support to the following soon-to-be-deprecated API operations:
    * Create Group Schedule Pattern (POST /v1/scheduling/group_schedule_patterns/apply_create)
    * Update or Remove Group Schedule Patterns (POST /v1/scheduling/group_schedule_patterns/apply_update
* The Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation did not always return the correct value in the "managerSignoffThruDate" property.
* The Retrieve Data (POST /v1/commons/data/multi_read) API operation did not return the full name for the AUDIT_DATASOURCE Data Dictionary key.
* The Retrieve Timecard Data for Multiple Employees (POST /v1/timekeeping/timecard_metrics/multi_read) API operation did not correctly allow pay code qualifiers to be used as filters.
* The Retrieve Persons (POST /v1/commons/persons/extensions/multi_read) API operation did not return a value for the "managerSignoffThruDate" property for newly created employees.
* The Create or Update Persons (POST /v1/commons/persons/multi_upsert) API operation returned an incorrect error when the value passed in "managerEmployeeGroupName" did not exist and a "homeHyperFindQueryName" was passed in the same call.
* The Bulk Accrual Reset (POST /v1/timekeeping/accruals/resets) API operation returned a null response for records with an accrual code name that did not exactly match the case of the accrual code name passed in the request body.
* The Retrieve Timecards as Manager (POST /v1/timekeeping/timecard/multi_read) API operation did not return all of the same time-related data as the Retrieve Timecard as Manager (GET /v1/timekeeping/timecard) API operation.

### Docs updates

The following changes were made to the conceptual documentation:

* Added this Important notes topic, which captures updates to the Developer Portal that fall outside of the new API operations listed in the [Version history](C:2d250085-ed39-496b-92fd-5f6a66d3f357)
* Added the [Best practices and tips](C:c32c06e7-365a-4cd4-a836-1845a3d56f41) topic along with new and edited subtopics
* Moved the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic to the top level of the conceptual documentation
* Updated the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic to include service limits for the Work domain
* Various edits and changes to improve usability of the Developer Portal content

### API updates

The following change was made to the reference documentation:

* Added the `extend_all_activities_query` query parameter to Retrieve Activity by Name (GET /v1/work/activities)