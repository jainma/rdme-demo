---
title: "Version history"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb662255dd00016e0b208"
---

# Version history

* [R9 Update 2](#R9U2)
* [R9 Update 1](#R9U1)
* [R9](#R9)
* [R8 Update 3](#R8U3)
* [R8 Update 2](#R8U2)
* [R8 Update 1](#R8U1)
* [R8](#R8)
* [R7 Update 3](#R7U3)
* [R7 Update 2](#R7U2)
* [R7 Update 1](#R7U1)
* [R7](#R7)
* [R6 Update 4](#R6U4)
* [R6 Update 3](#R6U3)
* [R6 Update 2](#R6U2)
* [R6 Update 1](#R6U1)
* [R6](#R6)
* [R5 Update 2](#R5U2)
* [R5 Update 1](#R5U1)
* [R5](#R5)
* [4.11.0](#4110)
* [4.10.0](#4100)
* [4.9.0](#490)
* [4.8.0](#480)
* [4.7.0](#470)
* [4.4.0](#440)
* [3.7.0](#370)
* [3.2.0](#320)
* [3.1.0](#310)
* [2.7.0](#270)
* [2.6.0](#260)
* [2.4.0](#240)
* [2.3.0](#230)
* [2.2.0](#220) 
* [2.0.0](#200)
* [1.12.0](#1120)
* [1.1.0](#110)

## Dimensions R9 Update 2 {#R9U2}

The following operations were added to the API in Dimensions R9 Update 2:

Domain                                    | Resource                              | Operation                                                       | Method | URL endpoint
----------------                          | ----------------                      | ----------------                                                | ------ | ----------------
Common Resources I                        | Employee Photos                       | Retrieve Photos for Multiple Employees                          | POST   | `/v1/commons/persons/profile_photos/multi_read`
Person Assignments                        | Certification Assignments             | Delete Certification Assignments                                | POST   | `/v1/commons/persons/certifications/apply_delete`
Person Assignments                        | Skill Assignments                     | Delete Skill Assignments                                        | POST   | `/v1/commons/persons/skills/apply_delete`
Work (Activities)                         | Team Segments Net Changes             | Retrieve Net Changes for Team Segments                          | POST   | `/v1/work/team_segments/net_changes/apply_read`





## Dimensions R9 Update 1 {#R9U1}

The following operations were added to the API in Dimensions R9 Update 1:

Domain                                    | Resource                              | Operation                                                       | Method | URL endpoint
----------------                          | ----------------                      | ----------------                                                | ------ | ----------------
Common Resources I                        | Messaging Notifications               | Delete Notifications by Cache Key                               | DELETE | `/v2/commons/notifications/cache/{cacheKey}`
Common Resources I                        | Transaction Assistant                 | Retrieve All Transaction Assistant Records                      | POST   | `/v1/commons/transaction_assistant/multi_read`
Common Resources II > Business Structures | Location Attribute Start Day Of Week  | Retrieve a Location Attribute Week Span                         | POST   | `/v1/commons/start_day_weeks/apply_read`
Forecasting                               | Labor Period Overrides                | Retrieve Labor Period Overrides                                 | POST   | `/v1/forecasting/labor_period_overrides/multi_read`
Forecasting                               | Labor Period Overrides                | Create or Update Labor Period Overrides                         | POST   | `/v1/forecasting/labor_period_overrides/multi_upsert`
Forecasting                               | Labor Period Overrides                | Delete Labor Period Overrides                                   | POST   | `/v1/forecasting/labor_period_overrides/multi_delete`
Forecasting                               | Labor Period Overrides                | Retrieve Overridable Tasks by Department                        | POST   | `/v1/forecasting/labor_period_overrides/overridable_department_tasks/apply_read`
Forecasting Setup                         | Labor Distribution Groups             | Retrieve All Labor Distribution Groups or by Name               | GET    | `/v1/forecasting/labor_distribution_groups`
Forecasting Setup                         | Labor Distribution Groups             | Retrieve Labor Distribution Group by ID                         | GET    | `/v1/forecasting/labor_distribution_groups/{id}`
Forecasting Setup                         | Labor Distribution Groups             | Create Labor Distribution Group                                 | POST   | `/v1/forecasting/labor_distribution_groups`
Forecasting Setup                         | Labor Distribution Groups             | Update Labor Distribution Group by ID                           | PUT    | `/v1/forecasting/labor_distribution_groups/{id}`
Forecasting Setup                         | Labor Distribution Groups             | Delete Labor Distribution Group by ID                           | DELETE | `/v1/forecasting/labor_distribution_groups/{id}`
Forecasting Setup                         | Labor Distribution Groups             | Retrieve All Allocation Method Types                            | GET    | `/v1/forecasting/labor_distribution_groups/setup/allocation_method_types`
Forecasting Setup                         | Labor Distribution Groups             | Retrieve All Borrow Hours Types                                 | GET    | `/v1/forecasting/labor_distribution_groups/setup/borrow_hours_types`
Forecasting Setup                         | Labor Distribution Group Profiles     | Retrieve All Labor Distribution Group Profiles or by Name       | GET    | `/v1/forecasting/labor_distribution_group_profiles`
Forecasting Setup                         | Labor Distribution Group Profiles     | Retrieve Labor Distribution Group Profile by ID                 | GET    | `/v1/forecasting/labor_distribution_group_profiles/{id}`
Forecasting Setup                         | Labor Distribution Group Profiles     | Retrieve Labor Distribution Group Profile by Location           | POST   | `/v1/forecasting/labor_distribution_group_profiles/apply_read`
Forecasting Setup                         | Labor Distribution Group Profiles     | Create Labor Distribution Group Profile                         | POST   | `/v1/forecasting/labor_distribution_group_profiles`
Forecasting Setup                         | Labor Distribution Group Profiles     | Update Labor Distribution Group Profile by ID                   | PUT    | `/v1/forecasting/labor_distribution_group_profiles/{id}`
Forecasting Setup                         | Labor Distribution Group Profiles     | Delete Labor Distribution Group Profile by ID                   | DELETE | `/v1/forecasting/labor_distribution_group_profiles/{id}`
Forecasting Setup                         | Labor Standards                       | Retrieve Labor Driver Adjustment Operations                     | GET    | `/v1/forecasting/labor_standards/labor_driver_operations`
Healthcare Analytics                      | Billing Department and Work Unit Maps | Retrieve All Billing Department and Work Unit Maps              | GET    | `/v1/hca/volume/billing_department_maps`
Healthcare Analytics                      | Billing Department and Work Unit Maps | Create or Update Billing Department and Work Unit Maps          | POST   | `/v1/hca/volume/billing_department_maps/multi_upsert`
People                                    | Persons                               | Retrieve All Persons                                            | POST   | `/v1/commons/persons/apply_read`
People                                    | Persons                               | Retrieve Current User                                           | GET    | `/v1/commons/persons/current_user_info`
Platform > Integrations                   | File-based Integrations               | Retrieve Integration Process by ID                              | GET    | `/v1/platform/integrations/{id}`
Platform > Integrations                   | File-based Integrations               | Create an Integration Process                                   | POST   | `/v1/platform/integrations`
Platform > Integrations                   | File-based Integrations               | Update Integration by ID                                        | PUT    | `/v1/platform/integrations/{id}`
Platform > Integrations                   | Integration Executions                | Retrieve Integration Executions                                 | POST   | `/v1/platform/integration_executions/multi_read`
Platform > Integrations                   | SFTP Connections                      | Retrieve All SFTP Connections                                   | GET    | `/v1/platform/integrations/sftp_connections`
Platform > Integrations                   | SFTP Connections                      | Retrieve SFTP Connection by ID                                  | GET    | `/v1/platform/integrations/sftp_connections/{id}`
Platform > Integrations                   | SFTP Connections                      | Test SFTP Connection by ID                                      | GET    | `/v1/platform/integrations/sftp_connections/{id}/connection_status`
Platform > Integrations                   | SFTP Connections                      | Update SFTP Connections for Integrations                        | POST   | `/v1/platform/integrations/sftp_connections/apply_update`
Timekeeping Setup                         | Break Rules                           | Retrieve GDAP-filtered Break Rule by ID                         | GET    | `/v2/timekeeping/setup/break_rules/{id}`
Timekeeping Setup                         | Break Rules                           | Retrieve GDAP-filtered Break Rules                              | GET    | `/v2/timekeeping/setup/break_rules`

<br /><br />
_**Note:** This update contains version 2 API operations which replace deprecated version 1 operations. Refer to the table in the following topic for more information:_
<br>
_[Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445)_

_**Important Note:** We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality._

The following **version 2** operations replace deprecated **version 1** operations:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Common Resources I          | Messaging Notifications                 | Retrieve Notifications                                          | GET    | `/v2/commons/notifications`

## Dimensions R9 {#R9}

The following operations were added to the API in Dimensions R9:

Domain                                    | Resource                              | Operation                                                       | Method | URL endpoint
----------------                          | ----------------                      | ----------------                                                | ------ | ----------------
Common Resources I                        | Feature Switches                      | Retrieve Feature Switch by Name                                 | GET    | `/v1/commons/feature_switch/{name}`
Common Resources I                        | Feature Switches                      | Retrieve Feature Switches                                       | POST   | `/v1/commons/feature_switch/multi_read`
Common Resources I                        | Generic Data Access Profiles          | Create or Update Generic Data Access Profiles                   | POST   | `/v1/commons/generic_data_access_profiles/apply_upsert`
Common Resources I                        | Generic Data Access Profiles          | Retrieve Generic Data Access Profiles                           | POST   | `/v1/commons/generic_data_access_profiles/multi_read`
Common Resources II > Business Structures | Location Attribute Assignments        | Retrieve Location Attribute Value                               | POST   | `/v1/commons/location_attribute_assignments/apply_read`
Common Resources II > Business Structures | Location Attributes                   | Retrieve Location Attribute by Criteria                         | GET    | `/v1/commons/location_attributes`
Common Resources II > Business Structures | Location Attributes                   | Retrieve Location Attribute by ID                               | GET    | `/v1/commons/location_attributes/{id}`
Common Resources II > Business Structures | Location Attributes                   | Retrieve Location Attributes                                    | POST   | `/v1/commons/location_attributes/multi_read`
Common Resources II > Business Structures | Location Attributes                   | Create Location Attribute                                       | POST   | `/v1/commons/location_attributes`
Common Resources II > Business Structures | Location Attributes                   | Create or Update Location Attributes                            | POST   | `/v1/commons/location_attributes/multi_upsert`
Common Resources II > Business Structures | Location Attributes                   | Update Location Attribute by ID                                 | PUT    | `/v1/commons/location_attributes/{id}`
Common Resources II > Business Structures | Location Attributes                   | Delete Location Attribute by ID                                 | DELETE | `/v1/commons/location_attributes/{id}`
Common Resources II > Business Structures | Location Attributes                   | Delete Location Attributes                                      | POST   | `/v1/commons/location_attributes/multi_delete`
Common Resources II > Known Places        | GPS Known Places                      | Retrieve Known Places                                           | POST   | `/v1/commons/known_places/multi_read`
Forecasting                               | Volume Forecast Intervals Engine      | Execute Volume Forecast Intervals Engine                        | POST   | `/v1/forecasting/volume_forecast_intervals_engine/apply_create`
Forecasting Setup                         | Forecast Planner Settings             | Retrieve Volume Forecast Intervals                              | GET    | `/v1/forecasting/forecast_planner_settings/resources/volume_forecast_intervals`
Person Assignments                        | Aggregated Person Assignments         | Retrieve All Assignments by Criteria                            | GET    | `/v1/commons/persons/assignments`
Scheduling Setup                          | Absence Quota Overrides               | Retrieve Absence Quota Overrides                                | POST   | `/v1/scheduling/setup/team_definition/absence_quota_overrides/apply_read`
Scheduling Setup                          | Absence Quota Overrides               | Create, Update, or Delete Absence Quota Overrides               | POST   | `/v1/scheduling/setup/team_definition/absence_quota_overrides/apply_upsert`
Scheduling Setup                          | ESS Calendar Settings                 | Retrieve Transfer Types for ESS Calendar Settings               | GET    | `/v1/scheduling/ess_calendar_settings/transfer_types`
Scheduling                                | Manager Schedules                     | Retrieve Employee Schedule Statuses                             | POST   | `/v1/scheduling/schedule/status/multi_read`
Scheduling                                | Scheduling Engines                    | Retrieve Scheduling Engine Asynchronous Request Status by Key   | GET    | `/v1/scheduling/schedule/apply_update/{id}/status`
Scheduling                                | Scheduling Engines                    | Retrieve Scheduling Engine Asynchronous Response Payload by Key | GET    | `/v1/scheduling/schedule/apply_update/{id}/response`
Scheduling                                | Scheduling Engines                    | Retrieve Summary of Scheduling Engine Asynchronous Delegate Profile Jobs | GET    | `/v1/scheduling/schedule/apply_update/async`
Scheduling                                | Scheduling Engines                    | Execute Scheduling Engine Asynchronously                        | POST   | `/v1/scheduling/schedule/apply_update/async`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve All Strategies or by Name                              | GET    | `/v1/scheduling/setup/schedule_generation_engine_strategies`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve Strategy by ID                                         | GET    | `/v1/scheduling/setup/schedule_generation_engine_strategies/{id}`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve Strategies                                             | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/multi_read`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve Strategies Assigned to Location by ID                  | GET    | `/v1/scheduling/setup/schedule_generation_engine_strategies/strategies_assignments`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve Strategies Assigned to Locations                       | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/strategies_assignments/multi_read`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve Locations Assigned to Strategy by ID                   | GET    | `/v1/scheduling/setup/schedule_generation_engine_strategies/{strategy_id}/location_assignments`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve Locations Assigned to Strategies                       | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/location_assignments/multi_read`
Scheduling                                | Schedule Generation Engine Strategies | Retrieve All Parameter Definitions for Strategies or by Name    | GET    | `/v1/scheduling/setup/schedule_generation_engine_strategies/settings`
Scheduling                                | Schedule Generation Engine Strategies | Create Strategy                                                 | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies`
Scheduling                                | Schedule Generation Engine Strategies | Create Strategies                                               | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/multi_create`
Scheduling                                | Schedule Generation Engine Strategies | Update Strategy by ID                                           | PUT    | `/v1/scheduling/setup/schedule_generation_engine_strategies/{id}`
Scheduling                                | Schedule Generation Engine Strategies | Update Strategies                                               | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/multi_update`
Scheduling                                | Schedule Generation Engine Strategies | Update Strategy Assignments to Locations                        | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/location_assignments/apply_update`
Scheduling                                | Schedule Generation Engine Strategies | Delete Strategy by ID                                           | DELETE | `/v1/scheduling/setup/schedule_generation_engine_strategies/{id}`
Scheduling                                | Schedule Generation Engine Strategies | Delete Strategies                                               | POST   | `/v1/scheduling/setup/schedule_generation_engine_strategies/multi_delete`

<br /><br />
_**Note:** This update contains version 2 API operations which replace deprecated version 1 operations. Refer to the table in the following topic for more information:_
<br>
_[Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445)_

_**Important Note:** We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality._

The following **version 2** operations replace deprecated **version 1** operations:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Scheduling Setup            | Schedule Groups                         | Retrieve All Schedule Groups or by Name                         | GET    | `/v2/scheduling/setup/schedule_groups`

## Dimensions R8 Update 3 {#R8U3}

The following operations were added to the API in Dimensions R8 Update 3:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Common Resources II > Business Structures | Location Sets             | Delete Location Sets                                            | POST   | `/v1/commons/location_sets/multi_delete`
Scheduling Setup            | Indicators                              | Retrieve All Indicators or by Name                              | GET    | `/v1/scheduling/setup/indicators`
Scheduling Setup            | Indicators                              | Retrieve Indicator by ID                                        | GET    | `/v1/scheduling/setup/indicators/{id}`
Scheduling Setup            | Indicators                              | Retrieve Indicators                                             | POST   | `/v1/scheduling/setup/indicators/multi_read`
Scheduling Setup            | Request Subtypes                        | Retrieve Request Subtype by Name                                | GET    | `/v1/scheduling/setup/request_subtypes`
Scheduling Setup            | Request Subtypes                        | Retrieve Request Subtype by ID                                  | GET    | `/v1/scheduling/setup/request_subtypes/{id}`
Scheduling Setup            | Request Subtypes                        | Retrieve Request Subtypes                                       | POST   | `/v1/scheduling/setup/request_subtypes/multi_read`

<br /><br />
_**Note:** This update contains version 2 API operations which replace deprecated version 1 operations. Refer to the table in the following topic for more information:_
<br>
_[Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445)_

_**Important Note:** We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality._

The following **version 2** operations replace deprecated **version 1** operations:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Leave                       | Leave Case Statuses                     | Retrieve Leave Case Statuses                                    | GET    | `/v2/leave/case_statuses`
Timekeeping Setup           | Accrual Codes                           | Retrieve Accrual Codes                                          | GET    | `/v2/timekeeping/setup/accrual_codes`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycodes as Manager                                    | GET    | `/v2/timekeeping/setup/pay_codes`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycodes as Employee                                   | GET    | `/v2/timekeeping/setup/employee_pay_codes`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycode by ID as Employee                              | GET    | `/v2/timekeeping/setup/employee_pay_codes/{id}`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycode Symbolic Values as Manager                     | GET    | `/v2/timekeeping/setup/pay_code_symbolic_values`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycode Symbolic Values as Employee                    | GET    | `/v2/timekeeping/setup/employee_pay_code_symbolic_values`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycode Symbolic Value by ID as Manager                | GET    | `/v2/timekeeping/setup/pay_code_symbolic_values/{id}`
Timekeeping Setup           | Paycodes for Timekeeping                | Retrieve Paycode Symbolic Value by ID as Employee               | GET    | `/v2/timekeeping/setup/employee_pay_code_symbolic_values/{id}`
Timekeeping Setup           | Timekeeping Pay Rules                   | Retrieve All Timekeeping Pay Rules                              | GET    | `/v2/timekeeping/setup/payrules`
Timekeeping Setup           | Timekeeping Pay Rules                   | Create Timekeeping Pay Rule                                     | POST   | `/v2/timekeeping/setup/payrules`
Timekeeping Setup           | Work Rules                              | Retrieve Work Rule by ID as Employee                            | GET    | `/v2/timekeeping/setup/employee_work_rules/{id}`
Timekeeping Setup           | Work Rules                              | Retrieve Work Rules as Employee                                 | GET    | `/v2/timekeeping/setup/employee_work_rules`

## Dimensions R8 Update 2 {#R8U2}

The following operations were added to the API in Dimensions R8 Update 2:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Common Resources I          | Cost Centers                            | Retrieve Cost Centers                                           | POST   | `/v1/commons/cost_centers/multi_read`
Common Resources I          | Labor Category Entries                  | Retrieve Labor Category Entries                                 | POST   | `/v1/commons/labor_entries/multi_read`
Common Resources I          | Labor Category Lists                    | Create or Update Labor Category Lists                           | POST   | `/v1/commons/labor_category_lists/multi_upsert`
Common Resources I          | Labor Category Profiles                 | Create or Update Labor Category Profiles                        | POST   | `/v1/commons/labor_category_profiles/multi_upsert`
Common Resources I          | Payroll Export                          | Retrieve Summary of Asynchronous Payroll Export Jobs            | GET    | `/v1/commons/payroll/export/async`
Common Resources I          | Payroll Export                          | Retrieve Payroll Export Asynchronous Response Payload by Key    | GET    | `/v1/commons/payroll/export/async/{executionKey}/response`
Common Resources I          | Payroll Export                          | Retrieve Payroll Export Asynchronous Request Status by Key      | GET    | `/v1/commons/payroll/export/async/{executionKey}/status`
Common Resources I          | Payroll Export                          | Export Payroll Asynchronously                                   | POST   | `/v1/commons/payroll/export/async`
Common Resources I          | Payroll Export                          | Export Small Batch Payroll                                      | POST   | `/v1/commons/payroll/export`
Common Resources I          | Payroll Staging                         | Retrieve Asynchronous Payroll Extraction Details by ID          | GET    | `/v1/commons/payroll/staging/{requestId}/details`
Common Resources I          | Payroll Staging                         | Retrieve Payroll Extraction Asynchronous Request Status by ID   | GET    | `/v1/commons/payroll/staging/{requestId}/status`
Common Resources I          | Payroll Staging                         | Execute Payroll Extraction Asynchronously                       | POST   | `/v1/commons/payroll/staging/async`
Common Resources I          | Payroll Tables                          | Retrieve Payroll Table by Name                                  | GET    | `/v1/commons/payroll/tables/{name}`
Common Resources I          | Payroll Tables                          | Retrieve All Payroll Tables                                     | GET    | `/v1/commons/payroll/tables`
Common Resources I          | Payroll Tables                          | Create Payroll Table                                            | POST   | `/v1/commons/payroll/tables/apply_create`
Common Resources I          | Payroll Tables                          | Create or Update Payroll Table                                  | POST   | `/v1/commons/payroll/tables/apply_upsert`
Common Resources I          | Payroll Tables                          | Delete Payroll Table by Name                                    | DELETE | `/v1/commons/payroll/tables/{name}`
Employee Self-Service       | Employee Availability Pattern Requests  | Retrieve Availability Pattern Request by ID                     | GET    | `/v1/scheduling/employee_availability_pattern_requests/{availabilityPatternRequestId}`
Employee Self-Service       | Employee Availability Pattern Requests  | Retrieve Request Subtypes by Availability Type                  | GET    | `/v1/scheduling/employee_availability_pattern_requests/request_subtypes`
Employee Self-Service       | Employee Availability Pattern Requests  | Create Availability Pattern Request                             | POST   | `/v1/scheduling/employee_availability_pattern_requests`
Employee Self-Service       | Employee Availability Pattern Requests  | Update Availability Pattern Request State                       | POST   | `/v1/scheduling/employee_availability_pattern_requests/apply_update`
Employee Self-Service       | Manager Availability Pattern Requests   | Retrieve Availability Pattern Requests as Manager               | POST   | `/v1/scheduling/manager_availability_pattern_requests/multi_read`
Employee Self-Service       | Manager Availability Pattern Requests   | Update Availability Pattern Request State as Manager            | POST   | `/v1/scheduling/manager_availability_pattern_requests/apply_update`
Forecasting Setup           | Machine Learning Models                 | Retrieve All Machine Learning Models or by Name                 | GET    | `/v2/forecasting/machine_learning_models`
Forecasting Setup           | Machine Learning Models                 | Create Machine Learning Model                                   | POST   | `/v2/forecasting/machine_learning_models`
Forecasting Setup           | Machine Learning Models                 | Delete Machine Learning Model by Name                           | DELETE | `/v2/forecasting/machine_learning_models`
Platform > Batch Processing | Batch Events                            | Retrieve Batch Event by ID                                      | GET    | `/v1/platform/batch_processing/batch_events/{id}`
Platform > Batch Processing | Batch Events                            | Retrieve All Batch Events                                       | GET    | `/v1/platform/batch_processing/batch_events`
Platform > Batch Processing | Batch Events                            | Retrieve Batch Tasks by Batch Event ID                          | GET    | `/v1/platform/batch_processing/batch_events/{id}/batch_tasks`
Platform > Batch Processing | Batch Events                            | Create Batch Events                                             | POST   | `/v1/platform/batch_processing/batch_events/multi_create`
Platform > Batch Processing | Batch Events                            | Update Batch Events by ID                                       | PUT    | `/v1/platform/batch_processing/batch_events/{id}`
Platform > Batch Processing | Batch Events                            | Update Batch Events                                             | POST   | `/v1/platform/batch_processing/batch_events/apply_update`
Platform > Batch Processing | Batch Events                            | Delete Batch Event by ID                                        | DELETE | `/v1/platform/batch_processing/batch_events/{id}`
Platform > Batch Processing | Batch Events                            | Delete Batch Events                                             | POST   | `/v1/platform/batch_processing/batch_events/multi_delete`
Platform > Batch Processing | Schedule Batch Events                   | Schedule Batch Events                                           | POST   | `/v1/platform/batch_processing/batch_events/schedule/multi_create`
Platform > Batch Processing | Batch Groups                            | Retrieve Batch Group by ID                                      | GET    | `/v1/platform/batch_processing/batch_groups/{id}`
Platform > Batch Processing | Batch Groups                            | Retrieve All Batch Groups                                       | GET    | `/v1/platform/batch_processing/batch_groups`
Platform > Batch Processing | Batch Groups                            | Retrieve Batch Events by Batch Group ID                         | GET    | `/v1/platform/batch_processing/batch_groups/{id}/batch_events`
Platform > Batch Processing | Batch Groups                            | Create Batch Groups                                             | POST   | `/v1/platform/batch_processing/batch_groups/multi_create`
Platform > Batch Processing | Batch Groups                            | Update Batch Groups by ID                                       | PUT    | `/v1/platform/batch_processing/batch_groups/{id}`
Platform > Batch Processing | Batch Groups                            | Update Batch Groups                                             | POST   | `/v1/platform/batch_processing/batch_groups/apply_update`
Platform > Batch Processing | Batch Groups                            | Delete Batch Group by ID                                        | DELETE | `/v1/platform/batch_processing/batch_groups/{id}`
Platform > Batch Processing | Batch Groups                            | Delete Batch Groups                                             | POST   | `/v1/platform/batch_processing/batch_groups/multi_delete`
Platform > Batch Processing | Batch Job Statuses                      | Retrieve Batch Job Statuses                                     | POST   | `/v1/platform/batch_processing/batch_job_status/multi_read`
Platform > Batch Processing | Batch Tasks                             | Retrieve Batch Task by ID                                       | GET    | `/v1/platform/batch_processing/batch_tasks/{id}`
Platform > Batch Processing | Batch Tasks                             | Retrieve All Batch Tasks                                        | GET    | `/v1/platform/batch_processing/batch_tasks`
Platform > Batch Processing | Batch Tasks                             | Retrieve All Batch Task Action Types                            | GET    | `/v1/platform/batch_processing/batch_tasks/setup/action_types`
Platform > Batch Processing | Batch Tasks                             | Create Batch Tasks                                              | POST   | `/v1/platform/batch_processing/batch_tasks/multi_create`
Platform > Batch Processing | Batch Tasks                             | Update Batch Tasks by ID                                        | PUT    | `/v1/platform/batch_processing/batch_tasks/{id}`
Platform > Batch Processing | Batch Tasks                             | Update Batch Tasks                                              | POST   | `/v1/platform/batch_processing/batch_tasks/apply_update`
Platform > Batch Processing | Batch Tasks                             | Delete Batch Task by ID                                         | DELETE | `/v1/platform/batch_processing/batch_tasks/{id}`
Platform > Batch Processing | Batch Tasks                             | Delete Batch Tasks                                              | POST   | `/v1/platform/batch_processing/batch_tasks/multi_delete`
Platform                    | Change Indicators                       | Retrieve Marker Types                                           | GET    | `/v1/platform/change_indicators`
Platform                    | Change Indicators                       | Retrieve Marker Events                                          | POST   | `/v1/platform/change_indicators/markers/apply_read`
Platform                    | Change Indicators                       | Retrieve Subscriptions                                          | GET    | `/v1/platform/change_indicators/subscriptions`
Platform                    | Change Indicators                       | Retrieve Cadences                                               | GET    | `/v1/platform/change_indicators/setup/cadence`
Platform                    | Change Indicators                       | Retrieve Retention Periods                                      | GET    | `/v1/platform/change_indicators/setup/retention_periods`
Platform                    | Change Indicators                       | Subscribe or Unsubscribe to Change Indicators                   | POST   | `/v1/platform/change_indicators/subscriptions/{action}`
Scheduling Setup            | Schedule Events                         | Retrieve Schedule Event by Name                                 | GET    | `/v1/scheduling/setup/schedule_events`
Scheduling Setup            | Schedule Events                         | Retrieve Schedule Event by ID                                   | GET    | `/v1/scheduling/setup/schedule_events/{id}`
Scheduling Setup            | Schedule Events                         | Retrieve Schedule Events                                        | POST   | `/v1/scheduling/setup/schedule_events/multi_read`
Scheduling Setup            | Schedule Events                         | Create Schedule Event                                           | POST   | `/v1/scheduling/setup/schedule_events`
Scheduling Setup            | Schedule Events                         | Create Schedule Events                                          | POST   | `/v1/scheduling/setup/schedule_events/multi_create`
Scheduling Setup            | Schedule Events                         | Update Schedule Event by ID                                     | PUT    | `/v1/scheduling/setup/schedule_events/{id}`
Scheduling Setup            | Schedule Events                         | Update Schedule Events                                          | POST   | `/v1/scheduling/setup/schedule_events/multi_update`
Scheduling Setup            | Schedule Events                         | Delete Schedule Event by ID                                     | DELETE | `/v1/scheduling/setup/schedule_events/{id}`
Scheduling Setup            | Schedule Events                         | Delete Schedule Events                                          | POST   | `/v1/scheduling/setup/schedule_events/multi_delete`
Scheduling Setup            | Schedule Event Rules                    | Retrieve All Schedule Event Rules or by Name                    | GET    | `/v1/scheduling/setup/schedule_event_rules`
Scheduling Setup            | Schedule Event Rules                    | Retrieve Schedule Event Rule by ID                              | GET    | `/v1/scheduling/setup/schedule_event_rules/{id}`
Scheduling Setup            | Schedule Event Rules                    | Retrieve Schedule Event Rules                                   | POST   | `/v1/scheduling/setup/schedule_event_rules/multi_read`
Scheduling Setup            | Schedule Event Rules                    | Create Schedule Event Rule                                      | POST   | `/v1/scheduling/setup/schedule_event_rules`
Scheduling Setup            | Schedule Event Rules                    | Create Schedule Event Rules                                     | POST   | `/v1/scheduling/setup/schedule_event_rules/multi_create`
Scheduling Setup            | Schedule Event Rules                    | Update Schedule Event Rule by ID                                | PUT    | `/v1/scheduling/setup/schedule_event_rules/{id}`
Scheduling Setup            | Schedule Event Rules                    | Update Schedule Event Rules                                     | POST   | `/v1/scheduling/setup/schedule_event_rules/multi_update`
Scheduling Setup            | Schedule Event Rules                    | Delete Schedule Event Rule by ID                                | DELETE | `/v1/scheduling/setup/schedule_event_rules/{id}`
Scheduling Setup            | Schedule Event Rules                    | Delete Schedule Event Rules                                     | POST   | `/v1/scheduling/setup/schedule_event_rules/multi_delete`
Timekeeping > Attestations  | Attestation Questions                   | Create Attestation Questions                                    | POST   | `/v1/timekeeping/attestation_questions/multi_create`
Timekeeping > Attestations  | Attestation Questions                   | Update Attestation Questions                                    | POST   | `/v1/timekeeping/attestation_questions/multi_update`
Timekeeping > Attestations  | Attestation Answers                     | Create Attestation Answers                                      | POST   | `/v1/timekeeping/attestation_answers/multi_create`
Timekeeping > Attestations  | Attestation Answers                     | Update Attestation Answers                                      | POST   | `/v1/timekeeping/attestation_answers/multi_update`
Timekeeping > Attestations  | Manual Time Entry Workflows             | Retrieve Manual Time Entry Workflows                            | POST   | `/v1/timekeeping/attestation_manual_entry_process`
Timekeeping > Attestations  | Complete Manual Time Entry Attestation Process | Complete Manual Time Entry Attestation Process           | POST   | `/v1/timekeeping/attestation_manual_entry_process/complete`
Timekeeping Bulk Operations | Bulk Payroll Lock                       | Bulk Payroll Lock                                               | POST   | `/v1/commons/payroll/lock/apply_update`
Timekeeping Setup           | Pay Code Tags                           | Retrieve All Pay Code Tags                                      | GET    | `/v1/timekeeping/setup/pay_code_tags`
Timekeeping Setup           | Pay Code Tags                           | Retrieve Pay Code Tag by ID                                     | GET    | `/v1/timekeeping/setup/pay_code_tags/{id}`
Timekeeping Setup           | Pay Code Tags                           | Create Pay Code Tag                                             | POST   | `/v1/timekeeping/setup/pay_code_tags`
Timekeeping Setup           | Pay Code Tags                           | Update Pay Code Tag by ID                                       | PUT    | `/v1/timekeeping/setup/pay_code_tags/{id}`
Timekeeping Setup           | Pay Code Tags                           | Delete Pay Code Tag by ID                                       | DELETE | `/v1/timekeeping/setup/pay_code_tags/{id}`
Work                        | Activities                              | Retrieve Activity Export Definitions                            | POST   | `/v1/work/activities/exports/apply_read`
Work                        | Activity Shifts                         | Delete Activity Shifts                                          | POST   | `/v1/work/activity_shifts/multi_delete`

<br /><br />
_**Note:** This update contains version 2 API operations which replace deprecated version 1 operations. Refer to the table in the following topic for more information:_
<br>
_[Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445)_

_**Important Note:** We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality._

The following **version 2** operations replace deprecated **version 1** operations:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Common Resources II > Business Structures | Location Sets             | Retrieve Paginated List of Location Sets                        | POST   | `/v2/commons/location_sets/multi_read`
Forecasting                 | Forecast Week                           | Retrieve a Forecast Week                                        | GET    | `/v2/forecasting/forecast_week`
Forecasting                 | Forecast Week                           | Retrieve Start Day                                              | GET    | `/v2/forecasting/forecast_week/start_day`
Forecasting                 | Forecast Week                           | Retrieve Start Days                                             | POST   | `/v2/forecasting/forecast_week/start_days/multi_read`
Forecasting                 | Forecast Week                           | Retrieve Default Start Day                                      | GET    | `/v2/forecasting/forecast_week/default_start_day`
Forecasting                 | Static Drivers                          | Retrieve All Static Drivers or by Name                          | GET    | `/v2/forecasting/static_drivers`
Forecasting                 | Static Drivers                          | Retrieve Static Driver by ID                                    | GET    | `/v2/forecasting/static_drivers/{id}`
Forecasting                 | Volume Forecast                         | Import Volume Forecast                                          | POST   | `/v2/forecasting/volume_forecast/import`
Forecasting                 | Volume Forecast Model Types             | Retrieve All Volume Forecast Model Types                        | GET    | `/v2/forecasting/volume_forecast_model_types`
Forecasting                 | Week Symbolic Periods                   | Retrieve Week Symbolic Period Types                             | GET    | `/v2/forecasting/week_symbolic_periods`
Forecasting                 | Generic Categories                      | Retrieve All Generic Categories or by Name                      | GET    | `/v2/forecasting/generic_categories`
Forecasting                 | Generic Categories                      | Retrieve Generic Category by ID                                 | GET    | `/v2/forecasting/generic_categories/{id}`
Forecasting                 | Generic Categories                      | Retrieve Generic Categories                                     | POST   | `/v2/forecasting/generic_categories/multi_read`

## Dimensions R8 Update 1 {#R8U1}

_**Note:** This update introduces the first version 2 API resources, which replace deprecated version 1 operations. Refer to the table in the following topic for more information:_
<br>
_[Version 2 resources and operations](C:420f1b59-1570-41c4-95e0-b49d795e4445)_

_**Important Note:** We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality._

The following operations were added to the API in Dimensions R8 Update 1:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Common Resources I          | Access Method Profiles                  | Retrieve All Access Method Profiles                             | GET    | `/v1/commons/access_method_profiles`
Common Resources I          | Access Method Profiles                  | Retrieve Access Method Profile by ID                            | GET    | `/v1/commons/access_method_profiles/{id}`
Common Resources I          | Access Method Profiles                  | Retrieve Access Method Profiles                                 | POST   | `/v1/commons/access_method_profiles/multi_read`
Common Resources I          | Access Method Profiles                  | Retrieve Access Methods                                         | GET    | `/v1/commons/access_method_profiles/access_methods`
Common Resources I          | Access Method Profiles                  | Retrieve Role Profiles                                          | GET    | `/v1/commons/access_method_profiles/role_profiles`
Common Resources I          | Access Method Profiles                  | Create Access Method Profile                                    | POST   | `/v1/commons/access_method_profiles`
Common Resources I          | Access Method Profiles                  | Create or Update Access Method Profiles                         | POST   | `/v1/commons/access_method_profiles/multi_upsert`
Common Resources I          | Access Method Profiles                  | Update Access Method Profile by ID                              | PUT    | `/v1/commons/access_method_profiles/{id}`
Common Resources I          | Access Method Profiles                  | Delete Access Method Profile by ID                              | DELETE | `/v1/commons/access_method_profiles/{id}`
Common Resources I          | Access Method Profiles                  | Delete Access Method Profiles                                   | POST   | `/v1/commons/access_method_profiles/multi_delete`
Common Resources I          | Hours of Operation                      | Delete Hours of Operation Effective Version                     | POST   | `/v2/commons/hours_operation/versions/apply_delete`
Forecasting                 | Daily Actual Volume                     | Create Daily Actual Volume                                      | POST   | `/v1/forecasting/daily_actual_volume/multi_create`
Forecasting                 | Labor Forecast Limits                   | Delete Labor Forecast Limit Effective Version                   | POST   | `/v2/forecasting/labor_forecast_limits/versions/apply_delete`
Forecasting                 | Labor Tasks                             | Delete Labor Task Effective Version by Criteria                 | POST   | `/v2/forecasting/tasks/versions/apply_delete`
Forecasting                 | Task Groups                             | Delete Task Group Effective Version by Criteria                 | POST   | `/v2/forecasting/task_groups/versions/apply_delete`
Forecasting                 | Task Groups                             | Retrieve Task Groups by Criteria                                | POST   | `/v2/forecasting/task_groups/apply_read`
Forecasting                 | Traffic Patterns                        | Retrieve Traffic Patterns                                       | POST   | `/v1/forecasting/traffic_patterns/multi_read`
Forecasting                 | Traffic Patterns                        | Create Traffic Patterns                                         | POST   | `/v1/forecasting/traffic_patterns/multi_create`
Forecasting                 | Traffic Patterns                        | Delete Traffic Patterns                                         | POST   | `/v1/forecasting/traffic_patterns/multi_delete`
Forecasting                 | Traffic Pattern Engine                  | Execute Traffic Pattern Engine                                  | POST   | `/v1/forecasting/traffic_pattern_engine/apply_create`
Platform                    | Action Templates                        | Retrieve All Announcement Action Templates                      | GET    | `/v1/platform/announcements/action_templates`
Platform                    | Action Templates                        | Retrieve Announcement Action Template by ID                     | GET    | `/v1/platform/announcements/action_templates/{id}`
Platform                    | Employee Announcements                  | Retrieve Announcement Message Response by ID as Employee        | GET    | `/v1/platform/announcements/employee_announcements/{id}`
Platform                    | Employee Announcements                  | Update Announcement Message Response as Employee                | POST   | `/v1/platform/announcements/employee_announcements/apply_update`
Platform                    | Manager Announcements                   | Retrieve Announcement Message Response by ID as Manager         | GET    | `/v1/platform/announcements/manager_announcements/{id}`
Platform                    | Manager Announcements                   | Retrieve Announcement Messages as Manager                       | POST   | `/v1/platform/announcements/manager_announcements/apply_read`
Platform                    | Manager Announcements                   | Create Announcement as Manager                                  | POST   | `/v1/platform/announcements/manager_announcements`
Platform                    | Kiosk                                   | Retrieve Kiosk Login Transactions                               | POST   | `/v1/timekeeping/kiosk_instance_logins/apply_read`
Platform                    | Kiosk                                   | Retrieve All Kiosk Configurations                               | GET    | `/v1/timekeeping/setup/kiosks`
Platform                    | Kiosk                                   | Retrieve Kiosk Configuration by ID                              | GET    | `/v1/timekeeping/setup/kiosks/{id}`
Platform                    | Kiosk                                   | Create Kiosk Configuration                                      | POST   | `/v1/timekeeping/setup/kiosks`
Platform                    | Kiosk                                   | Update Kiosk Configuration by ID                                | PUT    | `/v1/timekeeping/setup/kiosks/{id}`
Platform                    | Kiosk                                   | Delete Kiosk Configuration by ID                                | DELETE | `/v1/timekeeping/setup/kiosks/{id}`
Platform                    | Kiosk                                   | Retrieve All Kiosk Instances                                    | GET    | `/v1/timekeeping/setup/kiosk_instances`
Platform                    | Kiosk                                   | Retrieve Kiosk Instance by ID                                   | GET    | `/v1/timekeeping/setup/kiosk_instances/{id}`
Platform                    | Kiosk                                   | Create Kiosk Instance                                           | POST   | `/v1/timekeeping/setup/kiosk_instances`
Platform                    | Kiosk                                   | Update Kiosk Instance by ID                                     | PUT    | `/v1/timekeeping/setup/kiosk_instances/{id}`
Platform                    | Kiosk                                   | Delete Kiosk Instance by ID                                     | DELETE | `/v1/timekeeping/setup/kiosk_instances/{id}`
Platform > Reporting        | Report Requests                         | Retrieve Paginated List of Scheduled Report Requests            | POST   | `/v1/platform/scheduled_reports/apply_read`
Platform > Reporting        | Report Executions                       | Retrieve Report History by Criteria                             | POST   | `/v1/platform/report_executions/apply_read`
Scheduling                  | Rule Violations                         | Evaluate Employee Rule Violations                               | POST   | `/v1/scheduling/violations/evaluate`
Timekeeping > Attestations  | Attestation Answers                     | Retrieve All Attestation Answers or by Name                     | GET    | `/v1/timekeeping/attestation_answers`
Timekeeping > Attestations  | Attestation Answers                     | Retrieve Attestation Answer by ID                               | GET    | `/v1/timekeeping/attestation_answers/{id}`
Timekeeping > Attestations  | Attestation Answers                     | Retrieve Attestation Answers                                    | POST   | `/v1/timekeeping/attestation_answers/multi_read`
Timekeeping > Attestations  | Attestation Answers                     | Create Attestation Answer                                       | POST   | `/v1/timekeeping/attestation_answers`
Timekeeping > Attestations  | Attestation Answers                     | Update Attestation Answer by ID                                 | PUT    | `/v1/timekeeping/attestation_answers/{id}`
Timekeeping > Attestations  | Attestation Answers                     | Delete Attestation Answer by ID                                 | DELETE | `/v1/timekeeping/attestation_answers/{id}`
Timekeeping > Attestations  | Attestation Answers                     | Delete Attestation Answers                                      | POST   | `/v1/timekeeping/attestation_answers/multi_delete`
Timekeeping > Attestations  | Attestation Questions                   | Retrieve All Attestation Questions or by Name                   | GET    | `/v1/timekeeping/attestation_questions`
Timekeeping > Attestations  | Attestation Questions                   | Retrieve Attestation Question by ID                             | GET    | `/v1/timekeeping/attestation_questions/{id}`
Timekeeping > Attestations  | Attestation Questions                   | Retrieve Attestation Questions                                  | POST   | `/v1/timekeeping/attestation_questions/multi_read`
Timekeeping > Attestations  | Attestation Questions                   | Create Attestation Question                                     | POST   | `/v1/timekeeping/attestation_questions`
Timekeeping > Attestations  | Attestation Questions                   | Update Attestation Question by ID                               | PUT    | `/v1/timekeeping/attestation_questions/{id}`
Timekeeping > Attestations  | Attestation Questions                   | Delete Attestation Question by ID                               | DELETE | `/v1/timekeeping/attestation_questions/{id}`
Timekeeping > Attestations  | Attestation Questions                   | Delete Attestation Questions                                    | POST   | `/v1/timekeeping/attestation_questions/multi_delete`
Timekeeping                 | Bulk Asynchronous Paycode Edits         | Bulk Import Paycode Edits Asynchronously                        | POST   | `/v1/timekeeping/pay_code_edits/import/async`
Timekeeping                 | Bulk Asynchronous Paycode Edits         | Retrieve Summary of Asynchronous Paycode Edit Import Jobs       | GET    | `/v1/timekeeping/pay_code_edits/import/async`
Timekeeping                 | Bulk Asynchronous Paycode Edits         | Retrieve Paycode Edit Import Asynchronous Request Status by Key | GET    | `/v1/timekeeping/pay_code_edits/import/async/{execution_key}/status`
Timekeeping                 | Bulk Asynchronous Paycode Edits         | Retrieve Asynchronous Paycode Edit Import Response Payload by Key | GET  | `/v1/timekeeping/pay_code_edits/import/async/{execution_key}/response`
Timekeeping                 | Exception Tiles                         | Create Exception Tile                                           | POST   | `/v1/timekeeping/exception_tiles`
Timekeeping                 | Exception Tiles                         | Create Exception Tiles                                          | POST   | `/v1/timekeeping/exception_tiles/multi_create`
Timekeeping                 | Exception Tiles                         | Update Exception Tiles                                          | POST   | `/v1/timekeeping/exception_tiles/multi_update`
Timekeeping                 | Exception Tiles                         | Delete Exception Tile by ID                                     | POST   | `/v1/timekeeping/exception_tiles/{id}`
Timekeeping                 | Exception Tiles                         | Delete Exception Tiles                                          | POST   | `/v1/timekeeping/exception_tiles/multi_delete`
Timekeeping                 | Pending Historical Corrections          | Retrieve Summary of Asynchronous Pending Historical Compute Corrections Jobs       | GET    | `/v1/timekeeping/pending_historical_corrections/compute/async`
Timekeeping                 | Pending Historical Corrections          | Retrieve Compute Pending Historical Corrections Asynchronous Request Status by Key | GET    | `/v1/timekeeping/pending_historical_corrections/compute/{id}/status`
Timekeeping                 | Pending Historical Corrections          | Compute Pending Historical Corrections                                             | POST   | `/v1/timekeeping/pending_historical_corrections/compute/async`
Timekeeping                 | Pending Historical Corrections          | Retrieve Compute Pending Historical Corrections Asynchronous Request Status by Key | GET    | `/v1/timekeeping/pending_historical_corrections/compute/{id}/results`
Timekeeping                 | Pending Historical Corrections          | Retrieve Summary of Asynchronous Save Pending Historical Corrections Jobs          | GET    | `/v1/timekeeping/pending_historical_corrections/save/async`
Timekeeping                 | Pending Historical Corrections          | Retrieve Save Pending Historical Corrections Asynchronous Request Status by Key    | GET    | `/v1/timekeeping/pending_historical_corrections/save/{id}/status`
Timekeeping                 | Pending Historical Corrections          | Save Pending Historical Corrections                                                | POST   | `/v1/timekeeping/pending_historical_corrections/save/async`
Timekeeping                 | Pending Historical Corrections          | Retrieve Asynchronous Saved Pending Historical Corrections by Key                  | POST   | `/v1/timekeeping/pending_historical_corrections/save/{id}/results`
Timekeeping Setup           | Accrual Policies                        | Retrieve Accrual Policy by ID                                   | GET    | `/v1/timekeeping/setup/accrual_policies/{id}`
Timekeeping Setup           | Accrual Policies                        | Retrieve Accrual Policies                                       | POST   | `/v1/timekeeping/setup/accrual_policies/multi_read`
Timekeeping Setup           | Employment Terms                        | Update Employment Term Versions                                 | POST   | `/v1/timekeeping/setup/employment_terms/versions/apply_upsert`
Timekeeping Setup           | Time-Off Rules                          | Retrieve All Time-Off Rules                                     | GET    | `/v1/timekeeping/setup/time_off_rules`

<br /><br />
The following **version 2** operations replace deprecated **version 1** operations:

Domain                      | Resource                                   | Operation                                                            | Method | URL endpoint
----------------            | ----------------                           | ----------------                                                     | ------ | ----------------
Common Resources I          | Cost Centers                               | Retrieve Cost Center by ID                                           | GET    | `/v2/commons/cost_centers/{id}`
Common Resources I          | Cost Centers                               | Retrieve All Cost Centers                                            | GET    | `/v2/commons/cost_centers`
Common Resources I          | Hours of Operation                         | Retrieve All Hours of Operation or by Name                           | GET    | `/v2/commons/hours_operation`
Common Resources I          | Hours of Operation                         | Retrieve Hours of Operation by ID                                    | GET    | `/v2/commons/hours_operation/{id}`
Common Resources I          | Hours of Operation                         | Retrieve Multiple Hours of Operation                                 | POST   | `/v2/commons/hours_operation/multi_read`
Common Resources I          | Hours of Operation                         | Create Hours of Operation                                            | POST   | `/v2/commons/hours_operation`
Common Resources I          | Hours of Operation                         | Create Multiple Hours of Operation                                   | POST   | `/v2/commons/hours_operation/multi_create`
Common Resources I          | Hours of Operation                         | Update Hours of Operation by ID                                      | PUT    | `/v2/commons/hours_operation/{id}`
Common Resources I          | Hours of Operation                         | Update Multiple Hours of Operation                                   | POST   | `/v2/commons/hours_operation/multi_update`
Common Resources I          | Hours of Operation                         | Delete Hours of Operation by ID                                      | DELETE | `/v2/commons/hours_operation/{id}`
Common Resources I          | Hours of Operation                         | Delete Multiple Hours of Operation                                   | POST   | `/v2/commons/hours_operation/multi_delete`
Common Resources I          | Labor Categories                           | Retrieve Labor Category by ID                                        | GET    | `/v2/commons/labor_categories/{id}`
Common Resources I          | Labor Categories                           | Retrieve All Labor Categories or by Name                             | GET    | `/v2/commons/labor_categories`
Common Resources I          | Labor Category Entries                     | Retrieve Labor Category Entry by ID                                  | GET    | `/v2/commons/labor_entries/{id}`
Common Resources I          | Labor Category Entries                     | Retrieve Labor Category Entries by Category ID                       | GET    | `/v2/commons/labor_entries`
Forecasting                 | Labor Forecast Limits                      | Retrieve Labor Forecast Limit by Name                                | GET    | `/v2/forecasting/labor_forecast_limits`
Forecasting                 | Labor Forecast Limits                      | Retrieve Labor Forecast Limit by ID                                  | GET    | `/v2/forecasting/labor_forecast_limits/{id}`
Forecasting                 | Labor Forecast Limits                      | Retrieve Labor Forecast Limits by Criteria                           | POST   | `/v2/forecasting/labor_forecast_limits/apply_read`
Forecasting                 | Labor Forecast Limits                      | Create Labor Forecast Limit                                          | POST   | `/v2/forecasting/labor_forecast_limits`
Forecasting                 | Labor Forecast Limits                      | Create Labor Forecast Limits                                         | POST   | `/v2/forecasting/labor_forecast_limits/multi_create`
Forecasting                 | Labor Forecast Limits                      | Update Labor Forecast Limit by ID                                    | PUT    | `/v2/forecasting/labor_forecast_limits/{id}`
Forecasting                 | Labor Forecast Limits                      | Update Labor Forecast Limits                                         | POST   | `/v2/forecasting/labor_forecast_limits/multi_update`
Forecasting                 | Labor Forecast Limits                      | Delete Labor Forecast Limit by ID                                    | DELETE | `/v2/forecasting/labor_forecast_limits/{id}`
Forecasting                 | Labor Forecast Limits                      | Delete Labor Forecast Limits                                         | POST   | `/v2/forecasting/labor_forecast_limits/multi_delete`
Forecasting                 | Labor Standards, Tasks, and Task Groups    | Import Labor Standards, Tasks, and Task Groups                       | POST   | `/v2/forecasting/labor_standard_tasks/import`
Forecasting                 | Labor Standards, Tasks, and Task Groups    | Purge Labor Standards                                                | POST   | `/v2/forecasting/labor_standard_tasks/purge`
Forecasting                 | Labor Tasks                                | Retrieve All Labor Tasks or by Specification                         | GET    | `/v2/forecasting/tasks`
Forecasting                 | Labor Tasks                                | Retrieve Labor Task by ID                                            | GET    | `/v2/forecasting/tasks/{id}`
Forecasting                 | Labor Tasks                                | Retrieve Labor Tasks                                                 | POST   | `/v2/forecasting/tasks/multi_read`
Forecasting                 | Labor Tasks                                | Create Labor Task                                                    | POST   | `/v2/forecasting/tasks`
Forecasting                 | Labor Tasks                                | Create Labor Tasks                                                   | POST   | `/v2/forecasting/tasks/multi_create`
Forecasting                 | Labor Tasks                                | Update Labor Task by ID                                              | PUT    | `/v2/forecasting/tasks/{id}`
Forecasting                 | Labor Tasks                                | Update Labor Tasks                                                   | POST   | `/v2/forecasting/tasks/multi_update`
Forecasting                 | Labor Tasks                                | Delete Labor Task by ID                                              | DELETE | `/v2/forecasting/tasks/{id}`
Forecasting                 | Labor Tasks                                | Delete Labor Tasks                                                   | POST   | `/v2/forecasting/tasks/multi_delete`
Forecasting                 | Task Groups                                | Retrieve All Task Groups or by Name or Generic Department            | GET    | `/v2/forecasting/task_groups`
Forecasting                 | Task Groups                                | Retrieve a Task Group by ID                                          | GET    | `/v2/forecasting/task_groups/{id}`
Forecasting                 | Task Groups                                | Retrieve Task Groups                                                 | POST   | `/v2/forecasting/task_groups/multi_read`
Forecasting                 | Task Groups                                | Create Task Group                                                    | POST   | `/v2/forecasting/task_groups`
Forecasting                 | Task Groups                                | Create Task Groups                                                   | POST   | `/v2/forecasting/task_groups/multi_create`
Forecasting                 | Task Groups                                | Update Task Group by ID                                              | PUT    | `/v2/forecasting/task_groups/{id}`
Forecasting                 | Task Groups                                | Update Task Groups                                                   | POST   | `/v2/forecasting/task_groups/multi_update`
Forecasting                 | Task Groups                                | Delete Task Group by ID                                              | DELETE | `/v2/forecasting/task_groups/{id}`
Forecasting                 | Task Groups                                | Delete Task Groups                                                   | POST   | `/v2/forecasting/task_groups/multi_delete`
People > Person Assignments | Minor Rule and School Calendar Assignments | Retrieve Minor Rule and School Calendar Assignments by Person Number | GET    | `/v2/commons/persons/minor_rules`
People > Person Assignments | Minor Rule and School Calendar Assignments | Retrieve Minor Rule and School Calendar Assignments by ID            | GET    | `/v2/commons/persons/minor_rules/{person_id}`
People > Person Assignments | Minor Rule and School Calendar Assignments | Retrieve Minor Rule and School Calendar Assignments                  | POST   | `/v2/commons/persons/minor_rules/multi_read`
People > Person Assignments | Minor Rule and School Calendar Assignments | Update Minor Rule and School Calendar Assignments by ID              | PUT    | `/v2/commons/persons/minor_rules/{person_id}`
People > Person Assignments | Minor Rule and School Calendar Assignments | Update Minor Rule and School Calendar Assignments                    | POST   | `/v2/commons/persons/minor_rules/multi_upsert`
People > Person Assignments | Paycode Value Profile Assignments          | Retrieve Paycode Value Profile Assignment by Person Number           | GET    | `/v2/commons/persons/paycode_value_profiles`
People > Person Assignments | Paycode Value Profile Assignments          | Retrieve Paycode Value Profile Assignment by ID                      | GET    | `/v2/commons/persons/paycode_value_profiles/{personId}`
People > Person Assignments | Paycode Value Profile Assignments          | Retrieve Paycode Value Profile Assignments                           | POST   | `/v2/commons/persons/paycode_value_profiles/multi_read`
People > Person Assignments | Paycode Value Profile Assignments          | Update Paycode Value Profile Assignment by ID                        | PUT    | `/v2/commons/persons/paycode_value_profiles/{personId}`
People > Person Assignments | Paycode Value Profile Assignments          | Update Paycode Value Profile Assignments                             | POST   | `/v2/commons/persons/paycode_value_profiles/multi_update`
People > Person Assignments | Paycode Value Profile Assignments          | Delete Paycode Value Profile Assignment by ID                        | DELETE | `/v2/commons/persons/paycode_value_profiles/{personId}`
People > Person Assignments | Paycode Value Profile Assignments          | Delete Paycode Value Profile Assignments                             | POST   | `/v2/commons/persons/paycode_value_profiles/multi_delete`
People > Person Assignments | Schedule Rule Overrides                    | Retrieve Schedule Rule Override by ID                                | GET    | `/v2/commons/persons/schedule_rule_overrides/{person_id}`
People > Person Assignments | Schedule Rule Overrides                    | Retrieve All Schedule Rule Overrides or by Person Number             | GET    | `/v2/commons/persons/schedule_rule_overrides`
People > Person Assignments | Schedule Rule Overrides                    | Retrieve Schedule Rule Overrides                                     | POST   | `/v2/commons/persons/schedule_rule_overrides/multi_read`
People > Person Assignments | Scheduling Employee Preferences            | Retrieve Employee Preferences by ID                                  | GET    | `/v2/commons/persons/scheduling_employee_preferences/{personId}`
People > Person Assignments | Scheduling Employee Preferences            | Retrieve Employee Preferences by Person Number                       | GET    | `/v2/commons/persons/scheduling_employee_preferences`
People > Person Assignments | Scheduling Employee Preferences            | Retrieve Employee Preferences                                        | POST   | `/v2/commons/persons/scheduling_employee_preferences/multi_read`
Timekeeping Setup           | Accrual Profiles                           | Retrieve All Accrual Profiles                                        | GET    | `/v2/timekeeping/setup/accrual_profiles`
Timekeeping Setup           | Accrual Profiles                           | Retrieve Accrual Profile by ID                                       | GET    | `/v2/timekeeping/setup/accrual_profiles/{id}`
Timekeeping Setup           | Bonus and Deduction Rules                  | Retrieve Bonus or Deduction Rule by ID                               | GET    | `/v2/timekeeping/setup/deduct_rules/{id}`
Timekeeping Setup           | Bonus and Deduction Rules                  | Retrieve Bonus and Deduction Rules                                   | GET    | `/v2/timekeeping/setup/deduct_rules`
Timekeeping Setup           | Employment Terms                           | Retrieve All Employment Terms                                        | GET    | `/v2/timekeeping/setup/employment_terms`
Timekeeping Setup           | Employment Terms                           | Retrieve Employment Term by ID                                       | GET    | `/v2/timekeeping/setup/employment_terms/{id}`
Timekeeping Setup           | Paycodes for Timekeeping                   | Retrieve Paycodes as Employee                                        | GET    | `/v2/timekeeping/setup/employee_pay_codes`
Timekeeping Setup           | Paycodes for Timekeeping                   | Retrieve Paycode by ID as Employee                                   | GET    | `/v2/timekeeping/setup/employee_pay_codes/{id}`
Timekeeping Setup           | Work Rules                                 | Retrieve Work Rules as Manager                                       | GET    | `/v2/timekeeping/setup/work_rules`
Timekeeping Setup           | Work Rules                                 | Retrieve Work Rule by ID as Manager                                  | GET    | `/v2/timekeeping/setup/work_rules/{id}`

## Dimensions R8 {#R8}

The following operations were added to the API in Dimensions R8:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Common Resources I          | Symbolic Periods                        | Retrieve Symbolic Periods Grouped by Type                       | POST   | `/v1/commons/symbolicperiod/types`
Common Resources I          | Symbolic Purposes                       | Retrieve All Symbolic Purposes or by Name                       | GET    | `/v1/commons/symbolic_purposes`
Common Resources I          | Symbolic Purposes                       | Retrieve Symbolic Purpose by ID                                 | GET    | `/v1/commons/symbolic_purposes/{id}`
Common Resources I          | Symbolic Purposes                       | Create Symbolic Purpose                                         | POST   | `/v1/commons/symbolic_purposes`
Common Resources I          | Symbolic Purposes                       | Update Symbolic Purpose by ID                                   | PUT    | `/v1/commons/symbolic_purposes/{id}`
Common Resources I          | Symbolic Purposes                       | Delete Symbolic Purpose by ID                                   | DELETE | `/v1/commons/symbolic_purposes/{id}`
Forecasting                 | Actual Volume                           | Retrieve Actual Volume by Sites                                 | POST   | `/v1/forecasting/actual_volume/apply_read`
Forecasting                 | Generic Departments                     | Retrieve All Generic Departments or by Name                     | GET    | `/v1/forecasting/generic_departments`
Forecasting                 | Generic Departments                     | Retrieve Generic Department by ID                               | GET    | `/v1/forecasting/generic_departments/{id}`
Forecasting                 | Labor Budget                            | Retrieve Labor Budget Values                                    | POST   | `/v1/forecasting/labor_budget/multi_read`
Forecasting                 | Labor Standards                         | Create Labor Standard                                           | POST   | `/v1/forecasting/labor_standards`
Forecasting                 | Labor Standards                         | Create Labor Standards                                          | POST   | `/v1/forecasting/labor_standards/multi_create`
Forecasting                 | Labor Standards                         | Update Labor Standards                                          | POST   | `/v1/forecasting/labor_standards/multi_update`
Forecasting                 | Labor Standards                         | Delete Labor Standard by ID                                     | DELETE | `/v1/forecasting/labor_standards/{id}`
Forecasting                 | Labor Standards                         | Delete Labor Standards                                          | POST   | `/v1/forecasting/labor_standards/multi_delete`
Forecasting                 | Task Groups                             | Retrieve Task Groups by Name or Generic Department              | GET    | `/v1/forecasting/task_groups`
Forecasting                 | Task Groups                             | Retrieve a Task Group by ID                                     | GET    | `/v1/forecasting/task_groups/{id}`
Forecasting                 | Task Groups                             | Retrieve Task Groups                                            | POST   | `/v1/forecasting/task_groups/multi_read`
Forecasting                 | Task Groups                             | Create Task Group                                               | POST   | `/v1/forecasting/task_groups`
Forecasting                 | Task Groups                             | Create Task Groups                                              | POST   | `/v1/forecasting/task_groups/multi_create`
Forecasting                 | Task Groups                             | Update Task Group by ID                                         | PUT    | `/v1/forecasting/task_groups/{id}`
Forecasting                 | Task Groups                             | Update Task Groups                                              | POST   | `/v1/forecasting/task_groups/multi_update`
Forecasting                 | Task Groups                             | Delete Task Group by ID                                         | DELETE | `/v1/forecasting/task_groups/{id}`
Forecasting                 | Task Groups                             | Delete Task Groups                                              | POST   | `/v1/forecasting/task_groups/multi_delete`
Forecasting                 | Labor Tasks                             | Retrieve All Labor Tasks or by Specification                    | GET    | `/v1/forecasting/tasks`
Forecasting                 | Labor Tasks                             | Retrieve Labor Task by ID                                       | GET    | `/v1/forecasting/tasks/{id}`
Forecasting                 | Labor Tasks                             | Retrieve Labor Tasks                                            | POST   | `/v1/forecasting/tasks/multi_read`
Forecasting                 | Labor Tasks                             | Create Labor Task                                               | POST   | `/v1/forecasting/tasks`
Forecasting                 | Labor Tasks                             | Create Labor Tasks                                              | POST   | `/v1/forecasting/tasks/multi_create`
Forecasting                 | Labor Tasks                             | Update Labor Task by ID                                         | PUT    | `/v1/forecasting/tasks/{id}`
Forecasting                 | Labor Tasks                             | Update Labor Tasks                                              | POST   | `/v1/forecasting/tasks/multi_update`
Forecasting                 | Labor Tasks                             | Delete Labor Task by ID                                         | DELETE | `/v1/forecasting/tasks/{id}`
Forecasting                 | Labor Tasks                             | Delete Labor Tasks                                              | POST   | `/v1/forecasting/tasks/multi_delete`
Healthcare Analytics        | Work Unit Hyperfind Profiles            | Retrieve All Work Unit Hyperfind Profiles                       | GET    | `/v1/hca/work_unit_hyperfind_profiles`
Healthcare Analytics        | Work Unit Hyperfind Profiles            | Create or Update Work Unit Hyperfind Profiles                   | POST   | `/v1/hca/work_unit_hyperfind_profiles/multi_upsert`
Healthcare Analytics        | Work Units                              | Retrieve All Work Units                                         | GET    | `/v1/commons/work_units`
Healthcare Analytics        | Work Units                              | Create or Update Work Units                                     | POST   | `/v1/commons/work_units/multi_upsert`
People                      | Employee Glance Settings                | Retrieve All Employee Glance Settings or by Name                | GET    | `/v1/commons/employee_glance_settings`
People                      | Employee Glance Settings                | Retrieve Employee Glance Setting by ID                          | GET    | `/v1/commons/employee_glance_settings/{id}`
People                      | Employee Glance Settings                | Retrieve Employee Glance Settings                               | POST   | `/v1/commons/employee_glance_settings/multi_read`
People                      | Employee Glance Settings                | Create Employee Glance Setting                                  | POST   | `/v1/commons/employee_glance_settings`
People                      | Employee Glance Settings                | Create or Update Employee Glance Settings                       | POST   | `/v1/commons/employee_glance_settings/multi_upsert`
People                      | Employee Glance Settings                | Update Employee Glance Setting by ID                            | PUT    | `/v1/commons/employee_glance_settings/{id}`
People                      | Employee Glance Settings                | Delete Employee Glance Setting by ID                            | DELETE | `/v1/commons/employee_glance_settings/{id}`
People                      | Employee Glance Settings                | Delete Employee Glance Settings                                 | POST   | `/v1/commons/employee_glance_settings/multi_delete`
Timekeeping > Attestations  | Attestation Display and Submit Forms    | Create Attestation Display Form                                 | POST   | `/v1/timekeeping/attestation/displayed_forms`
Timekeeping > Attestations  | Attestation Display and Submit Forms    | Create Attestation Submit Form                                  | POST   | `/v1/timekeeping/attestation/submitted_forms`
Timekeeping Setup           | Timecard Add-On Group Options           | Retrieve Timecard Add-On Group Options                          | GET    | `/v1/timekeeping/setup/timecard_addon_groups`
Work                        | Activity Transactions                   | Retrieve Activity Transactions                                  | POST   | `/v1/work/activity_transactions/multi_read`
Work                        | Activity Query Resources                | Retrieve All Query Types                                        | GET    | `/v1/work/queries/setup/query_types`

## Dimensions R7 Update 3 {#R7U3}

The following operations were added to the API in Dimensions R7 Update 3:

Domain                      | Resource                                | Operation                                                       | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                | ------ | ----------------
Forecasting                 | Adjustment Driver Settings              | Retrieve Adjustment Driver Settings by ID                       | GET    | `/v1/forecasting/adjustment_driver_settings/{id}`
Forecasting                 | Adjustment Driver Settings              | Retrieve All Adjustment Driver Settings or by Name              | GET    | `/v1/forecasting/adjustment_driver_settings`
Forecasting                 | Adjustment Driver Settings              | Retrieve Adjustment Driver Settings by Location                 | POST   | `/v1/forecasting/adjustment_driver_settings/apply_read`
Forecasting                 | Adjustment Driver Settings              | Retrieve Adjustment Driver Settings                             | POST   | `/v1/forecasting/adjustment_driver_settings/multi_read`
Forecasting                 | Adjustment Driver Settings              | Create Adjustment Driver Settings                               | POST   | `/v1/forecasting/adjustment_driver_settings`
Forecasting                 | Adjustment Driver Settings              | Create Multiple Adjustment Driver Settings                      | POST   | `/v1/forecasting/adjustment_driver_settings/multi_create`
Forecasting                 | Adjustment Driver Settings              | Update Adjustment Driver Settings by ID                         | PUT    | `/v1/forecasting/adjustment_driver_settings/{id}`
Forecasting                 | Adjustment Driver Settings              | Update Multiple Adjustment Driver Settings                      | POST   | `/v1/forecasting/adjustment_driver_settings/multi_update`
Forecasting                 | Adjustment Driver Settings              | Delete Adjustment Driver Settings by ID                         | DELETE | `/v1/forecasting/adjustment_driver_settings/{id}`
Forecasting                 | Adjustment Driver Settings              | Delete Multiple Adjustment Driver Settings                      | POST   | `/v1/forecasting/adjustment_driver_settings/multi_delete`
Forecasting                 | Labor Constraint Profiles               | Retrieve a Labor Constraint Profile by ID                       | GET    | `/v1/forecasting/labor_constraint_profiles/{id}`
Forecasting                 | Labor Constraint Profiles               | Retrieve All Labor Constraint Profiles or by Name               | GET    | `/v1/forecasting/labor_constraint_profiles`
Forecasting                 | Labor Constraint Profiles               | Retrieve a Labor Constraint Profile by Location                 | POST   | `/v1/forecasting/labor_constraint_profiles/apply_read`
Forecasting                 | Labor Constraint Profiles               | Retrieve Labor Constraint Profiles                              | POST   | `/v1/forecasting/labor_constraint_profiles/multi_read`
Forecasting                 | Labor Constraint Profiles               | Create a Labor Constraint Profile                               | POST   | `/v1/forecasting/labor_constraint_profiles`
Forecasting                 | Labor Constraint Profiles               | Create Labor Constraint Profiles                                | POST   | `/v1/forecasting/labor_constraint_profiles/multi_create`
Forecasting                 | Labor Constraint Profiles               | Update a Labor Constraint Profile by ID                         | PUT    | `/v1/forecasting/labor_constraint_profiles/{id}`
Forecasting                 | Labor Constraint Profiles               | Update Labor Constraint Profiles                                | POST   | `/v1/forecasting/labor_constraint_profiles/multi_update`
Forecasting                 | Labor Constraint Profiles               | Delete a Labor Constraint Profile by ID                         | DELETE | `/v1/forecasting/labor_constraint_profiles/{id}`
Forecasting                 | Labor Constraint Profiles               | Delete Labor Constraint Profiles                                | POST   | `/v1/forecasting/labor_constraint_profiles/multi_delete`
Forecasting                 | Labor Constraint Settings               | Retrieve Labor Constraint Settings by ID                        | GET    | `/v1/forecasting/labor_constraint_settings/{id}`
Forecasting                 | Labor Constraint Settings               | Retrieve All Labor Constraint Settings or by Name               | GET    | `/v1/forecasting/labor_constraint_settings`
Forecasting                 | Labor Constraint Settings               | Retrieve Labor Constraint Settings                              | POST   | `/v1/forecasting/labor_constraint_settings/multi_read`
Forecasting                 | Labor Constraint Settings               | Create Labor Constraint Settings                                | POST   | `/v1/forecasting/labor_constraint_settings`
Forecasting                 | Labor Constraint Settings               | Create Multiple Labor Constraint Settings                       | POST   | `/v1/forecasting/labor_constraint_settings/multi_create`
Forecasting                 | Labor Constraint Settings               | Update Labor Constraint Settings by ID                          | PUT    | `/v1/forecasting/labor_constraint_settings/{id}`
Forecasting                 | Labor Constraint Settings               | Update Multiple Labor Constraint Settings                       | POST   | `/v1/forecasting/labor_constraint_settings/multi_update`
Forecasting                 | Labor Constraint Settings               | Delete Labor Constraint Settings by ID                          | DELETE | `/v1/forecasting/labor_constraint_settings/{id}`
Forecasting                 | Labor Constraint Settings               | Delete Multiple Labor Constraint Settings                       | POST   | `/v1/forecasting/labor_constraint_settings/multi_delete`
Forecasting                 | Labor Constraint Settings               | Retrieve Period Distributions                                   | GET    | `/v1/forecasting/labor_constraint_settings/setup/period_distributions`
Forecasting                 | Labor Constraint Settings               | Retrieve Labor Forecast Distribution Method Types               | GET    | `/v1/forecasting/labor_constraint_settings/setup/labor_forecast_distribution_method_types`
Forecasting                 | Labor Constraint Settings               | Retrieve Adjustment Types                                       | GET    | `/v1/forecasting/labor_constraint_settings/setup/adjustment_types`
Forecasting                 | Labor Constraint Settings               | Retrieve Control Types                                          | GET    | `/v1/forecasting/labor_constraint_settings/setup/control_types`
Forecasting                 | Static Driver Assignments               | Update Static Driver Assignments                                | POST   | `/v1/forecasting/static_driver_assignments/multi_update`

## Dimensions R7 Update 2 {#R7U2}

The following operations were added to the API in Dimensions R7 Update 2:

Domain                      | Resource                                | Operation                                                        | Method | URL endpoint
----------------            | ----------------                        | ----------------                                                 | ------ | ----------------
Common Resources I          | Delegate Profiles                       | Retrieve Summary of Asynchronous Delegate Profile Jobs           | GET    | `/v1/commons/delegate_profiles/async`
Common Resources I          | Delegate Profiles                       | Retrieve Delegate Profile Asynchronous Request Status by Key     | GET    | `/v1/commons/delegate_profiles/async/{executionKey}/status`
Common Resources I          | Delegate Profiles                       | Retrieve Asynchronous Response Payload by Key                    | GET    | `/v1/commons/delegate_profiles/async/{executionKey}/response`
Common Resources I          | Delegate Profiles                       | Add or Remove Delegate Profile Delegates Asynchronously          | POST   | `/v1/commons/delegate_profiles/apply_upsert/async`
Common Resources I          | Delegate Profiles                       | Create or Update Delegate Profiles Asynchronously                | POST   | `/v1/commons/delegate_profiles/multi_upsert/async`
Forecasting                 | Labor Forecast                          | Retrieve Labor Forecasts for Multiple Locations                  | POST   | `/v1/forecasting/labor_forecast/multi_read`
Forecasting                 | Volume Forecasts                        | Retrieve Volume Forecasts                                        | POST   | `/v1/forecasting/volume_forecasts/multi_read`
Scheduling                  | Paycode Edits—Scheduling                | Create Paycode Edits with Options (replaces R7 Update 1 version) | POST   | `/v1/scheduling/schedule/pay_code_edits/apply_import`

## Dimensions R7 Update 1 {#R7U1}

The following operations were added to the API in Dimensions R7 Update 1:

Domain                      | Resource                                | Operation                                            | Method | URL endpoint
----------------            | ----------------                        | ----------------                                     | ------ | ----------------
Common Resources            | Known IP Addresses                      | Retrieve Known IP Addresses                          | GET    | `/v1/commons/known_ip_addresses`
Common Resources            | Known IP Addresses                      | Retrieve Known IP Address by ID                      | GET    | `/v1/commons/known_ip_addresses/{id}`
Common Resources            | Known IP Addresses                      | Create Known IP Address                              | POST   | `/v1/commons/known_ip_addresses`
Common Resources            | Known IP Addresses                      | Create or Update Known IP Addresses                  | POST   | `/v1/commons/known_ip_addresses/multi_upsert`
Common Resources            | Known IP Addresses                      | Update Known IP Address by ID                        | PUT    | `/v1/commons/known_ip_addresses/{id}`
Common Resources            | Known IP Addresses                      | Delete Known IP Address by ID                        | DELETE | `/v1/commons/known_ip_addresses/{id}`
Forecasting                 | Labor Forecast                          | Create Labor Forecasts                               | POST   | `/v1/forecasting/labor_forecast/multi_create`
Healthcare Analytics        | Volume Process Status                   | Retrieve Volume Process Status by Key                | GET    | `/v1/hca/volume/{executionKey}/status`
People > Person Assignments | Pattern Template Profile Assignments    | Retrieve Pattern Template Profile Assignments by Person ID     | GET    | `/v1/commons/persons/pattern_template_profiles/{personId}`
People > Person Assignments | Pattern Template Profile Assignments    | Retrieve Pattern Template Profile Assignments by Person Number | GET    | `/v1/commons/persons/pattern_template_profiles`
People > Person Assignments | Pattern Template Profile Assignments    | Retrieve Pattern Template Profile Assignments                  | POST   | `/v1/commons/persons/pattern_template_profiles/multi_read`
People > Person Assignments | Pattern Template Profile Assignments    | Update Pattern Template Profile Assignment by Person ID        | PUT    | `/v1/commons/persons/pattern_template_profiles/{personId}`
People > Person Assignments | Pattern Template Profile Assignments    | Update Pattern Template Profile Assignments                    | POST   | `/v1/commons/persons/pattern_template_profiles/multi_update`
People > Person Assignments | Pattern Template Profile Assignments    | Delete Pattern Template Profile Assignment by Person ID        | DELETE | `/v1/commons/persons/pattern_template_profiles/{personId}`
People > Person Assignments | Pattern Template Profile Assignments    | Delete Pattern Template Profile Assignments                    | POST   | `/v1/commons/persons/pattern_template_profiles/multi_delete`
People > Person Assignments | Shift Template Profile Assignments      | Retrieve Shift Template Profile Assignments by Person ID       | GET    | `/v1/commons/persons/shift_template_profiles/{personId}`
People > Person Assignments | Shift Template Profile Assignments      | Retrieve Shift Template Profile Assignments by Person Number   | GET    | `/v1/commons/persons/shift_template_profiles`
People > Person Assignments | Shift Template Profile Assignments      | Retrieve Shift Template Profile Assignments                    | POST   | `/v1/commons/persons/shift_template_profiles/multi_read`
People > Person Assignments | Shift Template Profile Assignments      | Update Shift Template Profile Assignment by Person ID          | PUT    | `/v1/commons/persons/shift_template_profiles/{personId}`
People > Person Assignments | Shift Template Profile Assignments      | Update Shift Template Profile Assignments                      | POST   | `/v1/commons/persons/shift_template_profiles/multi_update`
People > Person Assignments | Shift Template Profile Assignments      | Delete Shift Template Profile Assignment by Person ID          | DELETE | `/v1/commons/persons/shift_template_profiles/{personId}`
People > Person Assignments | Shift Template Profile Assignments      | Delete Shift Template Profile Assignments                      | POST   | `/v1/commons/persons/shift_template_profiles/multi_delete`
People > Person Assignments | Worker Type Assignments                 | Retrieve Worker Type Assignments by Person ID                  | GET    | `/v1/commons/persons/worker_types/{personId}`
People > Person Assignments | Worker Type Assignments                 | Retrieve Worker Type Assignments by Person Number              | GET    | `/v1/commons/persons/worker_types`
People > Person Assignments | Worker Type Assignments                 | Retrieve Worker Type Assignments                               | POST   | `/v1/commons/persons/worker_types/multi_read`
People > Person Assignments | Worker Type Assignments                 | Update Worker Type Assignment by Person ID                     | PUT    | `/v1/commons/persons/worker_types/{personId}`
People > Person Assignments | Worker Type Assignments                 | Update Worker Type Assignments                                 | POST   | `/v1/commons/persons/worker_types/multi_update`
People > Person Assignments | Worker Type Assignments                 | Delete Worker Type Assignment by Person ID                     | DELETE | `/v1/commons/persons/worker_types/{personId}`
People > Person Assignments | Worker Type Assignments                 | Delete Worker Type Assignments                                 | POST   | `/v1/commons/persons/worker_types/multi_delete`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Retrieve Holiday and Unscheduled Day Request Settings by ID            | GET    | `/v1/scheduling/holiday_request_settings/{id}`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Retrieve Holiday and Unscheduled Day Request Settings by Specification | GET    | `/v1/scheduling/holiday_request_settings`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Retrieve Holiday and Unscheduled Day Request Settings by Object Refs   | POST   | `/v1/scheduling/holiday_request_settings/multi_read`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Create Holiday and Unscheduled Day Request Settings                    | POST   | `/v1/scheduling/holiday_request_settings`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Create Multiple Holiday and Unscheduled Day Request Settings           | POST   | `/v1/scheduling/holiday_request_settings/multi_create`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Update Holiday and Unscheduled Day Request Settings by ID              | PUT    | `/v1/scheduling/holiday_request_settings/{id}`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Update Multiple Holiday and Unscheduled Day Request Settings           | POST   | `/v1/scheduling/holiday_request_settings/multi_update`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Delete Holiday and Unscheduled Day Request Settings by ID              | DELETE | `/v1/scheduling/holiday_request_settings/{id}`
Scheduling Setup            | Holiday and Unscheduled Day Request Settings | Delete Multiple Holiday and Unscheduled Day Request Settings           | POST   | `/v1/scheduling/holiday_request_settings/multi_delete`
Scheduling Setup            | Pattern Template Profiles               | Retrieve All Pattern Template Profiles               | GET    | `/v1/scheduling/pattern_template_profiles`
Scheduling Setup            | Shift Template Profiles                 | Retrieve All Shift Template Profiles                 | GET    | `/v1/scheduling/shift_templates_profiles`
Scheduling Setup            | Worker Types                            | Retrieve All Worker Types                            | GET    | `/v1/scheduling/worker_types`
Scheduling                  | Paycode Edits—Scheduling                | Create Paycode Edits with Options                    | POST   | `/v1/scheduling/schedule/pay_code_edits/import`
Work                        | Activity Assignments                    | Retrieve Activities for Multiple Employees           | POST   | `/v1/work/employee_activities/multi_read`

## Dimensions R7 {#R7}

The following operations were added to the API in Dimensions R7:

Domain                      | Resource                                | Operation                                            | Method | URL endpoint
----------------            | ----------------                        | ----------------                                     | ------ | ----------------
Authentication and security | Manage Dimensions UI sessions           | Log Out a Dimensions UI Session                      | POST   | `/v1/auth/logout`
Common Resources            | Cost Centers                            | Retrieve Paginated List of Cost Centers              | POST   | `/v1/commons/cost_centers/apply_read`
Common Resources            | Delegate Profiles                       | Retrieve All Delegate Profiles or by Name            | GET    | `/v1/commons/delegate_profiles`
Common Resources            | Delegate Profiles                       | Retrieve Delegate Profile by ID                      | GET    | `/v1/commons/delegate_profiles/{id}`
Common Resources            | Delegate Profiles                       | Retrieve Delegate Profiles                           | POST   | `/v1/commons/delegate_profiles/multi_read`
Common Resources            | Delegate Profiles                       | Create Delegate Profile                              | POST   | `/v1/commons/delegate_profiles`
Common Resources            | Delegate Profiles                       | Create or Update Delegate Profiles                   | POST   | `/v1/commons/delegate_profiles/multi_upsert`
Common Resources            | Delegate Profiles                       | Update Delegate Profile by ID                        | PUT    | `/v1/commons/delegate_profiles/{id}`
Common Resources            | Delegate Profiles                       | Delete Delegate Profile by ID                        | DELETE | `/v1/commons/delegate_profiles/{id}`
Common Resources            | Delegate Profiles                       | Delete Delegate Profiles                             | POST   | `/v1/commons/delegate_profiles/multi_delete`
Common Resources            | Delegate Profiles                       | Add or Remove Delegate Profile Delegates             | POST   | `/v1/commons/delegate_profiles/apply_upsert`
Common Resources > Known Places | GPS Known Places                    | Retrieve All Known Places                            | GET    | `/v1/commons/known_places`
Common Resources > Known Places | GPS Known Places                    | Retrieve Known Place by ID                           | GET    | `/v1/commons/known_places/{id}`
Common Resources > Known Places | GPS Known Places                    | Create Known Place                                   | POST   | `/v1/commons/known_places`
Common Resources > Known Places | GPS Known Places                    | Create Known Places                                  | POST   | `/v1/commons/known_places/multi_create`
Common Resources > Known Places | GPS Known Places                    | Create or Update Known Places                        | POST   | `/v1/commons/known_places/multi_upsert`
Common Resources > Known Places | GPS Known Places                    | Update Known Place by ID                             | PUT    | `/v1/commons/known_places/{id}`
Common Resources > Known Places | GPS Known Places                    | Delete Known Place by ID                             | DELETE | `/v1/commons/known_places/{id}`
Common Resources > Known Places | GPS Known Places                    | Delete Known Places                                  | POST   | `/v1/commons/known_places/multi_delete`
Common Resources            | Labor Category Lists                    | Retrieve Labor Category List of Entries              | POST   | `/v1/commons/labor_category_lists/apply_read`
Common Resources            | Labor Category Profiles                 | Retrieve Paginated List of Labor Category Profiles   | POST   | `/v1/commons/labor_category_profiles/apply_read`
Common Resources            | Labor Category Profiles                 | Retrieve Labor Category Profiles                     | POST   | `/v1/commons/labor_category_profiles/multi_read`
Common Resources            | Labor Category Entries                  | Retrieve Paginated List of Labor Category Entries    | POST   | `/v1/commons/labor_entries/apply_read`
Common Resources            | TeleTime IP User Profiles               | Retrieve TeleTime IP User Profiles                   | GET    | `/v1/commons/teletime_ip/user_profiles`
Common Resources            | Timecard Approval Methods               | Retrieve Timecard Approval Methods                   | GET    | `/v1/commons/timecard_approval_methods`
Common Resources            | Transfer Display Profiles               | Retrieve All Transfer Display Profiles               | GET    | `/v1/commons/transfer_display_profiles`
Common Resources            | Transfer Display Profiles               | Retrieve Transfer Display Profile by ID              | GET    | `/v1/commons/transfer_display_profiles/{id}`
Common Resources            | Transfer Display Profiles               | Create Transfer Display Profile                      | POST   | `/v1/commons/transfer_display_profiles`
Common Resources            | Transfer Display Profiles               | Update Transfer Display Profile by ID                | PUT    | `/v1/commons/transfer_display_profiles/{id}`
Common Resources            | Transfer Display Profiles               | Delete Transfer Display Profile by ID                | DELETE | `/v1/commons/transfer_display_profiles/{id}`
Employee Self-Service       | Fill Open Shifts                        | Send Open Shift Notifications                        | POST   | `/v1/scheduling/fill_open_shifts/notify`
Employee Self-Service       | Fill Open Shifts                        | Accept Open Shift                                    | POST   | `/v1/scheduling/fill_open_shifts/accept`
Employee Self-Service       | Fill Open Shifts                        | Decline Open Shift                                   | POST   | `/v1/scheduling/fill_open_shifts/decline`
Forecasting                 | Labor Forecast Analyzer                 | Execute Labor Forecast Analyzer                      | POST   | `/v1/forecasting/labor_forecast_analyzer/apply_create`
Healthcare Analytics        | Charge Masters                          | Retrieve All Charge Masters                          | GET    | `/v1/hca/volume/charge_masters`
Healthcare Analytics        | Charge Masters                          | Create or Update Charge Masters                      | POST   | `/v1/hca/volume/charge_masters/multi_upsert`
Healthcare Analytics        | Charge Masters                          | Retrieve Volume Labels                               | POST   | `/v1/hca/volume/charge_masters/volume_labels/multi_read`
Healthcare Analytics        | Raw Volume                              | Create or Update Raw Volume                          | POST   | `/v1/hca/volume/raw_volume/multi_upsert`
Healthcare Analytics        | Volume Copy Maps                        | Retrieve All Volume Copy Maps                        | GET    | `/v1/hca/volume/volume_copy_maps`
Healthcare Analytics        | Volume Copy Maps                        | Create or Update Volume Copy Maps                    | POST   | `/v1/hca/volume/volume_copy_maps/multi_upsert`
Healthcare Analytics        | Volume Copy Override Maps               | Retrieve All Volume Copy Override Maps               | GET    | `/v1/hca/volume/volume_copy_override_maps`
Healthcare Analytics        | Volume Copy Override Maps               | Create or Update Volume Copy Override Maps           | POST   | `/v1/hca/volume/volume_copy_override_maps/multi_upsert`
Healthcare Analytics        | Volume Recalculation                    | Recalculate Volume                                   | POST   | `/v1/hca/volume/recalculate/async`
Healthcare Analytics        | Work Unit Hyperfinds                    | Retrieve All Work Unit Hyperfinds                    | GET    | `/v1/hca/work_unit_hyperfinds`
Healthcare Analytics        | Work Unit Hyperfinds                    | Create or Update Work Unit Hyperfinds                | POST   | `/v1/hca/work_unit_hyperfinds/multi_upsert`
Healthcare Analytics        | Work Unit Hyperfinds                    | Execute Work Unit Hyperfind                          | POST   | `/v1/hca/work_unit_hyperfinds/apply_read`
People                      | Aggregated Person Assignments           | Retrieve All Assignments by Person ID                | GET    | `/v1/commons/persons/assignments/{id}`
People                      | Aggregated Person Assignments           | Retrieve All Assignments for Multiple People         | POST   | `/v1/commons/persons/assignments/multi_read`
People                      | Aggregated Person Assignments           | Modify Assignments for Multiple People               | POST   | `/v1/commons/persons/assignments/multi_upsert`
People                      | Aggregated Person Assignments           | Retrieve All Assignment Names                        | GET    | `/v1/commons/persons/assignments/names`
People                      | Employee Wage Work Rules                | Retrieve Employee Wage and Work Rules                | POST   | `/v1/commons/persons/wage_work_rules/multi_read`
People                      | Employee Wage Work Rules                | Create or Update Wage and Work Rule Overrides        | POST   | `/v1/commons/persons/wage_work_rules/multi_upsert`
People > Person Assignments | Manager Role Assignments                | Retrieve Manager Role Assignments by ID              | GET    | `/v1/commons/persons/manager_role_assignments/{person_id}`
People > Person Assignments | Manager Role Assignments                | Retrieve Manager Role Assignments by Person Number   | GET    | `/v1/commons/persons/manager_role_assignments`
People > Person Assignments | Manager Role Assignments                | Retrieve Manager Role Assignments                    | POST   | `/v1/commons/persons/manager_role_assignments/multi_read`
People > Person Assignments | Manager Role Assignments                | Update Manager Role Assignments                      | POST   | `/v1/commons/persons/manager_role_assignments/multi_update`
People > Person Assignments | Manager Role Assignments                | Create, Update, or Delete Manager Role Assignments   | POST   | `/v1/commons/persons/manager_role_assignments/apply_upsert`
People > Person Assignments | Schedule Group Profile Assignments    | Retrieve Schedule Group Profile Assignments by Person Number | GET    | `/v1/commons/persons/schedule_group_profiles`
People > Person Assignments | Schedule Group Profile Assignments    | Retrieve Schedule Group Profile Assignments by Person ID     | GET    | `/v1/commons/persons/schedule_group_profiles/{personId}`
People > Person Assignments | Schedule Group Profile Assignments    | Retrieve Schedule Group Profile Assignments                  | POST   | `/v1/commons/persons/schedule_group_profiles/multi_read`
People > Person Assignments | Schedule Group Profile Assignments    | Update Schedule Group Profile Assignment by Person ID        | PUT    | `/v1/commons/persons/schedule_group_profiles/{personId}`
People > Person Assignments | Schedule Group Profile Assignments    | Update Schedule Group Profile Assignments                    | POST   | `/v1/commons/persons/schedule_group_profiles/multi_update`
People > Person Assignments | Schedule Group Profile Assignments    | Delete Schedule Group Profile Assignment by Person ID        | DELETE | `/v1/commons/persons/schedule_group_profiles/{personId}`
People > Person Assignments | Schedule Group Profile Assignments    | Delete Schedule Group Profile Assignments                    | POST   | `/v1/commons/persons/schedule_group_profiles/multi_delete`
People > Person Assignments | Schedule Override Employee Preferences | Retrieve Schedule Override Employee Preferences by Person Number | GET    | `/v1/commons/persons/scheduling_employee_preferences/schedule_generation_overrides`
People > Person Assignments | Schedule Override Employee Preferences | Retrieve Schedule Override Employee Preferences by Person ID     | GET    | `/v1/commons/persons/scheduling_employee_preferences/schedule_generation_overrides/{personId}`
People > Person Assignments | Schedule Override Employee Preferences | Retrieve Schedule Override Employee Preferences                  | POST   | `/v1/commons/persons/scheduling_employee_preferences/schedule_generation_overrides/multi_read`
People > Person Assignments | Schedule Override Employee Preferences | Create or Update Schedule Override Employee Preferences          | POST   | `/v1/commons/persons/scheduling_employee_preferences/schedule_generation_overrides/multi_upsert`
People > Person Assignments | Schedule Override Employee Preferences | Update Schedule Override Employee Preferences by Person ID       | PUT    | `/v1/commons/persons/scheduling_employee_preferences/schedule_generation_overrides/{personId}`
Platform > Integrations     | Integration Executions                 | Download File by Integration                         | GET    | `/v1/platform/integration_executions/{id}/file`
Platform > Integrations     | Integration Executions                 | Retrieve File Names by Integration ID                | GET    | `/v1/platform/integration_executions/{id}/filelist`
Scheduling                  | Call Logs                               | Retrieve Call Log by ID                             | GET    | `/v1/scheduling/call_logs/{id}`
Scheduling                  | Call Logs                               | Retrieve Call Logs                                  | POST   | `/v1/scheduling/call_logs/multi_read`
Scheduling                  | Call Logs                               | Create Call Log                                     | POST   | `/v1/scheduling/call_logs`
Scheduling                  | Call Logs                               | Create Call Logs                                    | POST   | `/v1/scheduling/call_logs/multi_create`
Scheduling                  | Schedule Group Profiles                 | Retrieve All Schedule Group Profiles                | GET    | `/v1/scheduling/scheduling_group_profiles`
Scheduling Setup            | Standard Shift Sets                     | Create Standard Shift Set                           | POST   | `/v1/scheduling/standard_shift_sets`
Scheduling Setup            | Standard Shift Sets                     | Create Standard Shift Sets                          | POST   | `/v1/scheduling/standard_shift_sets/multi_create`
Scheduling Setup            | Standard Shift Sets                     | Update Standard Shift Set by ID                     | PUT    | `/v1/scheduling/standard_shift_sets/{id}`
Scheduling Setup            | Standard Shift Sets                     | Update Standard Shift Sets                          | POST   | `/v1/scheduling/standard_shift_sets/multi_update`
Scheduling Setup            | Standard Shift Sets                     | Delete Standard Shift Set by ID                     | DELETE | `/v1/scheduling/standard_shift_sets/{id}`
Scheduling Setup            | Standard Shift Sets                     | Delete Standard Shift Sets                          | POST   | `/v1/scheduling/standard_shift_sets/multi_delete`
Scheduling Setup            | Standard Shift Set Assignments          | Retrieve Standard Shift Set Location Assignments with Locations | POST   | `/v1/scheduling/standard_shift_sets/assignments/apply_read`
Scheduling Setup            | Standard Shift Set Assignments          | Delete Standard Shift Set Location Assignments                  | POST   | `/v1/scheduling/standard_shift_sets/assignments/multi_delete`
Scheduling Setup            | Standard Shift Set Assignments          | Create or Update Standard Shift Set Location Assignments        | POST   | `/v1/scheduling/standard_shift_sets/assignments/multi_upsert`
Scheduling Setup            | Standard Shift Set Assignments          | Delete Standard Shift Set Location Assignments by Shift Set     | POST   | `/v1/scheduling/standard_shift_sets/assignments/apply_delete`
Scheduling Setup            | Occurrence Definitions                  | Retrieve All Occurrence Definitions or by Name       | GET    | `/v1/scheduling/setup/occurrence_definitions`
Scheduling Setup            | Occurrence Definitions                  | Retrieve Occurrence Definition by ID                 | GET    | `/v1/scheduling/setup/occurrence_definitions/{id}`
Scheduling Setup            | Occurrence Definitions                  | Retrieve Occurrence Definitions                      | POST   | `/v1/scheduling/setup/occurrence_definitions/multi_read`
Scheduling Setup            | Occurrence Definitions                  | Create Occurrence Definition                         | POST   | `/v1/scheduling/setup/occurrence_definitions`
Scheduling Setup            | Occurrence Definitions                  | Create Occurrence Definitions                        | POST   | `/v1/scheduling/setup/occurrence_definitions/multi_create`
Scheduling Setup            | Occurrence Definitions                  | Update Occurrence Definition by ID                   | PUT    | `/v1/scheduling/setup/occurrence_definitions/{id}`
Scheduling Setup            | Occurrence Definitions                  | Update Occurrence Definitions                        | POST   | `/v1/scheduling/setup/occurrence_definitions/multi_update`
Scheduling Setup            | Occurrence Definitions                  | Delete Occurrence Definition by ID                   | DELETE | `/v1/scheduling/setup/occurrence_definitions/{id}`
Scheduling Setup            | Occurrence Definitions                  | Delete Occurrence Definitions                        | POST   | `/v1/scheduling/setup/occurrence_definitions/multi_delete`
Timekeeping Setup           | Combination Rules                       | Retrieve All Combination Rules                       | GET    | `/v1/timekeeping/setup/combination_rules`
Timekeeping Setup           | Combination Rules                       | Retrieve Combination Rule by ID                      | GET    | `/v1/timekeeping/setup/combination_rules/{id}`
Timekeeping Setup           | Combination Rules                       | Retrieve Combination Rules                           | POST   | `/v1/timekeeping/setup/combination_rules/multi_read`
Timekeeping Setup           | Combination Rules                       | Create Combination Rule                              | POST   | `/v1/timekeeping/setup/combination_rules`
Timekeeping Setup           | Combination Rules                       | Create Combination Rules                             | POST   | `/v1/timekeeping/setup/combination_rules/multi_create`
Timekeeping Setup           | Combination Rules                       | Create or Update Combination Rules                   | POST   | `/v1/timekeeping/setup/combination_rules/apply_upsert`
Timekeeping Setup           | Combination Rules                       | Update Combination Rule by ID                        | PUT    | `/v1/timekeeping/setup/combination_rules/{id}`
Timekeeping Setup           | Combination Rules                       | Update Combination Rules                             | POST   | `/v1/timekeeping/setup/combination_rules/multi_update`
Timekeeping Setup           | Combination Rules                       | Delete Combination Rule by ID                        | DELETE | `/v1/timekeeping/setup/combination_rules/{id}`
Timekeeping                 | Combination Rules                       | Delete Combination Rules                             | POST   | `/v1/timekeeping/setup/combination_rules/multi_delete`
Timekeeping                 | Exception Categories                    | Retrieve All Exception Categories                    | GET    | `/v1/timekeeping/exception_categories`
Timekeeping                 | Exception Categories                    | Retrieve Exception Category by ID                    | GET    | `/v1/timekeeping/exception_categories/{id}`
Timekeeping                 | Exception Categories                    | Retrieve Exception Categories                        | POST   | `/v1/timekeeping/exception_categories/multi_read`
Timekeeping                 | Exception Categories                    | Create Exception Category                            | POST   | `/v1/timekeeping/exception_categories`
Timekeeping                 | Exception Categories                    | Create Exception Categories                          | POST   | `/v1/timekeeping/exception_categories/multi_create`
Timekeeping                 | Exception Categories                    | Update Exception Category by ID                      | PUT    | `/v1/timekeeping/exception_categories/{id}`
Timekeeping                 | Exception Categories                    | Update Exception Categories                          | POST   | `/v1/timekeeping/exception_categories/multi_update`
Timekeeping                 | Exception Categories                    | Delete Exception Categories                          | POST   | `/v1/timekeeping/exception_categories/multi_delete`
Timekeeping                 | Exception Categories                    | Delete Exception Category by ID                      | DELETE | `/v1/timekeeping/exception_categories/{id}`
Timekeeping                 | Exception Categories                    | Retrieve All Exception Types                         | GET    | `/v1/timekeeping/exception_types`
Timekeeping                 | Exception Tiles                         | Retrieve All Exception Tiles                         | GET    | `/v1/timekeeping/exception_tiles`
Timekeeping                 | Exception Tiles                         | Retrieve Exception Tile by ID                        | GET    | `/v1/timekeeping/exception_tiles/{id}`
Timekeeping                 | Exception Tiles                         | Update Exception Tile by ID                          | PUT    | `/v1/timekeeping/exception_tiles/{id}`
Timekeeping Setup           | Paycodes—Timekeeping                    | Retrieve Full Paycodes—Manager                       | GET    | `/v1/timekeeping/setup/paycodes`
Timekeeping Setup           | Paycodes—Timekeeping                    | Retrieve Full Paycode by ID—Manager                  | GET    | `/v1/timekeeping/setup/paycodes/{id}`
Timekeeping                 | Timecard Add-On Columns                 | Retrieve Timecard Add-On Columns                     | GET    | `/v1/timekeeping/setup/timecard_addon_columns`
Timekeeping                 | Timecard Add-On Profiles                | Retrieve All Timecard Add-On Profiles                | GET    | `/v1/timekeeping/setup/timecard_addon_profiles`
Timekeeping                 | Timecard Add-On Profiles                | Retrieve Timecard Add-On Profile by ID               | GET    | `/v1/timekeeping/setup/timecard_addon_profiles/{id}`
Timekeeping                 | Timecard Add-On Profiles                | Create Timecard Add-On Profile                       | POST   | `/v1/timekeeping/setup/timecard_addon_profiles`
Timekeeping                 | Timecard Add-On Profiles                | Update Timecard Add-On Profile by ID                 | PUT    | `/v1/timekeeping/setup/timecard_addon_profiles/{id}`
Timekeeping                 | Timecard Add-On Profiles                | Delete Timecard Add-On Profile by ID                 | DELETE | `/v1/timekeeping/setup/timecard_addon_profiles/{id}`
Timekeeping                 | Timecard Add-On Types                   | Retrieve Timecard Add-On Types                       | GET    | `/v1/timekeeping/setup/timecard_addon_types`

## Dimensions R6 Update 4 {#R6U4}

The following operations were added to the API in Dimensions R6 Update 4:

Domain                    | Resource                                | Operation                                            | Method | URL endpoint
----------------          | ----------------                        | ----------------                                     | ------ | ----------------
Platform                  | Menu Items                              | Retrieve All Menu Items                              | GET    | `/v1/platform/user_interface/links`
Platform > Reporting      | Report Data Objects                     | Generate Report Data Object Batched Requests by Name | POST   | `/v1/platform/report_dataobjects/{name}/data/generate_request_batches`
Timekeeping               | Paycodes—Timekeeping                    | Retrieve Paycodes                                    | POST   | `/v1/timekeeping/setup/pay_codes/multi_read`
Timekeeping               | Paycodes—Timekeeping                    | Create Paycode                                       | POST   | `/v1/timekeeping/setup/pay_codes`
Timekeeping               | Paycodes—Timekeeping                    | Create Paycodes                                      | POST   | `/v1/timekeeping/setup/pay_codes/multi_create`
Timekeeping               | Paycodes—Timekeeping                    | Create or Update Paycodes                            | POST   | `/v1/timekeeping/setup/pay_codes/multi_upsert`
Timekeeping               | Paycodes—Timekeeping                    | Update Paycode by ID                                 | PUT    | `/v1/timekeeping/setup/pay_codes/{id}`
Timekeeping               | Paycodes—Timekeeping                    | Update Paycodes                                      | POST   | `/v1/timekeeping/setup/pay_codes/multi_update`
Timekeeping               | Paycodes—Timekeeping                    | Delete Paycode by ID                                 | DELETE | `/v1/timekeeping/setup/pay_codes/{id}`
Timekeeping               | Paycodes—Timekeeping                    | Delete Paycodes                                      | POST   | `/v1/timekeeping/setup/pay_codes/multi_delete`
Timekeeping               | Paycode Distributions                   | Retrieve All Paycode Distributions or by Name        | GET    | `/v1/timekeeping/setup/pay_code_distributions`
Timekeeping               | Paycode Distributions                   | Retrieve Paycode Distribution by ID                  | GET    | `/v1/timekeeping/setup/pay_code_distributions/{id}`
Timekeeping               | Paycode Distributions                   | Retrieve Paycode Distributions                       | POST   | `/v1/timekeeping/setup/pay_code_distributions/multi_read`
Timekeeping               | Paycode Distributions                   | Create Paycode Distribution                          | POST   | `/v1/timekeeping/setup/pay_code_distributions`
Timekeeping               | Paycode Distributions                   | Create Paycode Distributions                         | POST   | `/v1/timekeeping/setup/pay_code_distributions/multi_create`
Timekeeping               | Paycode Distributions                   | Update Paycode Distribution by ID                    | PUT    | `/v1/timekeeping/setup/pay_code_distributions/{id}`
Timekeeping               | Paycode Distributions                   | Update Paycode Distributions                         | POST   | `/v1/timekeeping/setup/pay_code_distributions/multi_update`
Timekeeping               | Paycode Distributions                   | Create or Update Paycode Distributions               | POST   | `/v1/timekeeping/setup/pay_code_distributions/apply_upsert`
Timekeeping               | Paycode Distributions                   | Delete Paycode Distribution by ID                    | DELETE | `/v1/timekeeping/setup/pay_code_distributions/{id}`
Timekeeping               | Paycode Distributions                   | Delete Paycode Distributions                         | POST   | `/v1/timekeeping/setup/pay_code_distributions/multi_delete`

## Dimensions R6 Update 3 {#R6U3}

The following operations were added to the API in Dimensions R6 Update 3:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Forecasting               | Labor Standards                         | Update Labor Standard                             | POST   | `/v1/forecasting/labor_standards/apply_update`
Platform > KPI Framework  | Target Thresholds                       | Retrieve Target Threshold by ID                   | GET    | `/v1/platform/target_thresholds/{id}`
Platform > KPI Framework  | Target Thresholds                       | Retrieve Target Thresholds                        | POST   | `/v1/platform/target_thresholds/multi_read`
Platform > KPI Framework  | Target Thresholds                       | Retrieve Target Threshold Short Names             | GET    | `/v1/platform/target_thresholds/short_names`
Platform > KPI Framework  | Target Thresholds                       | Export Target Threshold Data                      | GET    | `/v1/platform/target_thresholds/export`
Platform > KPI Framework  | Target Thresholds                       | Create or Update Target Thresholds                | POST   | `/v1/platform/target_thresholds/multi_upsert`
Platform > KPI Framework  | Target Thresholds                       | Update a Target Threshold by ID                   | POST   | `/v1/platform/target_thresholds/{id}`
Platform > KPI Framework  | Target Threshold Evaluation Period      | Retrieve Target Threshold Evaluation Period       | GET    | `/v1/platform/target_thresholds/eval_period`
Platform > KPI Framework  | Target Threshold Indicator Texts        | Retrieve All Target Threshold Indicator Texts     | GET    | `/v1/platform/target_thresholds/indicator_texts`
Platform > KPI Framework  | Target Threshold Operators              | Retrieve All Target Threshold Operators           | GET    | `/v1/platform/target_thresholds/operators`
Platform > Reporting      | Report Data Objects                  | Generate Report Data Object Batched Requests by Name | POST   | `/v1/platform/report_dataobjects/{name}/data/generate_request_batches`
Timekeeping               | Work Rules                              | Retrieve All Work Rules                           | GET    | `/v1/timekeeping/setup/full_work_rules`
Timekeeping               | Work Rules                              | Retrieve Work Rule by ID                          | GET    | `/v1/timekeeping/setup/full_work_rules/{id}`
Timekeeping               | Work Rules                              | Retrieve Work Rules                               | POST   | `/v1/timekeeping/setup/full_work_rules/multi_read`
Timekeeping               | Work Rules                              | Create Work Rule                                  | POST   | `/v1/timekeeping/setup/full_work_rules`
Timekeeping               | Work Rules                              | Create Work Rules                                 | POST   | `/v1/timekeeping/setup/full_work_rules/multi_create`
Timekeeping               | Work Rules                              | Update Work Rule by ID                            | PUT    | `/v1/timekeeping/setup/full_work_rules/{id}`
Timekeeping               | Work Rules                              | Update Work Rules                                 | POST   | `/v1/timekeeping/setup/full_work_rules/multi_update`
Timekeeping               | Work Rules                              | Delete Work Rule by ID                            | DELETE | `/v1/timekeeping/setup/full_work_rules/{id}`
Timekeeping               | Work Rules                              | Delete Work Rules                                 | POST   | `/v1/timekeeping/setup/full_work_rules/multi_delete`
Work                      | Activity Resources                      | Retrieve All Eligible Default Activities          | GET    | `/v1/work/activities/setup/eligible_default_activities`
Work                      | Activity Efficiencies                   | Retrieve Activity Efficiencies                    | POST   | `/v1/work/activity_efficiencies/multi_read`

## Dimensions R6 Update 2 {#R6U2}

The following operations were added to the API in Dimensions R6 Update 2:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Platform                  | Menu Items                              | Retrieve All Menu Items                           | GET    | `/v1/platform/user_interface/links`

## Dimensions R6 Update 1 {#R6U1}

The following operations were added to the API in Dimensions R6 Update 1:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Common Resources          | Reviewer Lists                          | Retrieve Reviewer List by Criteria                | GET    | `/v1/commons/reviewer_lists`
Common Resources          | Reviewer Lists                          | Retrieve Reviewer List by ID                      | GET    | `/v1/commons/reviewer_lists/{id}`
Common Resources          | Reviewer Lists                          | Retrieve Reviewers for Reviewer Lists             | GET    | `/v1/commons/reviewer_lists/reviewers`
Common Resources          | Reviewer Lists                          | Create Reviewer List                              | POST   | `/v1/commons/reviewer_lists`
Common Resources          | Reviewer Lists                          | Create Reviewer Lists                             | POST   | `/v1/commons/reviewer_lists/multi_create`
Common Resources          | Reviewer Lists                          | Update Reviewer List by ID                        | PUT    | `/v1/commons/reviewer_lists/{id}`
Common Resources          | Reviewer Lists                          | Update Reviewer Lists                             | POST   | `/v1/commons/reviewer_lists/multi_update`
Common Resources          | Reviewer Lists                          | Delete Reviewer List by ID                        | DELETE | `/v1/commons/reviewer_lists/{id}`
Common Resources          | Reviewer Lists                          | Delete Reviewer Lists                             | POST   | `/v1/commons/reviewer_lists/multi_delete`
Common Resources          | Reviewer Purposes                       | Retrieve All Reviewer Purposes or by Name         | GET    | `/v1/commons/reviewer_purpose`
Common Resources          | Reviewer Purposes                       | Retrieve Reviewer Purpose by ID                   | GET    | `/v1/commons/reviewer_purpose/{id}`
Common Resources          | Reviewer Purposes                       | Create Reviewer Purpose                           | POST   | `/v1/commons/reviewer_purpose`
Common Resources          | Reviewer Purposes                       | Update Reviewer Purpose by ID                     | PUT    | `/v1/commons/reviewer_purpose/{id}`
Common Resources          | Reviewer Purposes                       | Delete Reviewer Purpose by ID                     | DELETE | `/v1/commons/reviewer_purpose/{id}`
Work                      | Activity Resources                      | Retrieve All Event Types                          | GET    | `/v1/work/activities/setup/event_types`
Work                      | Activity Shifts                         | Retrieve Activity Shifts                          | POST   | `/v1/work/activity_shifts/multi_read`
Work                      | Activity Profile Resources              | Retrieve Variance Check Types                     | GET    | `/v1/work/activity_profiles/setup/variance_check_types`

## Dimensions R6 {#R6}

The following operations were added to the API in Dimensions R6:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Common Resources          | Custom Tiles                            | Create Custom Tile                                | POST   | `/v1/commons/custom_tiles`
Common Resources          | Employee Groups                         | Retrieve Employee Groups                          | POST   | `/v1/commons/employee_groups/multi_read`
Common Resources          | Average Pay Rate Sets                   | Retrieve All Average Pay Rate Sets                | GET    | `/v1/commons/average_pay_rate_sets`
Common Resources          | Average Pay Rate Sets                   | Retrieve Average Pay Rate Set - One Location      | POST   | `/v1/commons/average_pay_rate_sets/apply_read`
Common Resources          | Average Pay Rate Sets                   | Create Average Pay Rate Set                       | POST   | `/v1/commons/average_pay_rate_sets`
Common Resources          | Average Pay Rate Sets                   | Create Average Pay Rate Sets                      | POST   | `/v1/commons/average_pay_rate_sets/multi_create`
Common Resources          | Average Pay Rate Sets                   | Update Average Pay Rate Set by ID                 | PUT    | `/v1/commons/average_pay_rate_sets/{id}`
Common Resources          | Average Pay Rate Sets                   | Update Average Pay Rate Sets                      | POST   | `/v1/commons/average_pay_rate_sets/multi_update`
Common Resources          | Average Pay Rate Sets                   | Delete Average Pay Rate Set by ID                 | DELETE | `/v1/commons/average_pay_rate_sets/{id}`
Common Resources          | Average Pay Rate Sets                   | Delete Average Pay Rate Sets                      | POST   | `/v1/commons/average_pay_rate_sets/multi_delete`
Employee Self-Service     | Employee Cover Requests                 | Retrieve Shift Cover Request by ID                | GET    | `/v1/scheduling/employee_cover_requests/{id}`
Employee Self-Service     | Employee Cover Requests                 | Retrieve Shift Cover Requests                     | POST   | `/v1/scheduling/employee_cover_requests/multi_read`
Employee Self-Service     | Employee Cover Requests                 | Create Shift Cover Request                        | POST   | `/v1/scheduling/employee_cover_requests`
Employee Self-Service     | Employee Cover Requests                 | Update Shift Cover Request                        | POST   | `/v1/scheduling/employee_cover_requests/apply_update`
Employee Self-Service     | Employee Cover Requests                 | Retrieve Candidate Employees                      | GET    | `/v1/scheduling/employee_cover_requests/candidate_employees`
Employee Self-Service     | Employee Cover Requests                 | Retrieve Shift Cover Request Subtypes             | GET    | `/v1/scheduling/employee_cover_requests/request_subtypes`
Employee Self-Service     | Employee Cover Requests                 | Retrieve Offerable Shifts                         | GET    | `/v1/scheduling/employee_cover_requests/shifts`
Employee Self-Service     | Employee Cover Requests                 | Retrieve Submission Periods                       | GET    | `/v1/scheduling/employee_cover_requests/submission_periods`
Employee Self-Service     | Manager Cover Requests                  | Retrieve Shift Cover Request by ID as Manager     | GET    | `/v1/scheduling/cover_requests/{id}`
Employee Self-Service     | Manager Cover Requests                  | Retrieve Rule Violations for Shift Cover Request  | GET    | `/v1/scheduling/cover_requests/{id}/rule_violations`
Employee Self-Service     | Manager Cover Requests                  | Retrieve Shift Cover Requests as Manager          | POST   | `/v1/scheduling/cover_requests/multi_read`
Employee Self-Service     | Manager Cover Requests                  | Update Shift Cover Request as Manager             | POST   | `/v1/scheduling/cover_requests/apply_update`
Forecasting               | Volume Analyzer                         | Retrieve Anomaly Scores                           | GET    | `/v1/forecasting/volume_analyzer/anomaly_scores`
Forecasting               | Volume Analyzer                         | Retrieve History Years                            | GET    | `/v1/forecasting/volume_analyzer/history_years`
Forecasting               | Volume Analyzer                         | Retrieve Analysis Data Sample Sizes               | GET    | `/v1/forecasting/volume_analyzer/analysis_data_sample_sizes`
Forecasting               | Volume Analyzer                         | Execute Volume Analyzer                           | POST   | `/v1/forecasting/volume_analyzer/apply_create`
Forecasting               | Adjustment Drivers                      | Retrieve Adjustment Driver Values                 | POST   | `/v1/forecasting/adjustment_drivers/multi_read`
Forecasting               | Adjustment Drivers                      | Update Adjustment Driver Values                   | POST   | `/v1/forecasting/adjustment_drivers/apply_upsert`
Forecasting               | Adjustment Drivers                      | Update Values for Multiple Adjustment Drivers     | POST   | `/v1/forecasting/adjustment_drivers/multi_upsert`
Healthcare Analytics      | HCA Payroll Job Maps                    | Retrieve Payroll Job Maps                         | GET    | `/v1/hca/payroll/job_maps`
Human Capital Management  | People Profiles                         | Retrieve All People Profiles                      | GET    | `/v1/commons/profiles/people_profiles`
Human Capital Management  | People Profiles                         | Retrieve People Profile by ID                     | GET    | `/v1/commons/profiles/people_profiles/{id}`
Human Capital Management  | People Profiles                         | Retrieve People Profiles                          | POST   | `/v1/commons/profiles/people_profiles/multi_read`
Human Capital Management  | Profile Field Maps                      | Retrieve All Profile Field Maps                   | GET    | `/v1/commons/profiles/profile_field_mappings`
Human Capital Management  | Profile Field Maps                      | Retrieve Profile Field Maps                       | POST   | `/v1/commons/profiles/profile_field_mappings/multi_read`
Human Capital Management  | Profile Field Maps                      | Create or Update Profile Field Maps               | POST   | `/v1/commons/profiles/profile_field_mappings/multi_upsert`
Human Capital Management  | Profile Templates                       | Retrieve All Profile Templates                    | GET    | `/v1/commons/profiles/profile_templates`
Human Capital Management  | Profile Templates                       | Retrieve Profile Template by ID                   | GET    | `/v1/commons/profiles/profile_templates/{id}`
Human Capital Management  | Profile Templates                       | Retrieve Profile Templates                        | POST   | `/v1/commons/profiles/profile_templates/multi_read`
People                    | Person Assignments > Direct Assignments | Retrieve All People Direct Assignment Profiles    | GET    | `/v1/commons/profiles/people_direct_assignments`
People                    | Person Assignments > Person Common ID   | Retrieve Persons without an Assigned AOID         | POST   | `/v1/commons/persons/external_id/apply_read`
Platform > Integrations   | Integration Executions                  | Submit Integration Execution Custom Errors        | POST   | `/v1/platform/integration_executions/{id}/custom_errors`
Scheduling                | Employment Term Schedule Patterns       | Retrieve Employment Term Schedule Pattern by ID   | GET    | `/v1/scheduling/employment_term_schedule_patterns/{id}`
Scheduling                | Employment Term Schedule Patterns       | Retrieve Employment Term Schedule Patterns        | POST   | `/v1/scheduling/employment_term_schedule_patterns/multi_read`
Scheduling                | Employment Term Schedule Patterns       | Create Employment Term Schedule Pattern           | POST   | `/v1/scheduling/employment_term_schedule_patterns/apply_create`
Scheduling                | Employment Term Schedule Patterns       | Update or Remove Employment Term Schedule Patterns | POST  | `/v1/scheduling/employment_term_schedule_patterns/apply_update`
Scheduling                | Employment Term Schedule Patterns       | Delete Employment Term Schedule Pattern by ID     | DELETE | `/v1/scheduling/employment_term_schedule_patterns/{id}`
Scheduling                | Employment Term Schedule Patterns       | Retrieve Employment Term Schedule Pattern Configuration | GET | `/v1/scheduling/employment_term_schedule_patterns/builder`
Scheduling                | Schedule Group Patterns                 | Retrieve Schedule Group Pattern by ID             | GET    | `/v1/scheduling/schedule_group_patterns/{id}`
Scheduling                | Schedule Group Patterns                 | Retrieve Schedule Group Patterns                  | POST   | `/v1/scheduling/schedule_group_patterns/multi_read`
Scheduling                | Schedule Group Patterns                 | Create Schedule Group Pattern                     | POST   | `/v1/scheduling/schedule_group_patterns/apply_create`
Scheduling                | Schedule Group Patterns                 | Update or Remove Schedule Group Patterns          | POST   | `/v1/scheduling/schedule_group_patterns/apply_update`
Scheduling                | Schedule Group Patterns                 | Delete Schedule Group Pattern by ID               | DELETE | `/v1/scheduling/schedule_group_patterns/{id}`
Scheduling                | Schedule Group Patterns                 | Retrieve Schedule Group Pattern Configuration     | GET    | `/v1/scheduling/schedule_group_patterns/builder`
Scheduling                | Skills and Certifications Profiles      | Retrieve All Skills and Certifications Profiles or by Name | GET | `/v1/scheduling/skill_certification_profiles`
Scheduling                | Skills and Certifications Profiles      | Retrieve Skills and Certifications Profile by ID  | GET    | `/v1/scheduling/skill_certification_profiles/{id}`
Scheduling                | Skills and Certifications Profiles      | Retrieve Skills and Certifications Profiles       | POST   | `/v1/scheduling/skill_certification_profiles/multi_read`
Scheduling                | Skills and Certifications Profiles      | Create Skills and Certifications Profile          | POST   | `/v1/scheduling/skill_certification_profiles`
Scheduling                | Skills and Certifications Profiles      | Create Skills and Certifications Profiles         | POST   | `/v1/scheduling/skill_certification_profiles/multi_create`
Scheduling                | Skills and Certifications Profiles      | Update Skills and Certifications Profile by ID    | PUT    | `/v1/scheduling/skill_certification_profiles/{id}`
Scheduling                | Skills and Certifications Profiles      | Update Skills and Certifications Profiles         | POST   | `/v1/scheduling/skill_certification_profiles/multi_update`
Scheduling                | Skills and Certifications Profiles      | Delete Skills and Certifications Profile by ID    | DELETE | `/v1/scheduling/skill_certification_profiles/{id}`
Scheduling                | Skills and Certifications Profiles      | Delete Skills and Certifications Profiles         | POST   | `/v1/scheduling/skill_certification_profiles/multi_delete`
Timekeeping               | Employment Terms                        | Retrieve Employment Terms                         | POST   | `/v1/timekeeping/setup/employment_terms/multi_read`
Timekeeping               | Timekeeping Setup Overtime Rules        | Retrieve Overtime Rules                           | POST   | `/v1/timekeeping/setup/overtime_rules/multi_read`
Timekeeping               | Percentage Allocation Rules             | Retrieve Percentage Allocation Rules              | POST   | `/v1/timekeeping/setup/percentage_allocation_rules/multi_read`
Work                      | Activities                              | Retrieve Activity by Name                         | GET    | `/v1/work/activities`
Work                      | Activities                              | Retrieve Activity by ID                           | GET    | `/v1/work/activities/{id}`
Work                      | Activities                              | Retrieve Activities                               | POST   | `/v1/work/activities/multi_read`
Work                      | Activities                              | Create Activity                                   | POST   | `/v1/work/activities`
Work                      | Activities                              | Create Activities                                 | POST   | `/v1/work/activities/multi_create`
Work                      | Activities                              | Create or Update Activities                       | POST   | `/v1/work/activities/multi_upsert`
Work                      | Activities                              | Update Activity by ID                             | PUT    | `/v1/work/activities/{id}`
Work                      | Activities                              | Update Activities                                 | POST   | `/v1/work/activities/multi_update`
Work                      | Activities                              | Delete Activity by ID                             | DELETE | `/v1/work/activities/{id}`
Work                      | Activities                              | Delete Activities                                 | POST   | `/v1/work/activities/multi_delete`
Work                      | Activity Resources                      | Retrieve All Data Access Types                    | GET    | `/v1/work/activities/setup/data_access_types`
Work                      | Activity Resources                      | Retrieve All Activity Complete Statuses           | GET    | `/v1/work/activities/setup/complete_statuses`
Work                      | Activity Resources                      | Retrieve All Quantity Allocation Types            | GET    | `/v1/work/activities/setup/quantity_allocation_types`
Work                      | Activity Resources                      | Retrieve All Activity Process Types               | GET    | `/v1/work/activities/setup/process_types`
Work                      | Activity Resources                      | Retrieve All Activity Types                       | GET    | `/v1/work/activities/setup/activity_types`
Work                      | Activity Resources                      | Retrieve All Activity Held History                | GET    | `/v1/work/activities/setup/held_histories`
Work                      | Activity Resources                      | Retrieve All Hours Allocation Types               | GET    | `/v1/work/activities/setup/hours_allocation_types`
Work                      | Activity Resources                      | Retrieve All Activity Priority Types              | GET    | `/v1/work/activities/setup/priority_types`
Work                      | Activity Resources                      | Retrieve All Sequence Validation Types            | GET    | `/v1/work/activities/setup/sequence_validation_types`
Work                      | Activity Profiles                       | Retrieve All Activity Profiles or by Name         | GET    | `/v1/work/activity_profiles`
Work                      | Activity Profiles                       | Retrieve Activity Profile by ID                   | GET    | `/v1/work/activity_profiles/{id}`
Work                      | Activity Profiles                       | Retrieve Activity Profiles                        | POST   | `/v1/work/activity_profiles/multi_read`
Work                      | Activity Profiles                       | Create Activity Profile                           | POST   | `/v1/work/activity_profiles`
Work                      | Activity Profiles                       | Create Activity Profiles                          | POST   | `/v1/work/activity_profiles/multi_create`
Work                      | Activity Profiles                       | Update Activity Profile by ID                     | PUT    | `/v1/work/activity_profiles/{id}`
Work                      | Activity Profiles                       | Update Activity Profiles                          | POST   | `/v1/work/activity_profiles/multi_update`
Work                      | Activity Profiles                       | Delete Activity Profile by ID                     | DELETE | `/v1/work/activity_profiles/{id}`
Work                      | Activity Profiles                       | Delete Activity Profiles                          | POST   | `/v1/work/activity_profiles/multi_delete`
Work                      | Activity Shifts                         | Create or Update Activity Shifts                  | POST   | `/v1/work/activity_shifts/multi_upsert`
Work                      | Activity Net Changes                    | Retrieve Net Changes for Activity Shift           | POST   | `/v1/work/activity_shifts/net_changes/multi_read`
Work                      | Activity Customers                      | Retrieve All Customers or by Name                 | GET    | `/v1/work/customers`
Work                      | Activity Customers                      | Retrieve Customer by ID                           | GET    | `/v1/work/customers/{id}`
Work                      | Activity Customers                      | Retrieve Customers                                | POST   | `/v1/work/customers/multi_read`
Work                      | Activity Customers                      | Create Customer                                   | POST   | `/v1/work/customers`
Work                      | Activity Customers                      | Create Customers                                  | POST   | `/v1/work/customers/multi_create`
Work                      | Activity Customers                      | Update Customer by ID                             | PUT    | `/v1/work/customers/{id}`
Work                      | Activity Customers                      | Update Customers                                  | POST   | `/v1/work/customers/multi_update`
Work                      | Activity Customers                      | Delete Customer by ID                             | DELETE | `/v1/work/customers/{id}`
Work                      | Activity Customers                      | Delete Customers                                  | POST   | `/v1/work/customers/multi_delete`
Work                      | Field Definitions                       | Retrieve All Field Definitions or by Name         | GET    | `/v1/work/field_definitions`
Work                      | Field Definitions                       | Retrieve Field Definition by ID                   | GET    | `/v1/work/field_definitions/{id}`
Work                      | Field Definitions                       | Retrieve Field Definitions                        | POST   | `/v1/work/field_definitions/multi_read`
Work                      | Field Definitions                       | Create Field Definition                           | POST   | `/v1/work/field_definitions`
Work                      | Field Definitions                       | Create Field Definitions                          | POST   | `/v1/work/field_definitions/multi_create`
Work                      | Field Definitions                       | Update Field Definition by ID                     | PUT    | `/v1/work/field_definitions/{id}`
Work                      | Field Definitions                       | Update Field Definitions                          | POST   | `/v1/work/field_definitions/multi_update`
Work                      | Field Definitions                       | Delete Field Definition by ID                     | DELETE | `/v1/work/field_definitions/{id}`
Work                      | Field Definitions                       | Delete Field Definitions                          | POST   | `/v1/work/field_definitions/multi_delete`
Work                      | Form Profiles                           | Retrieve All Form Profiles or by Name             | GET    | `/v1/work/form_profiles`
Work                      | Form Profiles                           | Retrieve Form Profile by ID                       | GET    | `/v1/work/form_profiles/{id}`
Work                      | Form Profiles                           | Retrieve Form Profiles                            | POST   | `/v1/work/form_profiles/multi_read`
Work                      | Form Profiles                           | Create Form Profile                               | POST   | `/v1/work/form_profiles`
Work                      | Form Profiles                           | Create Form Profiles                              | POST   | `/v1/work/form_profiles/multi_create`
Work                      | Form Profiles                           | Update Form Profile by ID                         | PUT    | `/v1/work/form_profiles/{id}`
Work                      | Form Profiles                           | Update Form Profiles                              | POST   | `/v1/work/form_profiles/multi_update`
Work                      | Form Profiles                           | Delete Form Profile by ID                         | DELETE | `/v1/work/form_profiles/{id}`
Work                      | Form Profiles                           | Delete Form Profiles                              | POST   | `/v1/work/form_profiles/multi_delete`
Work                      | Activity Forms                          | Retrieve All Activity Forms or by Name            | GET    | `/v1/work/forms`
Work                      | Activity Forms                          | Retrieve Activity Form by ID                      | GET    | `/v1/work/forms/{id}`
Work                      | Activity Forms                          | Retrieve Activity Forms                           | POST   | `/v1/work/forms/multi_read`
Work                      | Activity Forms                          | Create Activity Form                              | POST   | `/v1/work/forms`
Work                      | Activity Forms                          | Create Activity Forms                             | POST   | `/v1/work/forms/multi_create`
Work                      | Activity Forms                          | Update Activity Form by ID                        | PUT    | `/v1/work/forms/{id}`
Work                      | Activity Forms                          | Update Activity Forms                             | POST   | `/v1/work/forms/multi_update`
Work                      | Activity Forms                          | Delete Activity Form by ID                        | DELETE | `/v1/work/forms/{id}`
Work                      | Activity Forms                          | Delete Activity Forms                             | POST   | `/v1/work/forms/multi_delete`
Work                      | Activity Form Resources                 | Retrieve All Form Types                           | GET    | `/v1/work/forms/setup/form_types`
Work                      | Activity Form Resources                 | Retrieve All Entry Types                          | GET    | `/v1/work/forms/setup/entry_types`
Work                      | Activity Form Resources                 | Retrieve All Validation Types                     | GET    | `/v1/work/forms/setup/validation_types`
Work                      | Activity Form Resources                 | Retrieve All Input Source Types                   | GET    | `/v1/work/forms/setup/input_source_types`
Work                      | Activity Form Resources                 | Retrieve All Control Types or Only Applicable Type | GET    | `/v1/work/forms/setup/control_types`
Work                      | Activity Form Resources                 | Retrieve Offline Forms                            | GET    | `/v1/work/forms/setup/offline_forms`
Work                      | Paycode Actions                         | Retrieve All Paycode Actions or by Name           | GET    | `/v1/work/pay_code_actions`
Work                      | Paycode Actions                         | Retrieve Paycode Action by ID                     | GET    | `/v1/work/pay_code_actions/{id}`
Work                      | Paycode Actions                         | Retrieve Paycode Actions                          | POST   | `/v1/work/pay_code_actions/multi_read`
Work                      | Paycode Actions                         | Create Paycode Action                             | POST   | `/v1/work/pay_code_actions`
Work                      | Paycode Actions                         | Create Paycode Actions                            | POST   | `/v1/work/pay_code_actions/multi_create`
Work                      | Paycode Actions                         | Update Paycode Action by ID                       | PUT    | `/v1/work/pay_code_actions/{id}`
Work                      | Paycode Actions                         | Update Paycode Actions                            | POST   | `/v1/work/pay_code_actions/multi_update`
Work                      | Paycode Actions                         | Delete Paycode Action by ID                       | DELETE | `/v1/work/pay_code_actions/{id}`
Work                      | Paycode Actions                         | Delete Paycode Actions                            | POST   | `/v1/work/pay_code_actions/multi_delete`
Work                      | Activity Queries                        | Retrieve All Activity Queries or by Name          | GET    | `/v1/work/queries`
Work                      | Activity Queries                        | Retrieve Activity Query by ID                     | GET    | `/v1/work/queries/{id}`
Work                      | Activity Queries                        | Retrieve Activity Queries                         | POST   | `/v1/work/queries/multi_read`
Work                      | Activity Queries                        | Create Activity Query                             | POST   | `/v1/work/queries`
Work                      | Activity Queries                        | Create Activity Queries                           | POST   | `/v1/work/queries/multi_create`
Work                      | Activity Queries                        | Update Activity Query by ID                       | PUT    | `/v1/work/queries/{id}`
Work                      | Activity Queries                        | Update Activity Queries                           | POST   | `/v1/work/queries/multi_update`
Work                      | Activity Queries                        | Delete Activity Query by ID                       | DELETE | `/v1/work/queries/{id}`
Work                      | Activity Queries                        | Delete Activity Queries                           | POST   | `/v1/work/queries/multi_delete`
Work                      | Activity Query Resources                | Retrieve All Activity Query Date Range Date Types | GET    | `/v1/work/queries/setup/date_types`
Work                      | Activity Query Profiles                 | Retrieve All Activity Query Profiles or by Name   | GET    | `/v1/work/query_profiles`
Work                      | Activity Query Profiles                 | Retrieve Activity Query Profile by ID             | GET    | `/v1/work/query_profiles/{id}`
Work                      | Activity Query Profiles                 | Retrieve Activity Query Profiles                  | POST   | `/v1/work/query_profiles/multi_read`
Work                      | Activity Query Profiles                 | Create Activity Query Profile                     | POST   | `/v1/work/query_profiles`
Work                      | Activity Query Profiles                 | Create Activity Query Profiles                    | POST   | `/v1/work/query_profiles/multi_create`
Work                      | Activity Query Profiles                 | Update Activity Query Profile by ID               | PUT    | `/v1/work/query_profiles/{id}`
Work                      | Activity Query Profiles                 | Update Activity Query Profiles                    | POST   | `/v1/work/query_profiles/multi_update`
Work                      | Activity Query Profiles                 | Delete Activity Query Profile by ID               | DELETE | `/v1/work/query_profiles/{id}`
Work                      | Activity Query Profiles                 | Delete Activity Query Profiles                    | POST   | `/v1/work/query_profiles/multi_delete`
Work                      | Result Codes                            | Retrieve All Result Codes                         | GET    | `/v1/work/result_codes`
Work                      | Result Codes                            | Retrieve Result Code by ID                        | GET    | `/v1/work/result_codes/{id}`
Work                      | Result Codes                            | Retrieve Result Codes                             | POST   | `/v1/work/result_codes/multi_read`
Work                      | Result Codes                            | Create Result Code                                | POST   | `/v1/work/result_codes`
Work                      | Result Codes                            | Create Result Codes                               | POST   | `/v1/work/result_codes/multi_create`
Work                      | Result Codes                            | Update Result Code by ID                          | PUT    | `/v1/work/result_codes/{id}`
Work                      | Result Codes                            | Update Result Codes                               | POST   | `/v1/work/result_codes/multi_update`
Work                      | Result Codes                            | Create or Update Result Codes                     | POST   | `/v1/work/result_codes/multi_upsert`
Work                      | Result Codes                            | Delete Result Code by ID                          | DELETE | `/v1/work/result_codes/{id}`
Work                      | Result Codes                            | Delete Result Codes                               | POST   | `/v1/work/result_codes/multi_delete`
Work                      | Result Code Profiles                    | Retrieve All Result Code Profiles or by Name      | GET    | `/v1/work/result_code_profiles`
Work                      | Result Code Profiles                    | Retrieve Result Code Profile by ID                | GET    | `/v1/work/result_code_profiles/{id}`
Work                      | Result Code Profiles                    | Retrieve Result Code Profiles                     | POST   | `/v1/work/result_code_profiles/multi_read`
Work                      | Result Code Profiles                    | Create Result Code Profile                        | POST   | `/v1/work/result_code_profiles`
Work                      | Result Code Profiles                    | Create Result Code Profiles                       | POST   | `/v1/work/result_code_profiles/multi_create`
Work                      | Result Code Profiles                    | Update Result Code Profile by ID                  | PUT    | `/v1/work/result_code_profiles/{id}`
Work                      | Result Code Profiles                    | Update Result Code Profiles                       | POST   | `/v1/work/result_code_profiles/multi_update`
Work                      | Result Code Profiles                    | Delete Result Code Profile by ID                  | DELETE | `/v1/work/result_code_profiles/{id}`
Work                      | Result Code Profiles                    | Delete Result Code Profiles                       | POST   | `/v1/work/result_code_profiles/multi_delete`
Work                      | Results Templates                       | Retrieve All Results Templates or by Name         | GET    | `/v1/work/results_templates`
Work                      | Results Templates                       | Retrieve Results Template by ID                   | GET    | `/v1/work/results_templates/{id}`
Work                      | Results Templates                       | Retrieve Results Templates                        | POST   | `/v1/work/results_templates/multi_read`
Work                      | Results Templates                       | Create Results Template                           | POST   | `/v1/work/results_templates`
Work                      | Results Templates                       | Create Results Templates                          | POST   | `/v1/work/results_templates/multi_create`
Work                      | Results Templates                       | Update Results Template by ID                     | PUT    | `/v1/work/results_templates/{id}`
Work                      | Results Templates                       | Update Results Templates                          | POST   | `/v1/work/results_templates/multi_update`
Work                      | Results Templates                       | Delete Results Template by ID                     | DELETE | `/v1/work/results_templates/{id}`
Work                      | Results Templates                       | Delete Results Templates                          | POST   | `/v1/work/results_templates/multi_delete`
Work                      | Results Template Resources              | Retrieve All Step Types                           | GET    | `/v1/work/results_templates/setup/step_types`
Work                      | Activity Settings                       | Retrieve All Activity Settings                    | GET    | `/v1/work/settings`
Work                      | Activity Settings                       | Retrieve Activity Setting by ID                   | GET    | `/v1/work/settings/{id}`
Work                      | Activity Settings                       | Retrieve Activity Settings                        | POST   | `/v1/work/settings/multi_read`
Work                      | Activity Settings                       | Update Activity Setting by ID                     | PUT    | `/v1/work/settings/{id}`
Work                      | Activity Settings                       | Update Activity Settings                          | POST   | `/v1/work/settings/multi_update`
Work                      | Units of Measure                        | Retrieve All Units of Measure or by Name          | GET    | `/v1/work/units_of_measure`
Work                      | Units of Measure                        | Retrieve Unit of Measure by ID                    | GET    | `/v1/work/units_of_measure/{id}`
Work                      | Units of Measure                        | Retrieve Units of Measure                         | POST   | `/v1/work/units_of_measure/multi_read`
Work                      | Units of Measure                        | Create Unit of Measure                            | POST   | `/v1/work/units_of_measure`
Work                      | Units of Measure                        | Create Units of Measure                           | POST   | `/v1/work/units_of_measure/multi_create`
Work                      | Units of Measure                        | Update Unit of Measure by ID                      | PUT    | `/v1/work/units_of_measure/{id}`
Work                      | Units of Measure                        | Update Units of Measure                           | POST   | `/v1/work/units_of_measure/multi_update`
Work                      | Units of Measure                        | Delete Unit of Measure by ID                      | DELETE | `/v1/work/units_of_measure/{id}`
Work                      | Units of Measure                        | Delete Units of Measure                           | POST   | `/v1/work/units_of_measure/multi_delete`

## Dimensions R5 Update 2 {#R5U2}

The following operations were added to the API in Dimensions R5 Update 2:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Timekeeping               | Timekeeping Setup Overtime Rules        | Retrieve All Overtime Rules                       | GET    | `/v1/timekeeping/setup/overtime_rules`
Timekeeping               | Timekeeping Setup Overtime Rules        | Retrieve Overtime Rule by ID                      | GET    | `/v1/timekeeping/setup/overtime_rules/{id}`
Timekeeping               | Timekeeping Setup Overtime Rules        | Retrieve Overtime Rules                           | POST   | `/v1/timekeeping/setup/overtime_rules/multi_read`
Timekeeping               | Timekeeping Setup Overtime Rules        | Create Overtime Rule                              | POST   | `/v1/timekeeping/setup/overtime_rules`
Timekeeping               | Timekeeping Setup Overtime Rules        | Create Overtime Rules                             | POST   | `/v1/timekeeping/setup/overtime_rules/multi_create`
Timekeeping               | Timekeeping Setup Overtime Rules        | Update Overtime Rule by ID                        | PUT    | `/v1/timekeeping/setup/overtime_rules/{id}`
Timekeeping               | Timekeeping Setup Overtime Rules        | Update Overtime Rules                             | POST   | `/v1/timekeeping/setup/overtime_rules/multi_update`
Timekeeping               | Timekeeping Setup Overtime Rules        | Delete Overtime Rule by ID                        | DELETE | `/v1/timekeeping/setup/overtime_rules/{id}`
Timekeeping               | Timekeeping Setup Overtime Rules        | Delete Overtime Rules                             | POST   | `/v1/timekeeping/setup/overtime_rules/multi_delete`

## Dimensions R5 Update 1 {#R5U1}

The following operations were added to the API in Dimensions R5 Update 1:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Common Resources          | Business Structures > Location Sets     | Create or Update Location Set                     | POST   | `/v1/commons/location_sets/apply_upsert`
Common Resources          | Timezones                               | Retrieve Timezone                                 | GET    | `/v1/commons/setup/timezones`
Common Resources          | Timezones                               | Retrieve Timezone by ID                           | GET    | `/v1/commons/setup/timezones/{id}`
Leave                     | Leave Profiles                          | Retrieve All Leave Profiles                       | GET    | `/v1/leave/leave_profiles`
Leave                     | Leave Profiles                          | Retrieve Leave Profile by ID                      | GET    | `/v1/leave/leave_profiles/{id}`
Leave                     | Leave Categories                        | Retrieve All Leave Categories or by Name          | GET    | `/v1/leave/setup/leave_categories`
Leave                     | Leave Categories                        | Retrieve Leave Category by ID                     | GET    | `/v1/leave/setup/leave_categories/{id}`
Leave                     | Leave Categories                        | Retrieve Leave Categories                         | POST   | `/v1/leave/setup/leave_categories/multi_read`
Leave                     | Leave Reasons                           | Retrieve All Leave Reasons or by Name             | GET    | `/v1/leave/setup/leave_reasons`
Leave                     | Leave Reasons                           | Retrieve Leave Reason by ID                       | GET    | `/v1/leave/setup/leave_reasons/{id}`
Leave                     | Leave Reasons                           | Retrieve Leave Reasons                            | POST   | `/v1/leave/setup/leave_reasons/multi_read`
Timekeeping               | Timekeeping Setup Fixed Rules           | Retrieve All Fixed Rules                          | GET    | `/v1/timekeeping/setup/fixed_rules`
Timekeeping               | Timekeeping Setup Fixed Rules           | Retrieve Fixed Rules                              | POST   | `/v1/timekeeping/setup/fixed_rules/multi_read`
Timekeeping               | Timekeeping Setup Fixed Rules           | Create Fixed Rules                                | POST   | `/v1/timekeeping/setup/fixed_rules/multi_create`
Timekeeping               | Timekeeping Setup Fixed Rules           | Create or Update Fixed Rules                      | POST   | `/v1/timekeeping/setup/fixed_rules/multi_upsert`
Timekeeping               | Timekeeping Setup Fixed Rules           | Update Fixed Rule by ID                           | PUT    | `/v1/timekeeping/setup/fixed_rules/{id}`
Timekeeping               | Timekeeping Setup Fixed Rules           | Update Fixed Rules                                | POST   | `/v1/timekeeping/setup/fixed_rules/multi_update`
Timekeeping               | Timekeeping Setup Fixed Rules           | Delete Fixed Rules                                | POST   | `/v1/timekeeping/setup/fixed_rules/multi_delete`

## Dimensions R5 {#R5}

The following operations were added to the API in Dimensions R5:

Domain                    | Resource                                | Operation                                         | Method | URL endpoint
----------------          | ----------------                        | ----------------                                  | ------ | ----------------
Common Resources          | Business Structures > Jobs              | Retrieve Job Mappings by Persistent IDs           | POST   | `/v1/commons/jobs/persistent_ids/multi_read`
Common Resources          | Business Structures > Location Types    | Retrieve Location Types by Persistent IDs         | POST   | `/v1/commons/location_types/persistent_ids/multi_read`
Common Resources          | Business Structures > Locations         | Retrieve Location Mappings by Persistent IDs      | POST   | `/v1/commons/locations/persistent_ids/multi_read`
Common Resources          | Currency > Currency Definitions         | Retrieve All Currency Definitions                 | GET    | `/v1/commons/currency/definitions`
Common Resources          | Currency > Currency Definitions         | Retrieve Currency Definition by ID                | GET    | `/v1/commons/currency/definitions/{id}`
Common Resources          | Currency > Currency Policies            | Retrieve Base Currency Policy                     | GET    | `/v1/commons/currency/policies/base_currency`
Common Resources          | Currency > Currency Policies            | Retrieve All Currency Policies                    | GET    | `/v1/commons/currency/policies`
Common Resources          | Currency > Currency Policies            | Retrieve Currency Policy by ID                    | GET    | `/v1/commons/currency/policies/{id}`
Common Resources          | Currency > Currency Policies            | Retrieve Currency Policies                        | POST   | `/v1/commons/currency/policies/multi_read`
Common Resources          | Currency > Currency Policies            | Create Currency Policy                            | POST   | `/v1/commons/currency/policies`
Common Resources          | Currency > Currency Policies            | Update Currency Policy                            | POST   | `/v1/commons/currency/policies/apply_update`
Common Resources          | Currency > Currency Policies            | Create or Update Currency Policies                | POST   | `/v1/commons/currency/policies/multi_upsert`
Common Resources          | Currency > Exchange Rates               | Retrieve Converted Amount                         | POST   | `/v1/commons/currency/conversions/apply_read`
Common Resources          | Domain Event Categories                 | Retrieve All Domain Event Categories              | GET    | `/v1/commons/event_categories`
Common Resources          | Domain Event Categories                 | Retrieve Domain Event Category by ID              | GET    | `/v1/commons/event_categories/{id}`
Common Resources          | Domain Event Categories                 | Retrieve Domain Event Categories                  | POST   | `/v1/commons/event_categories/multi_read`
Common Resources          | Domain Event Categories                 | Create Domain Event Category                      | POST   | `/v1/commons/event_categories`
Common Resources          | Domain Event Categories                 | Create or Update Domain Event Categories          | POST   | `/v1/commons/event_categories/multi_upsert`
Common Resources          | Domain Event Categories                 | Update Domain Event Category by ID                | PUT    | `/v1/commons/event_categories/{id}`
Common Resources          | Domain Event Categories                 | Delete Domain Event Category by ID                | DELETE | `/v1/commons/event_categories/{id}`
Common Resources          | Domain Event Navigations                | Retrieve All Domain Event Navigations             | GET    | `/v1/commons/event_navigations`
Common Resources          | Domain Event Navigations                | Retrieve Domain Event Notification by ID          | GET    | `/v1/commons/event_navigations/{id}`
Common Resources          | Domain Event Navigations                | Retrieve Domain Event Navigations                 | POST   | `/v1/commons/event_navigations/multi_read`
Common Resources          | Domain Event Navigations                | Create Domain Event Notification                  | POST   | `/v1/commons/event_navigations`
Common Resources          | Domain Event Navigations                | Create or Update Domain Event Navigations         | POST   | `/v1/commons/event_navigations/multi_upsert`
Common Resources          | Domain Event Navigations                | Update Domain Event Notification by ID            | PUT    | `/v1/commons/event_navigations/{id}`
Common Resources          | Domain Event Navigations                | Delete Domain Event Notification by ID            | DELETE | `/v1/commons/event_navigations/{id}`
Common Resources          | Dynamic Event Notification Mappings     | Retrieve All Dynamic Event Notification Mappings  | GET    | `/v1/commons/event_notifications`
Common Resources          | Dynamic Event Notification Mappings     | Retrieve Dynamic Event Notification Mapping by ID | GET    | `/v1/commons/event_notifications/{id}`
Common Resources          | Dynamic Event Notification Mappings     | Retrieve Dynamic Event Notification Mappings      | POST   | `/v1/commons/event_notifications/multi_read`
Common Resources          | Dynamic Event Notification Mappings     | Create a Dynamic Event Notification Mapping       | POST   | `/v1/commons/event_notifications`
Common Resources          | Dynamic Event Notification Mappings     | Create or Update Dynamic Event Notification Mappings | POST | `/v1/commons/event_notifications/multi_upsert`
Common Resources          | Dynamic Event Notification Mappings     | Update a Dynamic Event Notification Mapping by ID | PUT    | `/v1/commons/event_notifications/{id}`
Common Resources          | Dynamic Event Notification Mappings     | Delete Dynamic Event Notification Mapping by ID   | DELETE | `/v1/commons/event_notifications/{id}`
Common Resources          | Dynamic Event Notification Mappings     | Delete Dynamic Event Notification Mappings        | POST   | `/v1/commons/event_notifications/multi_delete`
Common Resources          | Dynamic Event Notification Mappings     | Send Event Notifications                          | POST   | `/v1/commons/event_notifications/notify`
Common Resources          | Domain Events                           | Retrieve All Domain Events                        | GET    | `/v1/commons/event_types`
Common Resources          | Domain Events                           | Retrieve Domain Event by ID                       | GET    | `/v1/commons/event_types/{id}`
Common Resources          | Domain Events                           | Retrieve Domain Events                            | POST   | `/v1/commons/event_types/multi_read`
Common Resources          | Domain Events                           | Create Domain Event                               | POST   | `/v1/commons/event_types`
Common Resources          | Domain Events                           | Create or Update Domain Events                    | POST   | `/v1/commons/event_types/multi_upsert`
Common Resources          | Domain Events                           | Update Domain Event by ID                         | PUT    | `/v1/commons/event_types/{id}`
Common Resources          | Domain Events                           | Delete Domain Event by ID                         | DELETE | `/v1/commons/event_types/{id}`
Common Resources          | Domain Events                           | Delete Domain Events                              | POST   | `/v1/commons/event_types/multi_delete`
Common Resources          | Fiscal Calendars                        | Create Fiscal Periods                             | POST   | `/v1/commons/fiscal_calendars/import`
Common Resources          | Fiscal Calendars                        | Delete Fiscal Periods                             | POST   | `/v1/commons/fiscal_calendars/multi_delete`
Common Resources          | Generic Notifications                   | Retrieve All Generic Notifications                | GET    | `/v1/commons/generic_notifications`
Common Resources          | Generic Notifications                   | Retrieve Generic Notification by ID               | GET    | `/v1/commons/generic_notifications/{id}`
Common Resources          | Generic Notifications                   | Retrieve Generic Notifications                    | POST   | `/v1/commons/generic_notifications/multi_read`
Common Resources          | Generic Notifications                   | Create a Generic Notification                     | POST   | `/v1/commons/generic_notifications`
Common Resources          | Generic Notifications                   | Create or Update Generic Notifications            | POST   | `/v1/commons/generic_notifications/multi_upsert`
Common Resources          | Generic Notifications                   | Update a Generic Notification                     | PUT    | `/v1/commons/generic_notifications/{id}`
Common Resources          | Generic Notifications                   | Delete a Generic Notification                     | DELETE | `/v1/commons/generic_notifications/{id}`
Common Resources          | Generic Notifications                   | Delete Generic Notifications                      | POST   | `/v1/commons/generic_notifications/multi_delete`
Common Resources          | Hours of Operation                      | Retrieve All Hours of Operation or by Name        | GET    | `/v1/commons/hours_operation`
Common Resources          | Hours of Operation                      | Retrieve Hours of Operation by ID                 | GET    | `/v1/commons/hours_operation/{id}`
Common Resources          | Hours of Operation                      | Retrieve Multiple Hours of Operation              | POST   | `/v1/commons/hours_operation/multi_read`
Common Resources          | Hours of Operation                      | Create Hours of Operation                         | POST   | `/v1/commons/hours_operation`
Common Resources          | Hours of Operation                      | Create Multiple Hours of Operation                | POST   | `/v1/commons/hours_operation/multi_create`
Common Resources          | Hours of Operation                      | Update Hours of Operation by ID                   | PUT    | `/v1/commons/hours_operation/{id}`
Common Resources          | Hours of Operation                      | Update Multiple Hours of Operation                | POST   | `/v1/commons/hours_operation/multi_update`
Common Resources          | Hours of Operation                      | Delete Hours of Operation by ID                   | DELETE | `/v1/commons/hours_operation/{id}`
Common Resources          | Hours of Operation                      | Delete Multiple Hours of Operation                | POST   | `/v1/commons/hours_operation/multi_delete`
Common Resources          | Hours of Operation Assignments          | Retrieve Hours of Operation Assignments--One Location       | GET    | `/v1/commons/hours_operation_assignments`
Common Resources          | Hours of Operation Assignments          | Retrieve Hours of Operation Assignments--Multiple Locations | POST   | `/v1/commons/hours_operation_assignments/multi_read`
Common Resources          | Hours of Operation Assignments          | Create or Update Hours of Operation Assignments   | POST   | `/v1/commons/hours_operation_assignments/multi_upsert`
Common Resources          | Hours of Operation Assignments          | Delete Hours of Operation Assignments             | POST   | `/v1/commons/hours_operation_assignments/multi_delete`
Common Resources          | Hours of Operation Overrides            | Retrieve All Hours of Operation Overrides or by Name | GET | `/v1/commons/hours_operation_override`
Common Resources          | Hours of Operation Overrides            | Retrieve Hours of Operation Override by ID        | GET    | `/v1/commons/hours_operation_override/{id}`
Common Resources          | Hours of Operation Overrides            | Retrieve Hours of Operation Overrides             | POST   | `/v1/commons/hours_operation_override/multi_read`
Common Resources          | Hours of Operation Overrides            | Create Hours of Operation Override                | POST   | `/v1/commons/hours_operation_override`
Common Resources          | Hours of Operation Overrides            | Create Hours of Operation Overrides               | POST   | `/v1/commons/hours_operation_override/multi_create`
Common Resources          | Hours of Operation Overrides            | Update Hours of Operation Override by ID          | PUT    | `/v1/commons/hours_operation_override/{id}`
Common Resources          | Hours of Operation Overrides            | Update Hours of Operation Overrides               | POST   | `/v1/commons/hours_operation_override/multi_update`
Common Resources          | Hours of Operation Overrides            | Delete Hours of Operation Override by ID          | DELETE | `/v1/commons/hours_operation_override/{id}`
Common Resources          | Hours of Operation Overrides            | Delete Hours of Operation Overrides               | POST   | `/v1/commons/hours_operation_override/multi_delete`
Common Resources          | Hours of Operation Override Assignments | Retrieve Hours of Operation Override Assignment   | GET    | `/v1/commons/hours_operation_override_assignments`
Common Resources          | Hours of Operation Override Assignments | Retrieve Hours of Operation Override Assignments  | POST   | `/v1/commons/hours_operation_override_assignments/multi_read`
Common Resources          | Hours of Operation Override Assignments | Create or Update Hours of Operation Override Assignments | POST   | `/v1/commons/hours_operation_override_assignments/multi_upsert`
Common Resources          | Hours of Operation Override Assignments | Delete Hours of Operation Override Assignments    | POST   | `/v1/commons/hours_operation_override_assignments/multi_delete`
Common Resources          | Hyperfind > Hyperfind Queries           | Retrieve Hyperfind Query by ID                    | GET   | `/v1/commons/hyperfind/{id}`
Common Resources          | Information Access > Data Dictionary    | Update or Create Data Elements                    | POST   | `/v1/commons/data_dictionary/data_elements/multi_upsert`
Common Resources          | Information Access > Data Dictionary    | Retrieve Time Increments                          | GET    | `/v1/commons/data_dictionary/time_increments`
Common Resources          | Information Access > Entity Definitions | Retrieve All Entity Definitions                   | GET    | `/v1/commons/entity_definitions`
Common Resources          | Information Access > Entity Definitions | Retrieve Entity Definition by ID                  | GET    | `/v1/commons/entity_definitions/{id}`
Common Resources          | Information Access > Entity Definitions | Retrieve Entity Definitions                       | POST   | `/v1/commons/entity_definitions/multi_read`
Common Resources          | Information Access > Entity Definitions | Create Entity Definition                          | POST   | `/v1/commons/entity_definitions`
Common Resources          | Information Access > Entity Definitions | Create Entity Definitions                         | POST   | `/v1/commons/entity_definitions/multi_create`
Common Resources          | Information Access > Entity Definitions | Create or Update Entity Definitions               | POST   | `/v1/commons/entity_definitions/multi_upsert`
Common Resources          | Information Access > Entity Definitions | Update Entity Definition by ID                    | PUT    | `/v1/commons/entity_definitions/{id}`
Common Resources          | Information Access > Entity Definitions | Update Entity Definitions                         | POST   | `/v1/commons/entity_definitions/multi_update`
Common Resources          | Information Access > Entity Definitions | Delete Entity Definition by ID                    | DELETE | `/v1/commons/entity_definitions/{id}`
Forecasting               | Budget Distribution Types               | Retrieve All Budget Distribution Types            | GET    | `/v1/forecasting/budget_distribution_types`
Forecasting               | Forecasting Category Profiles           | Retrieve All Forecasting Category Profiles, Only Active, or by Name | GET    | `/v1/forecasting/category_profiles`
Forecasting               | Forecasting Category Profiles           | Retrieve Forecasting Category Profile by ID       | GET    | `/v1/forecasting/category_profiles/{id}`
Forecasting               | Forecasting Category Profiles           | Retrieve Forecasting Category Profiles            | POST   | `/v1/forecasting/category_profiles/multi_read`
Forecasting               | Forecasting Category Profiles           | Create Forecasting Category Profile               | POST   | `/v1/forecasting/category_profiles`
Forecasting               | Forecasting Category Profiles           | Create Forecasting Category Profiles              | POST   | `/v1/forecasting/category_profiles/multi_create`
Forecasting               | Forecasting Category Profiles           | Update Forecasting Category Profile by ID         | PUT    | `/v1/forecasting/category_profiles/{id}`
Forecasting               | Forecasting Category Profiles           | Update Forecasting Category Profiles              | POST   | `/v1/forecasting/category_profiles/multi_update`
Forecasting               | Forecasting Category Profiles           | Delete Forecasting Category Profile by ID         | DELETE | `/v1/forecasting/category_profiles/{id}`
Forecasting               | Forecasting Category Profiles           | Delete Forecasting Category Profiles              | POST   | `/v1/forecasting/category_profiles/multi_delete`
Forecasting               | Category Property Set Assignments       | Create or Update Category Property Set Assignments | POST   | `/v1/forecasting/category_property_set_assignments/multi_upsert`
Forecasting               | Category Property Set Assignments       | Delete Category Property Set Assignments          | POST   | `/v1/forecasting/category_property_set_assignments/multi_delete`
Forecasting               | Category Property Sets                  | Create Category Property Set                      | POST   | `/v1/forecasting/category_property_sets`
Forecasting               | Category Property Sets                  | Create Category Property Sets                     | POST   | `/v1/forecasting/category_property_sets/multi_create`
Forecasting               | Static Driver Assignments               | Retrieve Static Driver Assignments by Category    | GET    | `/v1/forecasting/static_driver_assignments`
Forecasting               | Static Driver Assignments               | Retrieve Static Driver Assignments                | POST   | `/v1/forecasting/static_driver_assignments/multi_read`
Forecasting               | Static Driver Assignments               | Create Static Driver Assignments                  | POST   | `/v1/forecasting/static_driver_assignments/multi_create`
Forecasting               | Static Driver Assignments               | Delete Static Driver Assignments                  | POST   | `/v1/forecasting/static_driver_assignments/multi_delete`
Forecasting               | Volume Forecast Model Types             | Retrieve All Volume Forecast Model Types          | GET    | `/v1/forecasting/volume_forecast_model_types`
Healthcare Analytics      | HCA Payroll Department Mappings         | Retrieve All Payroll Department Mappings          | GET    | `/v1/hca/payroll/department_maps`
Healthcare Analytics      | HCA Payroll Department Mappings         | Create or Update Payroll Department Mappings      | POST   | `/v1/hca/payroll/department_maps/multi_upsert`
Healthcare Analytics      | HCA Analytics Employment Status Mappings | Retrieve All Analytics Employment Status Mappings     | GET    | `/v1/hca/payroll/employment_status_maps`
Healthcare Analytics      | HCA Analytics Employment Status Mappings | Create or Update Analytics Employment Status Mappings | POST   | `/v1/hca/payroll/employment_status_maps/multi_upsert`
Healthcare Analytics      | HCA Payroll Job Mappings                | Create or Update Payroll Job Mappings             | POST   | `/v1/hca/payroll/job_maps/multi_upsert`
Human Capital Management  | HCM Payroll Aggregation                 | Retrieve Payroll Data for HCM                     | POST   | `/v1/hcm/payroll/data/apply_read`
Platform > Workflow       | Workflow Business Processes             | Retrieve Business Process                         | GET    | `/v1/platform/workflow/business_processes`
Platform > Workflow       | Workflow Business Processes             | Execute Business Process                          | POST   | `/v1/platform/workflow/business_processes/execute`
Platform > KPI Framework  | Mapping Categories                      | Retrieve All Mapping Categories                   | GET    | `/v1/platform/analytics/mapping_categories`
Platform > KPI Framework  | Mapping Categories                      | Retrieve Mapping Category by ID                   | GET    | `/v1/platform/analytics/mapping_categories/{id}`
Platform > KPI Framework  | Mapping Categories                      | Create Mapping Category                           | POST   | `/v1/platform/analytics/mapping_categories`
Platform > KPI Framework  | Mapping Categories                      | Update Mapping Category by ID                     | PUT    | `/v1/platform/analytics/mapping_categories/{id}`
Platform > KPI Framework  | Mapping Category Types                  | Retrieve All Mapping Category Types or by Name    | GET    | `/v1/platform/analytics/mapping_category_types`
Platform > KPI Framework  | Mapping Category Types                  | Retrieve Mapping Category Type by ID              | GET    | `/v1/platform/analytics/mapping_category_types/{id}`
Scheduling                | Workload Coverage                       | Evaluate Workload Coverage Details                | POST    | `/v1/scheduling/workload_coverage/workload_coverage_details/multi_read`
Scheduling Setup          | Schedule Rule Sets                      | Create Rule Set                                   | POST    | `/v1/scheduling/schedule_rule_sets`
Scheduling Setup          | Schedule Rule Sets                      | Update Rule Set by ID                             | PUT     | `/v1/scheduling/schedule_rule_sets/{ruleSetId}`
Scheduling Setup          | Schedule Rule Sets                      | Delete Rule Set by ID                             | DELETE  | `/v1/scheduling/schedule_rule_sets/{ruleSetId}`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Retrieve All Rule Set Location Assignments        | GET    | `/v1/scheduling/schedule_rule_sets/location_assignments`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Retrieve Rule Set Location Assignment by ID       | GET    | `/v1/scheduling/schedule_rule_sets/location_assignments/{id}`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Create or Update Rule Set Location Assignments    | POST   | `/v1/scheduling/schedule_rule_sets/location_assignments/multi_upsert`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Create or Update Rule Set Location Assignment     | PUT    | `/v1/scheduling/schedule_rule_sets/location_assignments`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Delete Rule Set Location Assignment by ID         | DELETE | `/v1/scheduling/schedule_rule_sets/location_assignments/{id}`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Delete Rule Set Location Assignments by Rule Set  | POST   | `/v1/scheduling/schedule_rule_sets/location_assignments/apply_delete`
Scheduling Setup          | Schedule Rule Set Location Assignments  | Delete Rule Set Location Assignments              | POST   | `/v1/scheduling/schedule_rule_sets/location_assignments/multi_delete`
Timekeeping               | Absence Spans                           | Retrieve Absence Spans                            | POST   | `/v1/timekeeping/absence_spans/multi_read`
Timekeeping               | Timekeeping Setup Fixed Rules           | Retrieve Fixed Rule by ID                         | GET    | `/v1/timekeeping/setup/fixed_rules/{id}`
Timekeeping               | Timekeeping Setup Fixed Rules           | Create Fixed Rule                                 | POST   | `/v1/timekeeping/setup/fixed_rules`
Timekeeping               | Timekeeping Setup Fixed Rules           | Delete Fixed Rule by ID                           | DELETE | `/v1/timekeeping/setup/fixed_rules/{id}`
Timekeeping               | Timekeeping Setup Pay Rules             | Retrieve Pay Rules                                | POST   | `/v1/timekeeping/setup/payrules/multi_read`
Timekeeping               | Timekeeping Setup Pay Rules             | Create Pay Rule                                   | POST   | `/v1/timekeeping/setup/payrules`
Timekeeping               | Timekeeping Setup Pay Rules             | Create Pay Rules                                  | POST   | `/v1/timekeeping/setup/payrules/multi_create`
Timekeeping               | Timekeeping Setup Pay Rules             | Update Pay Rule                                   | PUT    | `/v1/timekeeping/setup/payrules/{id}`
Timekeeping               | Timekeeping Setup Pay Rules             | Update Pay Rules                                  | POST   | `/v1/timekeeping/setup/payrules/multi_update`
Timekeeping               | Timekeeping Setup Pay Rules             | Delete Timekeeping Setup Pay Rule by ID           | DELETE | `/v1/timekeeping/setup/payrules/{id}`
Timekeeping               | Timekeeping Setup Pay Rules             | Delete Timekeeping Setup Pay Rules                | POST   | `/v1/timekeeping/setup/payrules/multi_delete`

## Dimensions 4.11.0 {#4110}

The following operations were added to the API in Dimensions 4.11.0:

Domain                    | Resource                                      | Operation                                                             | Method | URL endpoint
----------------          | ----------------                              | ----------------                                                      | ------ | ----------------
Timekeeping               | Absence Spans                                 | Retrieve Absence Spans                                                | POST   | `/v1/timekeeping/absence_spans/multi_read`

## Dimensions 4.10.0 {#4100}

The following operations were added to the API in Dimensions 4.10.0:

Domain                    | Resource                                      | Operation                                                             | Method | URL endpoint
----------------          | ----------------                              | ----------------                                                      | ------ | ----------------
People                    | Person Assignments > Attestation Profile Assignments | Retrieve Attestation Profile Assignments                       | POST   | `/v1/commons/persons/attestation_profile_assignments/multi_read`
People                    | Person Assignments > Attestation Profile Assignments | Update Attestation Profile Assignments                         | POST   | `/v1/commons/persons/attestation_profile_assignments/multi_update`
Common Resources          | Function Access Profiles                      | Retrieve All Function Access Profiles                                 | GET    | `/v1/commons/function_access_profiles`
Common Resources          | Function Access Profiles                      | Retrieve Function Access Profile by ID                                | GET    | `/v1/commons/function_access_profiles/{id}`
Common Resources          | Function Access Profiles                      | Create Function Access Profile                                        | POST   | `/v1/commons/function_access_profiles`
Common Resources          | Function Access Profiles                      | Update Function Access Profile by ID                                  | PUT    | `/v1/commons/function_access_profiles/{id}`
Common Resources          | Function Access Profiles                      | Delete Function Access Profile by ID                                  | DELETE | `/v1/commons/function_access_profiles/{id}`
Common Resources          | Access Control Points                         | Retrieve All Access Control Points                                    | GET    | `/v1/commons/access_control_points`
Scheduling Setup          | Standard Shift Set Assignments                | Retrieve Shift Set Assignments                                        | POST   | `/v1/scheduling/standard_shift_sets/assignments/multi_read`
Scheduling Setup          | Standard Shift Sets                           | Retrieve All Standard Shift Sets or by Name                           | GET    | `/v1/scheduling/standard_shift_sets`
Scheduling Setup          | Standard Shift Sets                           | Retrieve Standard Shift Sets by ID                                    | GET    | `/v1/scheduling/standard_shift_sets/{id}`
Scheduling Setup          | Standard Shift Sets                           | Retrieve Standard Shift Sets                                          | POST   | `/v1/scheduling/standard_shift_sets/multi_read`

## Dimensions 4.9.0 {#490}

The following operations were added to the API in Dimensions 4.9.0:

Domain                    | Resource                                      | Operation                                                             | Method | URL endpoint
----------------          | ----------------                              | ----------------                                                      | ------ | ----------------
People                    | Person Assignments > Employee Tag Assignments | Retrieve Employee Tag Assignments by Person ID                        | GET    | `/v1/commons/persons/employee_tags/{person_id}`
People                    | Person Assignments > Employee Tag Assignments | Retrieve Employee Tag Assignments by Person Number                    | GET    | `/v1/commons/persons/employee_tags`
People                    | Person Assignments > Employee Tag Assignments | Retrieve Employee Tag Assignments—Multiple Employees                  | POST   | `/v1/commons/persons/employee_tags/multi_read`
People                    | Person Assignments > Employee Tag Assignments | Create Employee Tag Assignments                                       | POST   | `/v1/commons/persons/employee_tags`
People                    | Person Assignments > Employee Tag Assignments | Create Employee Tag Assignments—Multiple Employees                    | POST   | `/v1/commons/persons/employee_tags/multi_create`
People                    | Person Assignments > Employee Tag Assignments | Create, Update, or Remove Employee Tag Assignments                    | PUT    | `/v1/commons/persons/employee_tags`
People                    | Person Assignments > Employee Tag Assignments | Create, Update, or Remove Employee Tag Assignments—Multiple Employees | POST   | `/v1/commons/persons/employee_tags/multi_upsert`
People                    | Person Assignments > Employee Tag Assignments | Delete Employee Tag Assignments                                       | POST   | `/v1/commons/persons/employee_tags/apply_delete`
People                    | Person Assignments > Employee Tag Assignments | Delete Employee Tag Assignments—Multiple Employees                    | POST   | `/v1/commons/persons/employee_tags/multi_delete`
Scheduling Setup          | Employee Visibility Periods                   | Retrieve All Employee Visibility Periods or by Name                   | GET    | `/v1/scheduling/setup/employee_visibility_periods`
Scheduling Setup          | Employee Visibility Periods                   | Retrieve Employee Visibility Period by ID                             | GET    | `/v1/scheduling/setup/employee_visibility_periods/{id}`
Scheduling Setup          | Employee Visibility Periods                   | Retrieve Employee Visibility Periods                                  | POST   | `/v1/scheduling/setup/employee_visibility_periods/multi_read`
Timekeeping               | Bulk Timecard Approvals                       | Bulk Timecard Approvals                                               | POST   | `/v1/timekeeping/approvals/import`
Timekeeping               | Bulk Timecard Approvals                       | Bulk Timecard Delete Approvals                                        | POST   | `/v1/timekeeping/approvals/multi_delete`

## Dimensions 4.8.0 {#480}

The following operations were added to the API in Dimensions 4.8.0:

Domain                    | Resource                          | Operation                                         | Method | URL endpoint
----------------          | ----------------                  | ----------------                                  | ------ | ----------------
Scheduling                | Manager Schedules                 | Retrieve Employee Schedule Changes                | POST   | `/v1/scheduling/schedule/changes/multi_read`
Scheduling                | Manager Schedule Actions          | Send Schedule Change Notifications                | POST   | `/v1/scheduling/schedule_management_actions/notifications/apply_update`

## Dimensions 4.7.0 {#470}

The following operation was added to the API in Dimensions 4.7.0:

Domain                    | Resource                          | Operation                                         | Method | URL endpoint
----------------          | ----------------                  | ----------------                                  | ------ | ----------------
Common Resources          | Bulk Downloads                    | Delete Bulk Downloads                             | POST   | `/v1/commons/exports/multi_delete`

## Dimensions 4.4.0 {#440}

The following operations were added to the API in Dimensions 4.4.0:

Domain                    | Resource                          | Operation                                         | Method | URL endpoint
----------------          | ----------------                  | ----------------                                  | ------ | ----------------
Common Resources          | Comments                          | Retrieve Comments-Employee                        | GET    | `/v1/commons/comments/employee_comments`
Common Resources          | Control Center Profiles           | Retrieve All Control Center Profiles              | GET    | `/v1/commons/control_center_profiles`
Common Resources          | Control Center Profiles           | Retrieve Control Center Profile by ID             | GET    | `/v1/commons/control_center_profiles/{id}`
Common Resources          | Control Center Profiles           | Retrieve Control Center Profiles                  | POST   | `/v1/commons/control_center_profiles/multi_read`
Common Resources > Information Access | Dataview Profiles     | Retrieve Dataview Profiles                        | POST   | `/v1/commons/dataview_profiles/multi_read`
Common Resources          | Display Profiles                  | Retrieve All Display Profiles                     | GET    | `/v1/commons/display_profiles`
Common Resources          | Display Profiles                  | Retrieve Display Profile by ID                    | GET    | `/v1/commons/display_profiles/{id}`
Common Resources          | Display Profiles                  | Retrieve Display Profiles                         | POST   | `/v1/commons/display_profiles/multi_read`
Common Resources          | Display Profiles                  | Create Display Profile                            | POST   | `/v1/commons/display_profiles`
Common Resources          | Display Profiles                  | Create Display Profiles                           | POST   | `/v1/commons/display_profiles/multi_create`
Common Resources          | Display Profiles                  | Update Display Profile by ID                      | PUT    | `/v1/commons/display_profiles/{id}`
Common Resources          | Display Profiles                  | Update Display Profiles                           | POST   | `/v1/commons/display_profiles/multi_update`
Common Resources          | Display Profiles                  | Delete Display Profile by ID                      | DELETE | `/v1/commons/display_profiles/{id}`
Common Resources          | Display Profiles                  | Retrieve All Display Profiles                     | GET    | `/v1/commons/display_profiles`
Common Resources          | Bulk Downloads                    | Submit Bulk Download                              | POST   | `/v1/commons/exports/async`
Common Resources          | Bulk Downloads                    | Retrieve Download Request Summary                 | GET    | `/v1/commons/exports`
Common Resources          | Bulk Downloads                    | Retrieve Download Status                          | GET    | `/v1/commons/exports/{id}/status`
Common Resources          | Bulk Downloads                    | Retrieve Download Results                         | GET    | `/v1/commons/exports/{id}/file`
Common Resources > Information Access | Home Pages            | Retrieve Home Page Profiles                       | POST   | `/v1/commons/home_pages/multi_read`
Common Resources > Hyperfind | Hyperfind Profiles             | Retrieve All Hyperfind Profiles                   | GET    | `/v1/commons/hyperfind_profiles`
Common Resources > Hyperfind | Hyperfind Profiles             | Retrieve Hyperfind Profile by ID                  | GET    | `/v1/commons/hyperfind_profiles/{id}`
Common Resources > Hyperfind | Hyperfind Profiles             | Retrieve Hyperfind Profiles                       | POST   | `/v1/commons/hyperfind_profiles/multi_read`
Common Resources > Business Structures | Jobs                 | Retrieve Effective Job by External ID             | GET    | `/v1/commons/jobs/external_ids/{externalId}`
Common Resources > Business Structures | Jobs                 | Retrieve Effective Jobs by External IDs           | POST   | `/v1/commons/jobs/external_ids/multi_read`
Common Resources > Business Structures | Location Types       | Retrieve Location Type by External ID             | GET    | `/v1/commons/location_types/external_ids/{externalId}`
Common Resources > Business Structures | Location Types       | Retrieve Location Types by External IDs           | POST   | `/v1/commons/location_types/external_ids/multi_read`
Common Resources > Business Structures | Locations            | Retrieve Location by External IDs                 | GET    | `/v1/commons/locations/external_ids/{external_id}`
Common Resources > Business Structures | Locations            | Retrieve Locations by External IDs                | POST   | `/v1/commons/locations/external_ids/multi_read`
People                    | People Information Profiles       | Retrieve All People Information Profiles          | GET    | `/v1/commons/person_profiles`
People                    | People Information Profiles       | Retrieve People Information Profile by ID         | GET    | `/v1/commons/person_profiles/{id}`
People                    | People Information Profiles       | Retrieve People Information Profiles              | POST   | `/v1/commons/person_profiles/multi_read`
People                    | Person Assignents > Category Profile Assignments | Retrieve Category Profile Assignment by Person Number | GET    | `/v1/commons/persons/forecasting_category_profiles`
People                    | Person Assignents > Category Profile Assignments | Retrieve Category Profile Assignment by Person Key    | GET    | `/v1/commons/persons/forecasting_category_profiles/{personKey}`
People                    | Person Assignents > Category Profile Assignments | Retrieve Category Profile Assignments                 | POST   | `/v1/commons/persons/forecasting_category_profiles/multi_read`
People                    | Person Assignents > Category Profile Assignments | Create or Update Category Profile Assignment          | PUT    | `/v1/commons/persons/forecasting_category_profiles`
People                    | Person Assignents > Category Profile Assignments | Update Category Profile Assignments                   | POST   | `/v1/commons/persons/forecasting_category_profiles/multi_update`
People                    | Person Assignents > Category Profile Assignments | Delete Category Profile Assignment                    | DELETE | `/v1/commons/persons/forecasting_category_profiles`
People                    | Person Assignents > Category Profile Assignments | Delete Category Profile Assignments                   | POST   | `/v1/commons/persons/forecasting_category_profiles/multi_delete`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Retrieve All Percentage Allocation Rules              | GET    | `/v1/commons/persons/percentage_allocation_rules/multi_read`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Retrieve Percentage Allocation Rules by ID            | GET    | `/v1/commons/persons/percentage_allocation_rules/{personId}`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Retrieve Percentage Allocation Rules by Person Number | GET    | `/v1/commons/persons/percentage_allocation_rules`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Assign Percentage Allocation Rule                     | POST   | `/v1/commons/persons/percentage_allocation_rules`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Assign Percentage Allocation Rule—Multiple Employees  | POST   | `/v1/commons/persons/percentage_allocation_rules/multi_create`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Update Percentage Allocation Rule                     | PUT    | `/v1/commons/persons/percentage_allocation_rules`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Update Percentage Allocation Rule—Multiple Employees  | POST   | `/v1/commons/persons/percentage_allocation_rules/multi_update`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Delete Percentage Allocation Rule                     | DELETE | `/v1/commons/persons/percentage_allocation_rules`
People                    | Person Assignents > Percentage Allocation Rule Assignments | Delete Percentage Allocation Rule—Multiple Employees  | POST   | `/v1/commons/persons/percentage_allocation_rules/multi_delete`
People                    | Person Assignents > Schedule Rule Overrides | Retrieve All Schedule Rule Overrides or by Person Number | GET    | `/v1/commons/persons/schedule_rule_overrides`
People                    | Person Assignents > Schedule Rule Overrides | Retrieve Schedule Rule Override by ID                    | GET    | `/v1/commons/persons/schedule_rule_overrides/{person_id}`
People                    | Person Assignents > Schedule Rule Overrides | Retrieve Schedule Rule Overrides                         | POST   | `/v1/commons/persons/schedule_rule_overrides/multi_read`
People                    | Person Assignents > Schedule Rule Overrides | Create Schedule Rule Override                            | POST   | `/v1/commons/persons/schedule_rule_overrides`
People                    | Person Assignents > Schedule Rule Overrides | Create Schedule Rule Overrides                           | POST   | `/v1/commons/persons/schedule_rule_overrides/multi_create`
People                    | Person Assignents > Schedule Rule Overrides | Update Schedule Rule Override                            | PUT    | `/v1/commons/persons/schedule_rule_overrides`
People                    | Person Assignents > Schedule Rule Overrides | Update Schedule Rule Overrides                           | POST   | `/v1/commons/persons/schedule_rule_overrides/multi_upsert`
People                    | Person Assignents > Schedule Rule Overrides | Delete Schedule Rule Override by ID                      | DELETE | `/v1/commons/persons/schedule_rule_overrides/{schedule_rule_override_id}`
People                    | Person Assignents > Schedule Rule Overrides | Delete Schedule Rule Overrides                           | POST   | `/v1/commons/persons/schedule_rule_overrides/multi_delete`
Forecasting               | Actual Volume                     | Retrieve Actual Volume by Site                    | POST   | `/v1/forecasting/actual_volume/multi_read`
Forecasting               | Actual Volume                     | Import Actual Volume                              | POST   | `/v1/forecasting/actual_volume/import`
Forecasting               | Category Property Set Assignments | Retrieve Category Property Set Assignment         | GET    | `/v1/forecasting/category_property_set_assignments`
Forecasting               | Category Property Set Assignments | Retrieve Category Property Set Assignments        | POST   | `/v1/forecasting/category_property_set_assignments/multi_read`
Forecasting               | Category Property Sets            | Retrieve All Category Property Sets or by Name    | GET    | `/v1/forecasting/category_property_sets`
Forecasting               | Category Property Sets            | Retrieve Category Property Set by ID              | GET    | `/v1/forecasting/category_property_sets/{id}`
Forecasting               | Category Property Sets            | Retrieve Category Property Sets                   | POST   | `/v1/forecasting/category_property_sets/multi_read`
Forecasting               | Combined Labor Distributions      | Retrieve All Combined Labor Distributions or by Specification | GET    | `/v1/forecasting/combined_labor_distributions`
Forecasting               | Combined Labor Distributions      | Retrieve Combined Labor Distribution by ID        | GET    | `/v1/forecasting/combined_labor_distributions/{id}`
Forecasting               | Combined Labor Distributions      | Retrieve Combined Labor Distributions             | POST   | `/v1/forecasting/combined_labor_distributions/multi_read`
Forecasting               | Combined Labor Distributions      | Create Combined Labor Distribution                | POST   | `/v1/forecasting/combined_labor_distributions`
Forecasting               | Combined Labor Distributions      | Create Combined Labor Distributions               | POST   | `/v1/forecasting/combined_labor_distributions/multi_create`
Forecasting               | Combined Labor Distributions      | Update Combined Labor Distribution by ID          | PUT    | `/v1/forecasting/combined_labor_distributions/{id}`
Forecasting               | Combined Labor Distributions      | Update Combined Labor Distributions               | POST   | `/v1/forecasting/combined_labor_distributions/multi_update`
Forecasting               | Combined Labor Distributions      | Delete Combined Labor Distribution by ID          | DELETE | `/v1/forecasting/combined_labor_distributions/{id}`
Forecasting               | Combined Labor Distributions      | Delete Combined Labor Distributions               | POST   | `/v1/forecasting/combined_labor_distributions/multi_delete`
Forecasting               | Combined Distribution Offset Types | Retrieve Combined Distribution Offset Types      | GET    | `/v1/forecasting/combined_distribution_offset_types`
Forecasting               | Combined Distribution Types       | Retrieve Combined Distribution Types              | GET    | `/v1/forecasting/combined_distribution_types`
Forecasting               | Consolidated Labor Forecast       | Retrieve Consolidated Labor Forecasts             | POST   | `/v1/forecasting/consolidated_labor_forecast/apply_read`
Forecasting               | Custom Driver Assignments         | Retrieve Custom Driver Assignments                | GET    | `/v1/forecasting/custom_driver_assignments`
Forecasting               | Custom Driver Assignments         | Retrieve Custom Driver Assignments by Context     | POST   | `/v1/forecasting/custom_driver_assignments/apply_read`
Forecasting               | Custom Driver Assignments         | Retrieve Custom Driver Assignments by Category    | POST   | `/v1/forecasting/custom_driver_assignments/multi_read`
Forecasting               | Custom Drivers                    | Retrieve Custom Driver Values                     | POST   | `/v1/forecasting/custom_driver_values/multi_read`
Forecasting               | Custom Drivers                    | Update Custom Driver Values                       | POST   | `/v1/forecasting/custom_driver_values/apply_upsert`
Forecasting               | Custom Drivers                    | Update Values for Multiple Custom Drivers         | POST   | `/v1/forecasting/custom_driver_values/multi_upsert`
Forecasting               | Custom Drivers Setup              | Retrieve a Custom Driver by Name and Generic Department | GET    | `/v1/forecasting/custom_drivers`
Forecasting               | Custom Drivers Setup              | Retrieve a Custom Driver by ID                    | GET    | `/v1/forecasting/custom_drivers/{id}`
Forecasting               | Custom Drivers Setup              | Retrieve Custom Drivers                           | POST   | `/v1/forecasting/custom_drivers/multi_read`
Forecasting               | Custom Drivers Setup              | Create Custom Driver                              | POST   | `/v1/forecasting/custom_drivers`
Forecasting               | Custom Drivers Setup              | Create Custom Drivers                             | POST   | `/v1/forecasting/custom_drivers/multi_create`
Forecasting               | Custom Drivers Setup              | Update Custom Driver by ID                        | PUT    | `/v1/forecasting/custom_drivers/{id}`
Forecasting               | Custom Drivers Setup              | Update Custom Drivers                             | POST   | `/v1/forecasting/custom_drivers/multi_update`
Forecasting               | Custom Drivers Setup              | Delete Custom Driver by ID                        | DELETE | `/v1/forecasting/custom_drivers/{id}`
Forecasting               | Custom Drivers Setup              | Delete Custom Drivers                             | POST   | `/v1/forecasting/custom_drivers/multi_delete`
Forecasting               | Earned Hours Engine               | Execute Earned Hours Engine                       | POST   | `/v1/forecasting/earned_hours_engine/apply_create`
Forecasting               | Engine Status                     | Retrieve Engine Statuses                          | POST   | `/v1/forecasting/engine_statuses/apply_read`
Forecasting               | Forecast Planner Profiles         | Retrieve All Forecast Planner Profiles or by Name | GET    | `/v1/forecasting/forecast_planner_profiles`
Forecasting               | Forecast Planner Profiles         | Retrieve a Forecast Planner Profile by ID         | GET    | `/v1/forecasting/forecast_planner_profiles/{id}`
Forecasting               | Forecast Planner Profiles         | Retrieve Forecast Planner Profiles                | POST   | `/v1/forecasting/forecast_planner_profiles/multi_read`
Forecasting               | Forecast Planner Profiles         | Create a Forecast Planner Profile                 | POST   | `/v1/forecasting/forecast_planner_profiles`
Forecasting               | Forecast Planner Profiles         | Create Forecast Planner Profiles                  | POST   | `/v1/forecasting/forecast_planner_profiles/multi_create`
Forecasting               | Forecast Planner Profiles         | Update a Forecast Planner Profile by ID           | PUT    | `/v1/forecasting/forecast_planner_profiles/{id}`
Forecasting               | Forecast Planner Profiles         | Update Forecast Planner Profiles                  | POST   | `/v1/forecasting/forecast_planner_profiles/multi_update`
Forecasting               | Forecast Planner Profiles         | Delete a Forecast Planner Profile by Name         | DELETE | `/v1/forecasting/forecast_planner_profiles`
Forecasting               | Forecast Planner Profiles         | Delete a Forecast Planner Profile by ID           | DELETE | `/v1/forecasting/forecast_planner_profiles/{id}`
Forecasting               | Forecast Planner Profiles         | Delete Forecast Planner Profiles                  | POST   | `/v1/forecasting/forecast_planner_profiles/multi_delete`
Forecasting               | Forecast Planner Settings         | Retrieve All Forecast Planner Settings or by Name | GET    | `/v1/forecasting/forecast_planner_settings`
Forecasting               | Forecast Planner Settings         | Retrieve a Forecast Planner Setting by ID         | GET    | `/v1/forecasting/forecast_planner_settings/{id}`
Forecasting               | Forecast Planner Settings         | Retrieve Forecast Planner Settings                | POST   | `/v1/forecasting/forecast_planner_settings/multi_read`
Forecasting               | Forecast Planner Settings         | Create a Forecast Planner Setting                 | POST   | `/v1/forecasting/forecast_planner_settings`
Forecasting               | Forecast Planner Settings         | Create Forecast Planner Settings                  | POST   | `/v1/forecasting/forecast_planner_settings/multi_create`
Forecasting               | Forecast Planner Settings         | Update a Forecast Planner Setting by ID           | PUT    | `/v1/forecasting/forecast_planner_settings/{id}`
Forecasting               | Forecast Planner Settings         | Update Forecast Planner Settings                  | POST   | `/v1/forecasting/forecast_planner_settings/multi_update`
Forecasting               | Forecast Planner Settings         | Delete a Forecast Planner Setting by Name         | DELETE | `/v1/forecasting/forecast_planner_settings`
Forecasting               | Forecast Planner Settings         | Delete a Forecast Planner Setting by ID           | DELETE | `/v1/forecasting/forecast_planner_settings/{id}`
Forecasting               | Forecast Planner Settings         | Delete Forecast Planner Settings                  | POST   | `/v1/forecasting/forecast_planner_settings/multi_delete`
Forecasting               | Forecast Planner Settings         | Retrieve Factor Definition Types                  | GET    | `/v1/forecasting/forecast_planner_settings/resources/factor_types`
Forecasting               | Forecast Planner Settings         | Retrieve Steps                                    | GET    | `/v1/forecasting/forecast_planner_settings/resources/steps`
Forecasting               | Forecast Week                     | Retrieve a Forecast Week                          | GET    | `/v1/forecasting/forecast_week`
Forecasting               | Forecast Week                     | Retrieve Start Day                                | GET    | `/v1/forecasting/forecast_week/start_day`
Forecasting               | Forecast Week                     | Retrieve Start Days                               | POST   | `/v1/forecasting/forecast_week/start_days/multi_read`
Forecasting               | Forecast Week                     | Retrieve Default Start Day                        | GET    | `/v1/forecasting/forecast_week/default_start_day`
Forecasting               | Forecasting Audits                | Retrieve Forecasting Audit Data                   | POST   | `/v1/forecasting/audit_records/multi_read`
Forecasting               | Generic Categories                | Retrieve All Generic Categories or by Name        | GET    | `/v1/forecasting/generic_categories`
Forecasting               | Generic Categories                | Retrieve Generic Category by ID                   | GET    | `/v1/forecasting/generic_categories/{id}`
Forecasting               | Generic Categories                | Retrieve Generic Categories                       | POST   | `/v1/forecasting/generic_categories/multi_read`
Forecasting               | Hours of Operation                | Retrieve All Hours of Operation or by Name        | GET    | `/v1/forecasting/hours_operation`
Forecasting               | Hours of Operation                | Retrieve Hours of Operation by ID                 | GET    | `/v1/forecasting/hours_operation/{id}`
Forecasting               | Hours of Operation                | Retrieve Multiple Hours of Operation              | POST   | `/v1/forecasting/hours_operation/multi_read`
Forecasting               | Hours of Operation                | Create Hours of Operation                         | POST   | `/v1/forecasting/hours_operation`
Forecasting               | Hours of Operation                | Create Multiple Hours of Operation                | POST   | `/v1/forecasting/hours_operation/multi_create`
Forecasting               | Hours of Operation                | Update Hours of Operation by ID                   | PUT    | `/v1/forecasting/hours_operation/{id}`
Forecasting               | Hours of Operation                | Update Multiple Hours of Operation                | POST   | `/v1/forecasting/hours_operation/multi_update`
Forecasting               | Hours of Operation                | Retrieve All Hours of Operation or by Name        | GET    | `/v1/forecasting/hours_operation`
Forecasting               | Hours of Operation                | Delete Hours of Operation by ID                   | DELETE | `/v1/forecasting/hours_operation/{id}`
Forecasting               | Hours of Operation                | Delete Multiple Hours of Operation                | POST   | `/v1/forecasting/hours_operation/multi_delete`
Forecasting               | Hours of Operation Assignments    | Retrieve Hours of Operation Assignments--One Location       | GET    | `/v1/forecasting/hours_operation_assignments`
Forecasting               | Hours of Operation Assignments    | Retrieve Hours of Operation Assignments--Multiple Locations | POST   | `/v1/forecasting/hours_operation_assignments/multi_read`
Forecasting               | Hours of Operation Assignments    | Create or Update Hours of Operation Assignments   | POST   | `/v1/forecasting/hours_operation_assignments/multi_upsert`
Forecasting               | Hours of Operation Assignments    | Delete Hours of Operation Assignments             | POST   | `/v1/forecasting/hours_operation_assignments/multi_delete`
Forecasting               | Hours of Operation Overrides      | Retrieve All Hours of Operation Overrides or by Name | GET   | `/v1/forecasting/hours_operation_override`
Forecasting               | Hours of Operation Overrides      | Retrieve Hours of Operation Override by ID        | GET   | `/v1/forecasting/hours_operation_override/{id}`
Forecasting               | Hours of Operation Overrides      | Retrieve Hours of Operation Overrides             | POST  | `/v1/forecasting/hours_operation_override/multi_read`
Forecasting               | Hours of Operation Overrides      | Create Hours of Operation Override                | POST  | `/v1/forecasting/hours_operation_override`
Forecasting               | Hours of Operation Overrides      | Create Hours of Operation Overrides               | POST  | `/v1/forecasting/hours_operation_override/multi_create`
Forecasting               | Hours of Operation Overrides      | Update Hours of Operation Override by ID          | PUT   | `/v1/forecasting/hours_operation_override/{id}`
Forecasting               | Hours of Operation Overrides      | Update Hours of Operation Overrides               | POST  | `/v1/forecasting/hours_operation_override/multi_update`
Forecasting               | Hours of Operation Overrides      | Delete Hours of Operation Override by ID          | DELETE | `/v1/forecasting/hours_operation_override/{id}`
Forecasting               | Hours of Operation Overrides      | Delete Hours of Operation Overrides               | POST  | `/v1/forecasting/hours_operation_override/multi_delete`
Forecasting               | Hours of Operation Override Assignments | Retrieve Hours of Operation Override Assignment  | GET   | `/v1/forecasting/hours_operation_override_assignments`
Forecasting               | Hours of Operation Override Assignments | Retrieve Hours of Operation Override Assignments | POST  | `/v1/forecasting/hours_operation_override_assignments/multi_read`
Forecasting               | Hours of Operation Override Assignments | Create or Update Hours of Operation Override Assignments | POST   | `/v1/forecasting/hours_operation_override_assignments/multi_upsert`
Forecasting               | Hours of Operation Override Assignments | Delete Hours of Operation Override Assignments   | POST  | `/v1/forecasting/hours_operation_override_assignments/multi_delete`
Forecasting               | Labor Budget                      | Retrieve Labor Budgets                            | POST   | `/v1/forecasting/labor_budget/apply_read`
Forecasting               | Labor Budget                      | Import Labor Budgets                              | POST   | `/v1/forecasting/labor_budget/import`
Forecasting               | Labor Forecast                    | Retrieve Labor Forecasts                          | POST   | `/v1/forecasting/labor_forecast/apply_read`
Forecasting               | Labor Forecast                    | Import Labor Forecasts                            | POST   | `/v1/forecasting/labor_forecast/import`
Forecasting               | Labor Forecast                    | Update Labor Forecast                             | POST   | `/v1/forecasting/labor_forecast`
Forecasting               | Labor Forecast                    | Update Labor Forecasts                            | POST   | `/v1/forecasting/labor_forecast/multi_update`
Forecasting               | Labor Forecast Limits             | Retrieve Labor Forecast Limit by Name             | GET    | `/v1/forecasting/labor_forecast_limits`
Forecasting               | Labor Forecast Limits             | Retrieve Labor Forecast Limit by ID               | GET    | `/v1/forecasting/labor_forecast_limits/{id}`
Forecasting               | Labor Forecast Limits             | Retrieve Labor Forecast Limits                    | POST   | `/v1/forecasting/labor_forecast_limits/multi_read`
Forecasting               | Labor Forecast Limits             | Create Labor Forecast Limit                       | POST   | `/v1/forecasting/labor_forecast_limits`
Forecasting               | Labor Forecast Limits             | Create Labor Forecast Limits                      | POST   | `/v1/forecasting/labor_forecast_limits/multi_create`
Forecasting               | Labor Forecast Limits             | Update Labor Forecast Limit by ID                 | PUT    | `/v1/forecasting/labor_forecast_limits/{id}`
Forecasting               | Labor Forecast Limits             | Update Labor Forecast Limits                      | POST   | `/v1/forecasting/labor_forecast_limits/multi_update`
Forecasting               | Labor Forecast Limits             | Delete Labor Forecast Limit by ID                 | DELETE | `/v1/forecasting/labor_forecast_limits/{id}`
Forecasting               | Labor Forecast Limits             | Delete Labor Forecast Limits                      | POST   | `/v1/forecasting/labor_forecast_limits/multi_delete`
Forecasting               | Labor Forecast Limit Assignments  | Retrieve Labor Forecast Limit Assignments         | POST   | `/v1/forecasting/labor_forecast_limit_assignments/multi_read`
Forecasting               | Labor Forecast Limit Assignments  | Create or Update Labor Forecast Limit Assignments | POST   | `/v1/forecasting/labor_forecast_limit_assignments/multi_upsert`
Forecasting               | Labor Forecast Limit Assignments  | Delete Labor Forecast Limit Assignments           | POST   | `/v1/forecasting/labor_forecast_limit_assignments/multi_delete`
Forecasting               | Labor Forecast Engine             | Execute Labor Forecast Engine                     | POST   | `/v1/forecasting/labor_forecaster/apply_create`
Forecasting               | Labor Standards                   | Retrieve All Labor Standards or by Specification  | GET    | `/v1/forecasting/labor_standards`
Forecasting               | Labor Standards                   | Retrieve Labor Standard by ID                     | GET    | `/v1/forecasting/labor_standards/{id}`
Forecasting               | Labor Standards                   | Retrieve Labor Standards                          | POST   | `/v1/forecasting/labor_standards/multi_read`
Forecasting               | Labor Standards, Tasks, and Task Groups | Import Labor Standards, Tasks, and Task Groups | POST | `/v1/forecasting/labor_standard_tasks/import`
Forecasting               | Labor Standards, Tasks, and Task Groups | Purge Labor Standards                          | POST | `/v1/forecasting/labor_standard_tasks/purge`
Forecasting               | Linked Categories                 | Retrieve All Linked Categories or by Specification | GET   | `/v1/forecasting/linked_category`
Forecasting               | Linked Categories                 | Retrieve Linked Categories                        | POST   | `/v1/forecasting/linked_category/multi_read`
Forecasting               | Linked Categories                 | Create Linked Categories                          | POST   | `/v1/forecasting/linked_category/multi_create`
Forecasting               | Linked Categories                 | Update Linked Categories                          | POST   | `/v1/forecasting/linked_category/multi_update`
Forecasting               | Linked Categories                 | Delete Linked Categories                          | POST   | `/v1/forecasting/linked_category/multi_delete`
Forecasting               | Linked Category Action Types      | Retrieve Linked Category Action Types             | GET    | `/v1/forecasting/linked_category_action_types`
Forecasting               | Period of Application Types       | Retrieve Period of Application Types              | GET    | `/v1/forecasting/labor_poa_types`
Forecasting               | Special Events                    | Retrieve All Special Events                       | GET    | `/v1/forecasting/special_events`
Forecasting               | Special Events                    | Retrieve a Special Event by ID                    | GET    | `/v1/forecasting/special_events/{id}`
Forecasting               | Special Events                    | Retrieve Special Events                           | POST   | `/v1/forecasting/special_events/multi_read`
Forecasting               | Special Events                    | Create a Special Event                            | POST   | `/v1/forecasting/special_events`
Forecasting               | Special Events                    | Create Special Events                             | POST   | `/v1/forecasting/special_events/multi_create`
Forecasting               | Special Events                    | Update Special Event by ID                        | PUT    | `/v1/forecasting/special_events/{id}`
Forecasting               | Special Events                    | Update Special Events                             | POST   | `/v1/forecasting/special_events/multi_update`
Forecasting               | Special Events                    | Delete Special Event by ID                        | DELETE | `/v1/forecasting/special_events/{id}`
Forecasting               | Special Events                    | Delete Special Events                             | POST   | `/v1/forecasting/special_events/multi_delete`
Forecasting               | Special Event Assignments         | Retrieve Special Event Assignments by Category     | GET    | `/v1/forecasting/special_event_assignments`
Forecasting               | Special Event Assignments         | Retrieve Special Event Assignments                 | POST   | `/v1/forecasting/special_event_assignments/multi_read`
Forecasting               | Special Event Assignments         | Create Special Event Assignments                   | POST   | `/v1/forecasting/special_event_assignments/multi_create`
Forecasting               | Special Event Assignments         | Delete Special Event Assignments                   | POST   | `/v1/forecasting/special_event_assignments/multi_delete`
Forecasting               | Static Drivers                    | Retrieve All Static Drivers or by Name            | GET    | `/v1/forecasting/static_drivers`
Forecasting               | Static Drivers                    | Retrieve Static Driver by ID                      | GET    | `/v1/forecasting/static_drivers/{id}`
Forecasting               | Volume Budget                     | Retrieve Volume Budgets                           | POST   | `/v1/forecasting/volume_budget/multi_read`
Forecasting               | Volume Budget                     | Import Volume Budgets                             | POST   | `/v1/forecasting/volume_budget/import`
Forecasting               | Volume Driver Assignments         | Retrieve a Volume Driver Assignment               | GET    | `/v1/forecasting/volume_driver_assignments`
Forecasting               | Volume Driver Assignments         | Retrieve Volume Driver Assignments                | POST   | `/v1/forecasting/volume_driver_assignments/multi_read`
Forecasting               | Volume Driver Assignments         | Create or Update Volume Driver Assignments        | POST   | `/v1/forecasting/volume_driver_assignments/multi_upsert`
Forecasting               | Volume Drivers                    | Retrieve All Volume Drivers or by Name            | GET    | `/v1/forecasting/volume_drivers`
Forecasting               | Volume Drivers                    | Retrieve Volume Driver by ID                      | GET    | `/v1/forecasting/volume_drivers/{id}`
Forecasting               | Volume Drivers                    | Retrieve Volume Drivers                           | POST   | `/v1/forecasting/volume_drivers/multi_read`
Forecasting               | Volume Drivers                    | Create Volume Driver                              | POST   | `/v1/forecasting/volume_drivers`
Forecasting               | Volume Drivers                    | Create Volume Drivers                             | POST   | `/v1/forecasting/volume_drivers/multi_create`
Forecasting               | Volume Drivers                    | Update Volume Driver by ID                        | PUT    | `/v1/forecasting/volume_drivers/{id}`
Forecasting               | Volume Drivers                    | Update Volume Drivers                             | POST   | `/v1/forecasting/volume_drivers/multi_update`
Forecasting               | Volume Drivers                    | Delete Volume Driver by ID                        | DELETE | `/v1/forecasting/volume_drivers/{id}`
Forecasting               | Volume Drivers                    | Delete Volume Drivers                             | POST   | `/v1/forecasting/volume_drivers/multi_delete`
Forecasting               | Volume Forecast                   | Retrieve Volume Forecasts                         | POST   | `/v1/forecasting/volume_forecast/multi_read`
Forecasting               | Volume Forecast                   | Import Volume Forecast                            | POST   | `/v1/forecasting/volume_forecast/import`
Forecasting               | Volume Forecast                   | Restore Volume Forecast                           | POST   | `/v1/forecasting/volume_forecast/restore`
Forecasting               | Volume Forecast                   | Update Volume Forecast                            | PUT    | `/v1/forecasting/volume_forecast`
Forecasting               | Volume Forecast Engine            | Retrieve Volume Forecast Engine Status            | POST   | `/v1/forecasting/volume_forecaster/apply_read`
Forecasting               | Volume Forecast Engine            | Execute Volume Forecast Engine                    | POST   | `/v1/forecasting/volume_forecaster/apply_create`
Forecasting               | Week Symbolic Periods             | Retrieve Week Symbolic Period Types               | GET    | `/v1/forecasting/week_symbolic_periods`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Jobs for Open Shift Requests             | GET    | `/v1/scheduling/employee_open_shift_requests/jobs`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Employee Open Shift Request by ID        | GET    | `/v1/scheduling/employee_open_shift_requests/{openShiftRequestId}`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Other Employees Reporting to Manager     | GET    | `/v1/scheduling/employee_open_shift_requests/employees`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Request Submission Periods               | GET    | `/v1/scheduling/employee_open_shift_requests/submission_periods`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Open Request Subtypes                    | GET    | `/v1/scheduling/employee_open_shift_requests/request_subtypes`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Open Shift Request Information           | POST   | `/v1/scheduling/employee_open_shift_requests/apply_read`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Employee Open Shift Requests             | POST   | `/v1/scheduling/employee_open_shift_requests/multi_read`
Employee Self-Service     | Employee Open Shift Requests      | Retrieve Requestable Open Shifts                  | POST   | `/v1/scheduling/employee_open_shift_requests/open_shifts/multi_read`
Employee Self-Service     | Employee Open Shift Requests      | Create Employee Open Shift Request                | POST   | `/v1/scheduling/employee_open_shift_requests`
Employee Self-Service     | Employee Open Shift Requests      | Update Employee Open Shift Request                | POST   | `/v1/scheduling/employee_open_shift_requests/apply_update`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Self-Schedule Request by Job ID          | GET    | `/v1/scheduling/employee_self_schedule_requests/jobs`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Self-Schedule Request by ID              | GET    | `/v1/scheduling/employee_self_schedule_requests/{essRequestId}`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Other Employees Reporting to Manager for Self-Scheduling | GET    | `/v1/scheduling/employee_self_schedule_requests/employees`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Open Self-Scheduling Request Subtypes    | GET    | `/v1/scheduling/employee_self_schedule_requests/request_subtypes`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Self-Scheduling Request Submission Periods | GET    | `/v1/scheduling/employee_self_schedule_requests/submission_periods`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Self-Schedule Requests                   | POST   | `/v1/scheduling/employee_self_schedule_requests/multi_read`
Employee Self-Service     | Employee Self-Schedule Requests   | Retrieve Requestable Open Shifts for Self-Scheduling | POST   | `/v1/scheduling/employee_self_schedule_requests/open_shifts/multi_read`
Employee Self-Service     | Employee Self-Schedule Requests   | Create Self-Schedule Request                      | POST   | `/v1/scheduling/employee_self_schedule_requests`
Employee Self-Service     | Employee Self-Schedule Requests   | Update Self-Schedule Request by ID                | PUT    | `/v1/scheduling/employee_self_schedule_requests`
Employee Self-Service     | Employee Self-Schedule Requests   | Update Self-Schedule Request State                | POST   | `/v1/scheduling/employee_self_schedule_requests/apply_update`
Employee Self-Service     | Manager Open Shift Requests       | Retrieve Open Shift Request by ID                 | GET    | `/v1/scheduling/open_shift_requests/{openShiftRequestId}`
Employee Self-Service     | Manager Open Shift Requests       | Retrieve Similar Open Shift Requests by ID        | GET    | `/v1/scheduling/open_shift_requests/similar_requests`
Employee Self-Service     | Manager Open Shift Requests       | Retrieve Open Shift Requests as Manager           | POST   | `/v1/scheduling/open_shift_requests/multi_read`
Employee Self-Service     | Manager Open Shift Requests       | Update Open Shift Request                         | POST   | `/v1/scheduling/open_shift_requests/apply_update`
Employee Self-Service     | Manager Self-Schedule Requests    | Retrieve Self-Schedule Requests as Manager        | POST   | `/v1/scheduling/self_schedule_requests/multi_read`
Scheduling Setup          | Schedule Rules                    | Retrieve All Schedule Rules or by Name            | GET    | `/v1/scheduling/schedule_rules`
Scheduling Setup          | Schedule Rules                    | Retrieve Schedule Rule by ID                      | GET    | `/v1/scheduling/schedule_rules/{id}`
Scheduling Setup          | Schedule Rules                    | Retrieve Schedule Rules                           | POST   | `/v1/scheduling/schedule_rules/multi_read`
Scheduling Setup          | Calendar Profiles                 | Retrieve All Calendar Profiles or by Name         | GET    | `/v1/scheduling/setup/ess_calendar_profiles`
Scheduling Setup          | Calendar Profiles                 | Retrieve Calendar Profile by ID                   | GET    | `/v1/scheduling/setup/ess_calendar_profiles/{id}`
Scheduling Setup          | Calendar Profiles                 | Retrieve Calendar Profiles                        | POST   | `/v1/scheduling/setup/ess_calendar_profiles/multi_read`
Scheduling Setup          | Tag Definitions                   | Update Tag Definition by ID                       | PUT    | `/v1/scheduling/setup/tag_definitions/{id}`
Scheduling Setup          | Workload Planner Profiles         | Retrieve All Workload Planner Profiles            | GET    | `/v1/scheduling/setup/workload_planner_profiles`
Scheduling Setup          | Workload Planner Profiles         | Retrieve Workload Planner Profile by ID           | GET    | `/v1/scheduling/setup/workload_planner_profiles/{id}`
Scheduling Setup          | Workload Planner Profiles         | Retrieve Workload Planner Profiles                | POST   | `/v1/scheduling/setup/workload_planner_profiles/multi_read`
Scheduling Setup          | Staffing Matrices                 | Create Staffing Matrix                            | POST   | `/v1/scheduling/staffing_matrices`
Scheduling Setup          | Staffing Matrices                 | Create Staffing Matrices                          | POST   | `/v1/scheduling/staffing_matrices/multi_create`
Scheduling Setup          | Staffing Matrices                 | Update Staffing Matrix by ID                      | PUT    | `/v1/scheduling/staffing_matrices/{id}`
Scheduling Setup          | Staffing Matrices                 | Update Staffing Matrices                          | POST   | `/v1/scheduling/staffing_matrices/multi_update`
Scheduling Setup          | Staffing Matrices                 | Delete Staffing Matrix by ID                      | DELETE | `/v1/scheduling/staffing_matrices/{id}`
Scheduling Setup          | Staffing Matrices                 | Delete Staffing Matrices                          | POST   | `/v1/scheduling/staffing_matrices/multi_delete`
Scheduling Setup          | Workload Patterns                 | Bulk Retrieve Workload Patterns                   | POST   | `/v1/scheduling/workload_patterns/multi_read`
Scheduling Setup          | Workload Patterns                 | Bulk Create or Update Workload Patterns           | POST   | `/v1/scheduling/workload_patterns/multi_upsert`
Scheduling Setup          | Workload Patterns                 | Bulk Delete Workload Patterns                     | POST   | `/v1/scheduling/workload_patterns/multi_delete`
Scheduling                | Schedule Planner Profiles         | Retrieve All Schedule Planner Profiles or by Name | GET    | `/v1/scheduling/setup/schedule_planner_profiles`
Scheduling                | Schedule Planner Profiles         | Retrieve Schedule Planner Profile by ID           | GET    | `/v1/scheduling/setup/schedule_planner_profiles/{id}`
Scheduling                | Schedule Planner Profiles         | Retrieve Schedule Planner Profiles                | POST   | `/v1/scheduling/setup/schedule_planner_profiles/multi_read`
Timekeeping               | Attestation Unapproved Timecard Data | Retrieve Unapproved Timecard Data              | GET    | `/v1/timekeeping/attestation_unapproved_timecard_data`
Timekeeping               | Timekeeping Bulk Operations          | Bulk Import of Punches and Paycode Edits       | POST   | `/v1/timekeeping/data/import`
Timekeeping               | Enable Edits Bulk Update             | Enable Edits Bulk Update                       | POST   | `/v1/timekeeping/enable_edits/import`
Timekeeping               | Bulk Paycode Edits                   | Import Paycode Edits                           | POST   | `/v1/timekeeping/pay_code_edits/import`
Timekeeping               | Bulk Paycode Edits                   | Bulk Delete Paycode Edits                      | POST   | `/v1/timekeeping/pay_code_edits/multi_delete`
Timekeeping               | Timecard Settings                    | Retrieve Timecard Settings                     | POST   | `/v1/timekeeping/setup/timecard_settings/multi_read`
Timekeeping               | Timekeeping Alert Profiles           | Retrieve All Timekeeping Alert Profiles        | GET    | `/v1/timekeeping/setup/timekeeping_alert_profiles`
Timekeeping               | Timekeeping Alert Profiles           | Retrieve Timekeeping alert profile by ID       | GET    | `/v1/timekeeping/setup/timekeeping_alert_profiles/{id}`
Timekeeping               | Timekeeping Alert Profiles           | Retrieve Timekeeping Alert Profiles            | POST   | `/v1/timekeeping/setup/timekeeping_alert_profiles/multi_read`
Timekeeping               | Bulk Timecard Signoffs               | Bulk Timecard Signoffs                         | POST   | `/v1/timekeeping/signoffs/import`
Timekeeping               | Timecard Changes                     | Retrieve Timecard Changes                      | GET    | `/v1/timekeeping/timecard/changes`
Timekeeping               | Timecard Changes                     | Retrieve Timecard Change by ID                 | GET    | `/v1/timekeeping/timecard/changes/{id}`
Timekeeping               | Timecard Changes                     | Update Timecard Change Status                  | PUT    | `/v1/timekeeping/timecard/changes/{id}`
Timekeeping               | Timecard Changes                     | Update Timecard Change Statuses                | POST    | `/v1/timekeeping/timecard/changes/multi_update`
Timekeeping               | Timecard Changes for Reports         | Retrieve Timecard Changes for Reports          | POST   | `/v1/timekeeping/timecard/changes/reports/multi_read`

## Dimensions 3.7.0 {#370}

The following operations were added to the API in Dimensions 3.7.0:

Domain                    | Resource                                                            | Operation                                               | Method           | URL endpoint
----------------          | ----------------                                                    | ----------------                                        | ---------------- | ----------------
People                    | Person Assignments > Employment Terms Assignments for People Import | Retrieve Employment Term Memberships by ID              | GET              | `/v1/commons/persons/employment_terms/{personId}`
People                    | Person Assignments > Employment Terms Assignments for People Import | Retrieve Employment Term Memberships by Person Number   | GET              | `/v1/commons/persons/employment_terms`
People                    | Person Assignments > Employment Terms Assignments for People Import | Retrieve Employment Term Memberships-Multiple Employees | POST             | `/v1/commons/persons/employment_terms/multi_read`
People                    | Person Assignments > Employment Terms Assignments for People Import | Add Employment Term Memberships-One Employee            | POST             | `/v1/commons/persons/employment_terms`
People                    | Person Assignments > Employment Terms Assignments for People Import | Add Employment Term Memberships-Multiple Employees      | POST             | `/v1/commons/persons/employment_terms/multi_create`
People                    | Person Assignments > Employment Terms Assignments for People Import | Update Employment Term Memberships-One Employee         | PUT              | `/v1/commons/persons/employment_terms`
People                    | Person Assignments > Employment Terms Assignments for People Import | Update Employment Term Memberships-Multiple Employees   | POST             | `/v1/commons/persons/employment_terms/multi_upsert`	
People                    | Person Assignments > Employment Terms Assignments for People Import | Remove Employment Term Memberships-One Employee         | POST             | `/v1/commons/persons/employment_terms/apply_delete`
People                    | Person Assignments > Employment Terms Assignments for People Import | Remove Employment Term Memberships-Multiple Employees   | POST             | `/v1/commons/persons/employment_terms/multi_delete`	
People                    | Person Assignments > Group Assignments for People Import            | Retrieve Group Memberships by ID                        | GET              | `/v1/commons/persons/schedule_groups/{personId}`
People                    | Person Assignments > Group Assignments for People Import            | Retrieve Group Memberships by Person Number             | GET              | `/v1/commons/persons/schedule_groups`
People                    | Person Assignments > Group Assignments for People Import            | Retrieve Group Memberships-Multiple Employees           | POST             | `/v1/commons/persons/schedule_groups/multi_read`
People                    | Person Assignments > Group Assignments for People Import            | Add Group Memberships-One Employee                      | POST             | `/v1/commons/persons/schedule_groups`
People                    | Person Assignments > Group Assignments for People Import            | Add Group Memberships-Multiple Employees                | POST             | `/v1/commons/persons/schedule_groups/multi_create`
People                    | Person Assignments > Group Assignments for People Import            | Update Group Memberships-One Employee                   | PUT              | `/v1/commons/persons/schedule_groups`
People                    | Person Assignments > Group Assignments for People Import            | Update Group Memberships-Multiple Employees             | POST             | `/v1/commons/persons/schedule_groups/multi_upsert`	
People                    | Person Assignments > Group Assignments for People Import            | Remove Group Memberships-One Employee                   | POST             | `/v1/commons/persons/schedule_groups/apply_delete`
People                    | Person Assignments > Group Assignments for People Import            | Remove Group Memberships-Multiple Employees             | POST             | `/v1/commons/persons/schedule_groups/multi_delete`
Scheduling Setup          | Staffing Matrices                                                   | Retrieve Staffing Matrix by ID                          | GET              | `/v1/scheduling/staffing_matrices/{id}`
Scheduling Setup          | Staffing Matrices                                                   | Retrieve All Staffing Matrices or by Name               | GET              | `/v1/scheduling/staffing_matrices`
Scheduling Setup          | Staffing Matrices                                                   | Retrieve Staffing Matrices                              | POST             | `/v1/scheduling/staffing_matrices/multi_read`
Scheduling                | Schedule Zone Sets                                                  | Retrieve Schedule Zone Set by ID                        | GET              | `/v1/scheduling/schedule_zone_sets/{id}`
Scheduling                | Schedule Zone Sets                                                  | Retrieve All Schedule Zone Sets or by Name              | GET              | `/v1/scheduling/schedule_zone_sets`
Scheduling                | Schedule Zone Sets                                                  | Retrieve Schedule Zone Sets                             | POST             | `/v1/scheduling/schedule_zone_sets/multi_read`
Scheduling                | Schedule Zone Sets                                                  | Retrieve Schedule Zone Set Assignments                  | POST             | `/v1/scheduling/schedule_zone_sets/assignments/multi_read`

## Dimensions 3.2.0 {#320}

The following operations were added to the API in Dimensions 3.2.0:

Domain                    | Resource                               | Operation                                            | Method           | URL endpoint
----------------          | ----------------                       | ----------------                                     | ---------------- | ----------------
Common Resources          | Custom Tiles                           | Retrieve All Custom Tiles                            | GET              | `/v1/commons/custom_tiles`
Common Resources          | Custom Tiles                           | Retrieve Custom Tile by ID                           | GET              | `/v1/commons/custom_tiles/{id}`
Common Resources          | Custom Tiles                           | Retrieve Custom Tiles                                | POST             | `/v1/commons/custom_tiles/multi_read`
Common Resources          | Custom Tiles                           | Create Custom Tile                                   | POST             | `/v1/commons/custom_tiles`
Common Resources          | Custom Tiles                           | Update Custom Tile by ID                             | PUT              | `/v1/commons/custom_tiles/{id}`
Common Resources          | Custom Tiles                           | Delete Custom Tile by ID                             | DELETE           | `/v1/commons/custom_tiles/{id}`
Scheduling                | Coverage Counting Profiles             | Retrieve Coverage Counting Profile by ID             | GET              | `/v1/scheduling/coverage_counting_profiles/{id}`
Scheduling                | Coverage Counting Profiles             | Retrieve Coverage Counting Profile by Name or All    | GET              | `/v1/scheduling/coverage_counting_profiles`
Scheduling                | Coverage Counting Profiles             | Retrieve Coverage Counting Profiles                  | POST             | `/v1/scheduling/coverage_counting_profiles/multi_read`
Scheduling                | Coverage Counting Profiles             | Retrieve Coverage Counting Profile Assignment        | GET   | `/v1/scheduling/coverage_counting_profiles/assignments`
Scheduling                | Coverage Counting Profiles             | Retrieve Coverage Counting Profile Assignments       | POST             | `/v1/scheduling/coverage_counting_profiles/assignments/multi_read`
Scheduling                | Location Profiles Option Sets          | Retrieve Location Profiles Option Set by ID          | GET              | `/v1/scheduling/location_profiles_option_set/{id}`
Scheduling                | Location Profiles Option Sets          | Retrieve Location Profiles Option Set by Name or All | GET              | `/v1/scheduling/location_profiles_option_set`
Scheduling                | Location Profiles Option Sets          | Retrieve Location Profiles Option Sets               | POST             | `/v1/scheduling/location_profiles_option_set/multi_read`
Scheduling                | Location Profiles Option Sets          | Retrieve Location Profiles Option Set Assignment     | GET   | `/v1/scheduling/location_profiles_option_set/assignments`
Scheduling                | Location Profiles Option Sets          | Retrieve Location Profiles Option Set Assignments    | POST | `/v1/scheduling/location_profiles_option_set/assignments/multi_read`

## Dimensions 3.1.0 {#310}

The following operation was added to the API in Dimensions 3.1.0:

Domain                    | Resource                                             | Operation                                            | Method           | URL endpoint
----------------          | ----------------                                     | ----------------                                     | ---------------- | ----------------
Common Resources          | Device Groups                                        | Retrieve Device Groups                               | GET              | `/v1/commons/device_groups`

## Dimensions 2.7.0 {#270}

The following operations were added to the API in Dimensions 2.7.0:

Domain                    | Resource                                             | Operation                                            | Method           | URL endpoint
----------------          | ----------------                                     | ----------------                                     | ---------------- | ----------------
People                    | Person Assignments > Schedule Rule Set Assignments   | Retrieve Rule Set Assignments                        | GET              | `/v1/commons/persons/schedule_rule_sets`
People                    | Person Assignments > Schedule Rule Set Assignments   | Retrieve Rule Set Assignments—Multiple Employees     | POST             | `/v1/commons/persons/schedule_rule_sets/multi_read`
People                    | Person Assignments > Schedule Rule Set Assignments   | Update Rule Set Assignments by ID                    | PUT              | `/v1/commons/persons/schedule_rule_sets/{personId}`
People                    | Person Assignments > Schedule Rule Set Assignments   | Update Rule Set Assignments—Multiple Employees       | POST             | `/v1/commons/persons/schedule_rule_sets/multi_upsert`
People                    | Scheduling Employee Preferences                      | Retrieve Employee Preferences by ID                  | GET              | `/v1/commons/persons/scheduling_employee_preferences/{personId}`
People                    | Scheduling Employee Preferences                      | Retrieve Employee Preferences by Person Number       | GET              | `/v1/commons/persons/scheduling_employee_preferences`
People                    | Scheduling Employee Preferences                      | Retrieve Employee Preferences                        | POST             | `/v1/commons/persons/scheduling_employee_preferences/multi_read`
People                    | Scheduling Employee Preferences                      | Update Employee Preferences by ID                    | PUT              | `/v1/commons/persons/scheduling_employee_preferences`
People                    | Scheduling Employee Preferences                      | Update Employee Preferences                          | POST             | `/v1/commons/persons/scheduling_employee_preferences/multi_upsert`
Platform > Integrations   | Process Callback                                     | Update Integration Execution Details                 | POST             | `/v1/platform/integrations/update_status`
Scheduling                | Minor Rule Sets                                      | Retrieve Minor Rule by Minor Rule ID                 | GET              | `/v1/scheduling/minor_rule_sets/{id}`
Scheduling                | Minor Rule Sets                                      | Retrieve Minor Rule Value by Name                    | GET              | `/v1/scheduling/minor_rule_sets`
Scheduling                | Minor Rule Sets                                      | Retrieve a Collection of Minor Rules                 | POST             | `/v1/scheduling/minor_rule_sets/multi_read`
Scheduling                | Paycode Value Profiles                               | Retrieve Paycode Value Profile by ID                 | GET              | `/v1/scheduling/pay_code_value_profiles/{id}`
Scheduling                | Paycode Value Profiles                               | Retrieve Paycode Value Profile by Name               | GET              | `/v1/scheduling/pay_code_value_profiles`
Scheduling                | Paycode Value Profiles                               | Retrieve All Paycode Value Profiles                  | POST             | `/v1/scheduling/pay_code_value_profiles/multi_read`
Scheduling                | Paycode Value Profiles                               | Create Paycode Value Profile                         | POST             | `/v1/scheduling/pay_code_value_profiles`
Scheduling                | Paycode Value Profiles                               | Create Paycode Value Profiles                        | POST             | `/v1/scheduling/pay_code_value_profiles/multi_create`
Scheduling                | Paycode Value Profiles                               | Update Paycode Value Profile by ID                   | PUT              | `/v1/scheduling/pay_code_value_profiles/{id}`
Scheduling                | Paycode Value Profiles                               | Update Paycode Value Profiles                        | POST             | `/v1/scheduling/pay_code_value_profiles/multi_update`
Scheduling                | Paycode Value Profiles                               | Delete Paycode Value Profile by ID                   | DELETE           | `/v1/scheduling/pay_code_value_profiles/{id}`
Scheduling                | Paycode Value Profiles                               | Delete Paycode Value Profiles                        | POST             | `/v1/scheduling/pay_code_value_profiles/multi_delete`
Scheduling                | Schedule Rule Sets                                   | Retrieve Rule Set by ID                              | GET              | `/v1/scheduling/schedule_rule_sets/{id}`
Scheduling                | Schedule Rule Sets                                   | Retrieve All Rule Sets or by Name                    | GET              | `/v1/scheduling/schedule_rule_sets`
Scheduling                | Schedule Rule Sets                                   | Retrieve Rule Sets                                   | POST             | `/v1/scheduling/schedule_rule_sets/multi_read`
Scheduling                | Zone Categories                                      | Retrieve Zone Category by ID                         | GET              | `/v1/scheduling/zone_categories/{id}`
Scheduling                | Zone Categories                                      | Retrieve Zone Categories by Name or All              | GET              | `/v1/scheduling/zone_categories`
Scheduling                | Zone Categories                                      | Retrieve All Zone Categories                         | POST             | `/v1/scheduling/zone_categories/multi_read`

## Dimensions 2.6.0 {#260}

The following operations were added to the API in Dimensions 2.6.0:

Domain                    | Resource                                             | Operation                                           | Method           | URL endpoint
----------------          | ----------------                                     | ----------------                                    | ---------------- | ----------------
Scheduling                | Certifications Setup                                 | Retrieve Certification by ID                        | GET              | `/v1/scheduling/certifications/{certificationId}`
Scheduling                | Certifications Setup                                 | Retrieve Certification by Name or All               | GET              | `/v1/scheduling/certifications`
Scheduling                | Certifications Setup                                 | Retrieve Certifications                             | POST             | `/v1/scheduling/certifications/multi_read`
Scheduling                | Certifications Setup                                 | Create Certification                                | POST             | `/v1/scheduling/certifications`
Scheduling                | Certifications Setup                                 | Create Certifications                               | POST             | `/v1/scheduling/certifications/multi_create`
Scheduling                | Certifications Setup                                 | Update Certification by ID                          | PUT              | `/v1/scheduling/certifications/{certificationId}`
Scheduling                | Certifications Setup                                 | Update Certifications                               | POST             | `/v1/scheduling/certifications/multi_update`
Scheduling                | Certifications Setup                                 | Delete Certification by ID                          | DELETE           | `/v1/scheduling/certifications/{certificationId}`
Scheduling                | Certifications Setup                                 | Delete Certifications                               | POST             | `/v1/scheduling/certifications/multi_delete`
Scheduling                | Employee Time Off Requests                           | Retrieve Employee Accrual Balance                   | GET              | `/v1/scheduling/employee_timeoff/accruals`
Scheduling                | Employee Time Off Requests                           | Retrieve Employee Request Period                    | GET              | `/v1/scheduling/employee_timeoff/request_periods`
Scheduling                | Employee Time Off Requests                           | Retrieve Employee Request Subtype                   | GET              | `/v1/scheduling/employee_timeoff/request_subtypes`
Scheduling                | Employee Time Off Requests                           | Retrieve Employee Symbolic Value                    | GET              | `/v1/scheduling/employee_timeoff/symbolic_values`
Scheduling                | Proficiency Levels                                   | Retrieve Proficiency Level by ID                    | GET              | `/v1/scheduling/proficiency_levels/{id}`
Scheduling                | Proficiency Levels                                   | Retrieve Proficiency Level by Name                  | GET              | `/v1/scheduling/proficiency_levels`
Scheduling                | Proficiency Levels                                   | Retrieve Proficiency Levels                         | POST             | `/v1/scheduling/proficiency_levels/multi_read`
Scheduling                | Proficiency Levels                                   | Create Proficiency Level                            | POST             | `/v1/scheduling/proficiency_levels`
Scheduling                | Proficiency Levels                                   | Create Proficiency Levels                           | POST             | `/v1/scheduling/proficiency_levels/multi_create`
Scheduling                | Proficiency Levels                                   | Update Proficiency Level by ID                      | PUT              | `/v1/scheduling/proficiency_levels/{proficiencyLevelId}`
Scheduling                | Proficiency Levels                                   | Update Proficiency Levels                           | POST             | `/v1/scheduling/proficiency_levels/multi_update`
Scheduling                | Proficiency Levels                                   | Delete Proficiency Level by ID                      | DELETE           | `/v1/scheduling/proficiency_levels/{proficiencyLevelId}`
Scheduling                | Proficiency Levels                                   | Delete Proficiency Levels                           | POST             | `/v1/scheduling/proficiency_levels/multi_delete`
Scheduling                | Skills Setup                                         | Retrieve Skill by ID                                | GET              | `/v1/scheduling/skills/{skillId}`
Scheduling                | Skills Setup                                         | Retrieve Skill by Name or All                       | GET              | `/v1/scheduling/skills`
Scheduling                | Skills Setup                                         | Retrieve Skills                                     | POST             | `/v1/scheduling/skills/multi_read`
Scheduling                | Skills Setup                                         | Create Skill                                        | POST             | `/v1/scheduling/skills`
Scheduling                | Skills Setup                                         | Create Skills                                       | POST             | `/v1/scheduling/skills/multi_create`
Scheduling                | Skills Setup                                         | Update Skill by ID                                  | PUT              | `/v1/scheduling/skills/{skillId}`
Scheduling                | Skills Setup                                         | Update Skills                                       | POST             | `/v1/scheduling/skills/multi_update`
Scheduling                | Skills Setup                                         | Delete Skill by ID                                  | DELETE           | `/v1/scheduling/skills/{skillId}`
Scheduling                | Skills Setup                                         | Delete Skills                                       | POST             | `/v1/scheduling/skills/multi_delete`
Scheduling                | Manager Time Off Requests                            | Retrieve Manager Accrual Balance                    | GET              | `/v1/scheduling/timeoff/accruals`
Scheduling                | Manager Time Off Requests                            | Retrieve Manager Request Period                     | GET              | `/v1/scheduling/timeoff/request_periods`
Scheduling                | Manager Time Off Requests                            | Retrieve Manager Request Subtype                    | GET              | `/v1/scheduling/timeoff/request_subtypes`
Scheduling                | Manager Time Off Requests                            | Retrieve Manager Symbolic Value                     | GET              | `/v1/scheduling/timeoff/symbolic_values`

## Dimensions 2.4.0 {#240}

The following operations were added to the API in Dimensions 2.4.0:

Domain                    | Resource                                             | Operation                                           | Method           | URL endpoint
----------------          | ----------------                                     | ----------------                                    | ---------------- | ----------------
People                    | Paycode Value Profile Assignments                    | Retrieve Paycode Value Profile Assignment by ID     | GET              | `/v1/commons/persons/pay_code_value_profiles/{personId}`
People                    | Paycode Value Profile Assignments                    | Retrieve Paycode Value Profile Assignment by Person Number | GET       | `/v1/commons/persons/pay_code_value_profiles`
People                    | Paycode Value Profile Assignments                    | Retrieve All Paycode Value Profile Assignments      | POST             | `/v1/commons/persons/pay_code_value_profiles/multi_read`
People                    | Paycode Value Profile Assignments                    | Update Paycode Value Profile Assignment by ID       | PUT              | `/v1/commons/persons/pay_code_value_profiles/{personId}`
People                    | Paycode Value Profile Assignments                    | Update Paycode Value Profile Assignments            | POST             | `/v1/commons/persons/pay_code_value_profiles/multi_update`
People                    | Paycode Value Profile Assignments                    | Delete Paycode Value Profile Assignment by ID       | DELETE	          | `/v1/commons/persons/pay_code_value_profiles/{personId}`
People                    | Paycode Value Profile Assignments                    | Delete Paycode Value Profile Assignments            | POST             | `/v1/commons/persons/pay_code_value_profiles/multi_delete`	
Scheduling                | Day Type Equivalencies                               | Retrieve Day Type Equivalence by ID                 | GET              | `/v1/scheduling/day_type_equivalences/{id}`
Scheduling                | Day Type Equivalencies                               | Retrieve Day Type Equivalence by Name or All        | GET              | `/v1/scheduling/day_type_equivalences`
Scheduling                | Day Type Equivalencies                               | Retrieve All Day Type Equivalencies                 | POST             | `/v1/scheduling/day_type_equivalences/multi_read`
Scheduling                | Holiday Request Settings                             | Retrieve Holiday Request Setting by ID              | GET              | `/v1/scheduling/holiday_request_settings/{id}`
Scheduling                | Holiday Request Settings                             | Retrieve Holiday Request Settings                   | GET              | `/v1/scheduling/holiday_request_settings`
Scheduling                | Holiday Request Settings                             | Retrieve All Holiday Request Settings               | POST             | `/v1/scheduling/holiday_request_settings/multi_read`
Scheduling                | Symbolic Source Types                                | Retrieve Symbolic Source Type by ID                 | GET              | `/v1/scheduling/symbolic_source_types/{id}`
Scheduling                | Symbolic Source Types                                | Retrieve Symbolic Source Types by Name or All       | GET              | `/v1/scheduling/symbolic_source_types`
Scheduling                | Symbolic Source Types                                | Retrieve All Symbolic Source Types                  | POST             | `/v1/scheduling/symbolic_source_types/multi_read`

## Dimensions 2.3.0 {#230}

The following operation was added to the API in Dimensions 2.3.0:

Domain           | Resource                      | Operation                     | Method           | URL endpoint
---------------- | ----------------              | ----------------              | ---------------- | ----------------
Scheduling       | Workload Generator            | Generate a Workload           | POST             | `/v1/scheduling/workload_generator/apply_update`

## Dimensions 2.2.0 {#220}

The following operations were added to the API in Dimensions 2.2.0:

Domain                    | Resource                                             | Operation                                           | Method           | URL endpoint
----------------          | ----------------                                     | ----------------                                    | ---------------- | ----------------
People                    | Certification Assignments                            | Retrieve Certification Assignments by ID            | GET              | `/v1/commons/persons/certifications/{personId}`
People                    | Certification Assignments                            | Retrieve Certification Assignments by Person Number | GET              | `/v1/commons/persons/certifications`
People                    | Certification Assignments                            | Retrieve All Certification Assignments              | POST             | `/v1/commons/persons/certifications/multi_read`
People                    | Certification Assignments                            | Update Certification Assignment by ID               | PUT              | `/v1/commons/persons/certifications/{personId}`
People                    | Certification Assignments                            | Update Certification Assignments                    | POST             | `/v1/commons/persons/certifications/multi_upsert`
People                    | Skill Assignments                                    | Retrieve Skill Assignments by ID                    | GET              | `/v1/commons/persons/skills/{personId}`
People                    | Skill Assignments                                    | Retrieve Skill Assignments by Person Number         | GET              | `/v1/commons/persons/skills`
People                    | Skill Assignments                                    | Retrieve All Skill Assignments                      | POST             | `/v1/commons/persons/skills/multi_read`
People                    | Skill Assignments                                    | Update Skill Assignment by ID                       | PUT              | `/v1/commons/persons/skills/{personId}`
People                    | Skill Assignments                                    | Update Skill Assignments                            | POST             | `/v1/commons/persons/skills/multi_upsert`	

## Dimensions 2.0.0 {#200}

The following operations were added to the API in Dimensions 2.0.0:

Domain                    | Resource                                             | Operation                         | Method           | URL endpoint
----------------          | ----------------                                     | ----------------                  | ---------------- | ----------------
People                    | Person Assignments > Attestation Profile Assignments | Retrieve All Attestation Profiles | GET              | `/v1/commons/persons/{person_id}/attestation_profile_assignments`
People                    | Person Assignments > Attestation Profile Assignments | Assign Attestation Profile        | POST             | `/v1/commons/persons/{person_id}/attestation_profile_assignments`
People                    | Person Assignments > Attestation Profile Assignments | Retrieve All Attestation Profiles by Person Number   | GET              | `/v1/commons/persons/attestation_profile_assignments`
People                    | Person Assignments > Attestation Profile Assignments | Assign Attestation Profile by Person Number          | POST             | `/v1/commons/persons/attestation_profile_assignments`
Scheduling                | Employee Swap Requests                               | Retrieve Shift Swap Request by ID | GET              | `/v1/scheduling/employee_swap/{swapRequestId}`
Scheduling                | Employee Swap Requests                               | Create Shift Swap Request         | POST             | `/v1/scheduling/employee_swap`
Scheduling                | Employee Swap Requests                               | Retrieve Shift Swap Request Information              | POST             | `/v1/scheduling/employee_swap/apply_read`
Scheduling                | Employee Swap Requests                               | Retrieve Shift Swap Requests      | POST             | `/v1/scheduling/employee_swap/multi_read`
Scheduling                | Employee Swap Requests                               | Update Shift Swap Request         | POST             | `/v1/scheduling/employee_swap/apply_update`
Scheduling                | Manager Swap Requests                                | Retrieve Shift Swap Request by ID as Manager         | GET              | `/v1/scheduling/manager_swap/{swapRequestId}`
Scheduling                | Manager Swap Requests                                | Retrieve Rule Violations for Shift Swap Request      | POST             | `/v1/scheduling/manager_swap/apply_read`
Scheduling                | Manager Swap Requests                                | Retrieve Shift Swap Requests as Manager              | POST             | `/v1/scheduling/manager_swap/multi_read`
Scheduling                | Manager Swap Requests                                | Update Shift Swap Request as Manager                 | POST             | `/v1/scheduling/manager_swap/apply_update`
Timekeeping               | Attestation Assignments                              | Retrieve All Attestation Assignments                 | GET              | `/v1/timekeeping/attestation_assignments`
Timekeeping               | Attestation Assignments                              | Create Attestation Assignment                        | POST             | `/v1/timekeeping/attestation_assignments`
Timekeeping               | Attestation Assignments                              | Retrieve Attestation Assignment by ID                | GET              | `/v1/timekeeping/attestation_assignments/{id}`
Timekeeping               | Attestation Assignments                              | Update Attestation Assignment by ID                  | PUT              | `/v1/timekeeping/attestation_assignments/{id}`
Timekeeping               | Attestation Assignments                              | Delete Attestation Assignment by ID                  | DELETE           | `/v1/timekeeping/attestation_assignments/{id}`
Timekeeping               | Attestation Buttons                                  | Retrieve All Attestation Buttons                     | GET              | `/v1/timekeeping/attestation_buttons`
Timekeeping               | Attestation Buttons                                  | Create Attestation Button                            | POST             | `/v1/timekeeping/attestation_buttons`
Timekeeping               | Attestation Buttons                                  | Retrieve Attestation Button by ID                    | GET              | `/v1/timekeeping/attestation_buttons/{id}`
Timekeeping               | Attestation Buttons                                  | Update Attestation Button by ID                      | PUT              | `/v1/timekeeping/attestation_buttons/{id}`
Timekeeping               | Attestation Buttons                                  | Delete Attestation Button by ID                      | DELETE           | `/v1/timekeeping/attestation_buttons/{id}`
Timekeeping               | Attestation Daily Details                            | Retrieve Attestation Daily Details                   | POST             | `/v1/timekeeping/attestation/multi_read`
Timekeeping               | Attestation Conditions                               | Retrieve All Attestation Conditions                  | GET              | `/v1/timekeeping/attestation_conditions`
Timekeeping               | Attestation Conditions                               | Create Attestation Condition                         | POST             | `/v1/timekeeping/attestation_conditions`
Timekeeping               | Attestation Conditions                               | Retrieve Attestation Condition by ID                 | GET              | `/v1/timekeeping/attestation_conditions/{id}`
Timekeeping               | Attestation Conditions                               | Update Attestation Condition by ID                   | PUT              | `/v1/timekeeping/attestation_conditions/{id}`
Timekeeping               | Attestation Conditions                               | Delete Attestation Condition by ID                   | DELETE           | `/v1/timekeeping/attestation_conditions/{id}`
Timekeeping               | Attestation Profiles                                 | Retrieve All Attestation Profiles                    | GET              | `/v1/timekeeping/attestation_profiles`
Timekeeping               | Attestation Profiles                                 | Create Attestation Profile                           | POST             | `/v1/timekeeping/attestation_profiles`
Timekeeping               | Attestation Profiles                                 | Retrieve Attestation Profile by ID                   | GET              | `/v1/timekeeping/attestation_profiles/{id}`
Timekeeping               | Attestation Profiles                                 | Update Attestation Profile by ID                     | PUT              | `/v1/timekeeping/attestation_profiles/{id}`
Timekeeping               | Attestation Workflow Attributes                      | Set Attestation Workflow Attributes by ID            | POST             | `/v1/timekeeping/attestation_workflow_attributes/{id}`

## Dimensions 1.12.0 {#1120}

The following operations were added to the API in Dimensions 1.12.0:

Domain           | Resource                      | Operation                                                           | Method           | URL endpoint
---------------- | ----------------              | ----------------                                                    | ---------------- | ----------------
Scheduling       | Workload Volume               | Retrieve Workload Volumes                                           | POST             | `/v1/scheduling/volume/multi_read`
Scheduling       | Workload Volume               | Update Workload Weights or Update, Lock, or Unlock Workload Volumes | POST             | `/v1/scheduling/volume/apply_update`

## Dimensions 1.1.0 {#110}

The following operation was added to the API in Dimensions 1.1.0:

Domain           | Resource                      | Operation                     | Method           | URL endpoint
---------------- | ----------------              | ----------------              | ---------------- | ----------------
Common Resources | Pay Period Timespans          | Retrieve Pay Period Timespans | GET              | `/v1/commons/pay_period`
