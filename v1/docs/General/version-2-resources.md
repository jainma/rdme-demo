---
title: "Version 2 resources and operations"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb662255dd00016e0b208"
---

# Version 2 resources and operations

This topic correlates version 2 resources and operations with the deprecated version 1 resources and operations they replace.

_**Note:** Each API operation lists the Access Control Points (ACPs) associated with that operation._

_**Important Note:** We recommend you update your implementations to utilize version 2 operations as they provide better security, performance, and functionality._

Replacement Operations                                                                                                                                  | Dimensions Release
----------------                                                                                                                                        | ----------------
`GET /v2/commons/notifications replaces GET /v1/commons/notifications`                                                                                  | R9 Update 1
`GET /v2/scheduling/setup/schedule_groups replaces GET /v1/scheduling/setup/schedule_groups`                                                            | R9
`GET /v2/leave/case_statuses` replaces `GET /v1/leave/case_statuses`                                                                                    | R8 Update 3
`GET /v2/timekeeping/setup/accrual_codes` replaces `GET /v1/timekeeping/setup/accrual_codes`                                                            | R8 Update 3
`GET /v2/timekeeping/setup/pay_codes` replaces `GET /v1/timekeeping/setup/pay_codes`                                                                    | R8 Update 3
`GET /v2/timekeeping/setup/employee_pay_codes` replaces `GET /v1/timekeeping/setup/employee_pay_codes`                                                  | R8 Update 3
`GET /v2/timekeeping/setup/employee_pay_codes/{id}` replaces `GET /v1/timekeeping/setup/employee_pay_codes/{id}`                                        | R8 Update 3
`GET /v2/timekeeping/setup/pay_code_symbolic_values` replaces `GET /v1/timekeeping/setup/pay_code_symbolic_values`                                      | R8 Update 3
`GET /v2/timekeeping/setup/employee_pay_code_symbolic_values` replaces `GET /v1/timekeeping/setup/employee_pay_code_symbolic_values`                    | R8 Update 3
`GET /v2/timekeeping/setup/pay_code_symbolic_values/{id}` replaces `GET /v1/timekeeping/setup/pay_code_symbolic_values/{id}`                            | R8 Update 3
`GET /v2/timekeeping/setup/employee_pay_code_symbolic_values/{id}` replaces `GET /v1/timekeeping/setup/employee_pay_code_symbolic_values/{id}`          | R8 Update 3
`GET /v2/timekeeping/setup/payrules` replaces `GET /v1/timekeeping/setup/payrules`                                                                      | R8 Update 3
`POST /v2/timekeeping/setup/payrules` replaces `POST /v1/timekeeping/setup/payrules`                                                                    | R8 Update 3
`GET /v2/timekeeping/setup/employee_work_rules` replaces `GET /v1/timekeeping/setup/employee_work_rules`                                                | R8 Update 3
`GET /v2/timekeeping/setup/employee_work_rules/{id}` replaces `GET /v1/timekeeping/setup/employee_work_rules/{id}`                                      | R8 Update 3
`POST /v2/commons/location_sets/multi_read` replaces `POST /v1/commons/location_sets/multi_read`                                                        | R8 Update 2
`GET /v2/forecasting/forecast_week` replaces `GET /v1/forecasting/forecast_week`                                                                        | R8 Update 2
`GET /v2/forecasting/forecast_week/start_day` replaces `GET /v1/forecasting/forecast_week/start_day`                                                    | R8 Update 2
`POST /v2/forecasting/forecast_week/start_days/multi_read` replaces `POST /v1/forecasting/forecast_week/start_days/multi_read`                          | R8 Update 2
`GET /v2/forecasting/forecast_week/default_start_day` replaces `GET /v1/forecasting/forecast_week/default_start_day`                                    | R8 Update 2
`GET /v2/forecasting/static_drivers` replaces `GET /v1/forecasting/static_drivers`                                                                      | R8 Update 2
`GET /v2/forecasting/static_drivers/{id}` replaces `GET /v1/forecasting/static_drivers/{id}`                                                            | R8 Update 2
`POST /v2/forecasting/volume_forecast/import` replaces `POST /v1/forecasting/volume_forecast/import`                                                    | R8 Update 2
`GET /v2/forecasting/volume_forecast_model_types` replaces `GET /v1/forecasting/volume_forecast_model_types`                                            | R8 Update 2
`GET /v2/forecasting/week_symbolic_periods` replaces `GET /v1/forecasting/week_symbolic_periods`                                                        | R8 Update 2
`GET /v2/forecasting/generic_categories` replaces `GET /v1/forecasting/generic_categories`                                                              | R8 Update 2
`GET /v2/forecasting/generic_categories/{id}` replaces `GET /v1/forecasting/generic_categories/{id}`                                                    | R8 Update 2
`POST /v2/forecasting/generic_categories/multi_read` replaces `POST /v1/forecasting/generic_categories/multi_read`                                      | R8 Update 2
`GET /v2/commons/cost_centers` replaces `GET /v1/commons/cost_centers`                                                                                  | R8 Update 1
`GET /v2/commons/cost_centers/{id}` replaces `GET /v1/commons/cost_centers/{id}`                                                                        | R8 Update 1
`GET /v2/commons/hours_operation` replaces `GET /v1/commons/hours_operation`                                                                            | R8 Update 1
`GET /v2/commons/hours_operation/{id}` replaces `GET /v1/commons/hours_operation/{id}`                                                                  | R8 Update 1
`POST /v2/commons/hours_operation/multi_read` replaces `POST /v1/commons/hours_operation/multi_read`                                                    | R8 Update 1
`POST /v2/commons/hours_operation` replaces `POST /v1/commons/hours_operation`                                                                          | R8 Update 1
`POST /v2/commons/hours_operation/multi_create` replaces `POST /v1/commons/hours_operation/multi_create`                                                | R8 Update 1
`PUT /v2/commons/hours_operation/{id}` replaces `PUT /v1/commons/hours_operation/{id}`                                                                  | R8 Update 1
`POST /v2/commons/hours_operation/multi_update` replaces `POST /v1/commons/hours_operation/multi_update`                                                | R8 Update 1
`DELETE /v2/commons/hours_operation/{id}` replaces `DELETE /v1/commons/hours_operation/{id}`                                                            | R8 Update 1
`POST /v2/commons/hours_operation/multi_delete` replaces `POST /v1/commons/hours_operation/multi_delete`                                                | R8 Update 1
`GET /v2/commons/labor_categories` replaces `GET /v1/commons/labor_categories`                                                                          | R8 Update 1
`GET /v2/commons/labor_categories/{id}` replaces `GET /v1/commons/labor_categories/{id}`                                                                | R8 Update 1
`GET /v2/commons/labor_entries` replaces `GET /v1/commons/labor_entries`                                                                                | R8 Update 1
`GET /v2/commons/labor_entries/{id}` replaces `GET /v1/commons/labor_entries/{id}`                                                                      | R8 Update 1
`GET /v2/commons/persons/minor_rules` replaces `GET /v1/commons/persons/minor_rules`                                                                    | R8 Update 1
`GET /v2/commons/persons/minor_rules/{person_id}` replaces `GET /v1/commons/persons/minor_rules/{person_id}`                                            | R8 Update 1
`PUT /v2/commons/persons/minor_rules/{person_id}` replaces `PUT /v1/commons/persons/minor_rules/{person_id}`                                            | R8 Update 1
`POST /v2/commons/persons/minor_rules/multi_read` replaces `POST /v1/commons/persons/minor_rules/multi_read`                                            | R8 Update 1
`POST /v2/commons/persons/minor_rules/multi_upsert` replaces `POST /v1/commons/persons/minor_rules/multi_upsert`                                        | R8 Update 1
`GET /v2/commons/persons/paycode_value_profiles` replaces `GET /v1/commons/persons/paycode_value_profiles`                                              | R8 Update 1
`GET /v2/commons/persons/paycode_value_profiles/{personId}` replaces `GET /v1/commons/persons/paycode_value_profiles/{personId}`                        | R8 Update 1
`PUT /v2/commons/persons/paycode_value_profiles/{personId}` replaces `PUT /v1/commons/persons/paycode_value_profiles/{personId}`                        | R8 Update 1
`DELETE /v2/commons/persons/paycode_value_profiles/{personId}` replaces `DELETE /v1/commons/persons/paycode_value_profiles/{personId}`                  | R8 Update 1
`POST /v2/commons/persons/paycode_value_profiles/multi_delete` replaces `POST /v1/commons/persons/paycode_value_profiles/multi_delete`                  | R8 Update 1
`POST /v2/commons/persons/paycode_value_profiles/multi_read` replaces `POST /v1/commons/persons/paycode_value_profiles/multi_read`                      | R8 Update 1
`POST /v2/commons/persons/paycode_value_profiles/multi_update` replaces `POST /v1/commons/persons/paycode_value_profiles/multi_update`                  | R8 Update 1
`GET /v2/commons/persons/schedule_rule_overrides/{person_id}` replaces `GET /v1/commons/persons/schedule_rule_overrides/{person_id}`                    | R8 Update 1
`GET /v2/commons/persons/schedule_rule_overrides` replaces `GET /v1/commons/persons/schedule_rule_overrides`                                            | R8 Update 1
`POST /v2/commons/persons/schedule_rule_overrides/multi_read` replaces `POST /v1/commons/persons/schedule_rule_overrides/multi_read`                    | R8 Update 1
`GET /v2/commons/persons/scheduling_employee_preferences` replaces `GET /v1/commons/persons/scheduling_employee_preferences`                            | R8 Update 1
`GET /v2/commons/persons/scheduling_employee_preferences/{personId}` replaces `GET /v1/commons/persons/scheduling_employee_preferences/{personId}`      | R8 Update 1
`POST /v2/commons/persons/scheduling_employee_preferences/multi_read` replaces `POST /v1/commons/persons/scheduling_employee_preferences/multi_read`    | R8 Update 1
`GET /v2/forecasting/labor_forecast_limits` replaces `GET /v1/forecasting/labor_forecast_limits`                                                        | R8 Update 1
`GET /v2/forecasting/labor_forecast_limits/{id}` replaces `GET /v1/forecasting/labor_forecast_limits/{id}`                                              | R8 Update 1
`POST /v2/forecasting/labor_forecast_limits/apply_read` replaces `POST /v1/forecasting/labor_forecast_limits/multi_read`                                | R8 Update 1
`POST /v2/forecasting/labor_forecast_limits` replaces `POST /v1/forecasting/labor_forecast_limits`                                                      | R8 Update 1
`POST /v2/forecasting/labor_forecast_limits/multi_create` replaces `POST /v1/forecasting/labor_forecast_limits/multi_create`                            | R8 Update 1
`PUT /v2/forecasting/labor_forecast_limits/{id}` replaces `PUT /v1/forecasting/labor_forecast_limits/{id}`                                              | R8 Update 1
`POST /v2/forecasting/labor_forecast_limits/multi_update` replaces `POST /v1/forecasting/labor_forecast_limits/multi_update`                            | R8 Update 1
`DELETE /v2/forecasting/labor_forecast_limits/{id}` replaces `DELETE /v1/forecasting/labor_forecast_limits/{id}`                                        | R8 Update 1
`POST /v2/forecasting/labor_forecast_limits/multi_delete` replaces `POST /v1/forecasting/labor_forecast_limits/multi_delete`                            | R8 Update 1
`POST /v2/forecasting/labor_standard_tasks/import` replaces `POST /v1/forecasting/labor_standard_tasks/import`                                          | R8 Update 1
`POST /v2/forecasting/labor_standard_tasks/purge` replaces `POST /v1/forecasting/labor_standard_tasks/purge`                                            | R8 Update 1
`GET /v2/forecasting/tasks` replaces `GET /v1/forecasting/tasks`                                                                                        | R8 Update 1
`GET /v2/forecasting/tasks/{id}` replaces `GET /v1/forecasting/tasks/{id}`                                                                              | R8 Update 1
`POST /v2/forecasting/tasks/multi_read` replaces `POST /v1/forecasting/tasks/multi_read`                                                                | R8 Update 1
`POST /v2/forecasting/tasks` replaces `POST /v1/forecasting/tasks`                                                                                      | R8 Update 1
`POST /v2/forecasting/tasks/multi_create` replaces `POST /v1/forecasting/tasks/multi_create`                                                            | R8 Update 1
`PUT /v2/forecasting/tasks/{id}` replaces `PUT /v1/forecasting/tasks/{id}`                                                                              | R8 Update 1
`POST /v2/forecasting/tasks/multi_update` replaces `POST /v1/forecasting/tasks/multi_update`                                                            | R8 Update 1
`DELETE /v2/forecasting/tasks/{id}` replaces `DELETE /v1/forecasting/tasks/{id}`                                                                        | R8 Update 1
`POST /v2/forecasting/tasks/multi_delete` replaces `POST /v1/forecasting/tasks/multi_delete`                                                            | R8 Update 1
`GET /v2/forecasting/task_groups` replaces `GET /v1/forecasting/task_groups`                                                                            | R8 Update 1
`GET /v2/forecasting/task_groups/{id}` replaces `GET /v1/forecasting/task_groups/{id}`                                                                  | R8 Update 1
`POST /v2/forecasting/task_groups/multi_read` replaces `POST /v1/forecasting/task_groups/multi_read`                                                    | R8 Update 1
`POST /v2/forecasting/task_groups` replaces `POST /v1/forecasting/task_groups`                                                                          | R8 Update 1
`POST /v2/forecasting/task_groups/multi_create` replaces `POST /v1/forecasting/task_groups/multi_create`                                                | R8 Update 1
`PUT /v2/forecasting/task_groups/{id}` replaces `PUT /v1/forecasting/task_groups/{id}`                                                                  | R8 Update 1
`POST /v2/forecasting/task_groups/multi_update` replaces `POST /v1/forecasting/task_groups/multi_update`                                                | R8 Update 1
`DELETE /v2/forecasting/task_groups/{id}` replaces `DELETE /v1/forecasting/task_groups/{id}`                                                            | R8 Update 1
`POST /v2/forecasting/task_groups/multi_delete` replaces `POST /v1/forecasting/task_groups/multi_delete`                                                | R8 Update 1
`GET /v2/timekeeping/setup/accrual_profiles/{id}` replaces `GET /v1/timekeeping/setup/accrual_profiles/{id}`                                            | R8 Update 1
`GET /v2/timekeeping/setup/accrual_profiles` replaces `GET /v1/timekeeping/setup/accrual_profiles`                                                      | R8 Update 1
`GET /v2/timekeeping/setup/deduct_rules/{id}` replaces `GET /v1/timekeeping/setup/deduct_rules/{id}`                                                    | R8 Update 1
`GET /v2/timekeeping/setup/deduct_rules` replaces `GET /v1/timekeeping/setup/deduct_rules`                                                              | R8 Update 1
`GET /v2/timekeeping/setup/employee_pay_codes/{id}` replaces `GET /v1/timekeeping/setup/employee_pay_codes/{id}`                                        | R8 Update 1
`GET /v2/timekeeping/setup/employee_pay_codes` replaces `GET /v1/timekeeping/setup/employee_pay_codes`                                                  | R8 Update 1
`GET /v2/timekeeping/setup/employment_terms/{id}` replaces `GET /v1/timekeeping/setup/employment_terms/{id}`                                            | R8 Update 1
`GET /v2/timekeeping/setup/employment_terms` replaces `GET /v1/timekeeping/setup/employment_terms`                                                      | R8 Update 1
`GET /v2/timekeeping/setup/work_rules/{id}` replaces `GET /v1/timekeeping/setup/work_rules/{id}`                                                        | R8 Update 1
`GET /v2/timekeeping/setup/work_rules` replaces `GET /v1/timekeeping/setup/work_rules`                                                                  | R8 Update 1