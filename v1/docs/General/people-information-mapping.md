---
title: "People Editor Cross-Reference"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb662255dd00016e0b208"
---

# People Editor Cross-Reference

The following fields in the People Information editor are listed in the order they appear in the Dimensions UI and are mapped to the request payload properties that correspond to each field. If a field is read-only and only appears in an API response body, that detail is noted below in the Notes column.

## Contents

* [Summary](#summary)
* [Employee > Information](#employee-information)
* [Employee > Contacts](#employee-contacts)
* [Employee > Additional Information](#employee-additional-information)
* [Employee > Person's Dates](#employee-person-dates)
* [Employee > Process Profiles](#employee-process-profiles)
* [Employee > Access Profiles](#employee-access-profiles)
* [Assignments > Multiple Assignments](#assignments-multiple-assignments)
* [Timekeeping > Approvals & Reviewers](#timekeeping-approvals-reviewers)
* [Timekeeping > Timekeeper](#timekeeping-timekeeper)
* [Timekeeping > Employee Role](#timekeeping-employee-role)
* [Activities > Activities](#activities-activities)
* [Activities > Defaults](#activities-defaults)
* [Scheduling > Skills & Certifications](#scheduling-skills-certs)
* [Scheduling > Scheduler](#scheduling-scheduler)
* [Scheduling > Employee Preferences](#scheduling-employee-preferences)
* [Scheduling > Schedule Rule Overrides](#scheduling-schedule-rule-overrides)
* [Accruals > Accruals Information](#accruals-info)
* [Leave > Leave Information](#leave-info)
* [Attendance > Attendance Information](#attendance-info)
* [Devices > Biometrics](#devices-biometrics)
* [Devices > TeleTime IP](#devices-teletime-ip)
* [Devices > Device Information](#devices-device-information)

## Summary {#summary}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Employee > Employment Status                                  | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `employmentStatusList` > `employmentStatusName`        | Active, Inactive, Terminated; Alphanumeric (30)
Employee > Analytics Labor Type                               | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `analyticsLaborTypeList` > `analyticsLaborTypeName`    | 
Employee > Hire Date                                          | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `hireDate`                                  | 
Employee > Accruals Profile                                   | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `accrualProfileName`                        | 
Primary Job Information > Primary Job                         | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `primaryLaborAccounts` > `organizationPath`                | 
Primary Job Information > Primary Labor Category              | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `primaryLaborAccounts` > `laborCategoryName`               | 
Primary Job Information > Time Zone                           | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `timeZoneName`                    | Alphanumeric (30)
Devices > Device Group                                        | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `deviceGroupName`                 | 
Devices > Current Badge Number                                | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `badgeAssignments` > `badgeNumber`                     | Numeric 0-9 (10)
Scheduler > Schedule Group                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleGroup` > `assignments` > `scheduleGroup`                  | The Schedule Group Name can also be set using *Create Person* (`POST /v1/commons/persons`) `jobAssignment` > `scheduleGroupName`, but not the start or end dates
Scheduler > Current Skills                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `skills` > `assignments` > `skill`                                 |
Scheduler > Current Certifications                            | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `certification`                 |
Scheduler > Schedule Rule Set                                 | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleRuleSet` > `scheduleRuleSetAssignments` > `ruleSet`       |
Scheduler > Preferred Zone Category                           | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleEmployeePreference` > `zoneCategory`                | 
Scheduler > Preferred Zone                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleEmployeePreference` > `zone`                        | 
User Details > Username                                       | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `userName`                                          | Alphanumeric (50)
User Details > Account Status                                 | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `userAccountStatusList` > `userAccountStatusName`      | Active, Inactive, Terminated
User Details > Last Password Change (Date-Time)               | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `passwordUpdatedDateTime`                           | Read-only
User Details > Account is Locked                              | *N/A*                                        | *N/A*                                                                        | Boolean, Read-only
User Details > Email                                          | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `emailAddresses` > `address`                           |
User Details > Locale Policy                                  | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `localePolicyName`                |
User Details > Only Custom Data Field                         | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `customDataList` > `customDataTypeName`                | Each paired with `customDataList` > `text` in an array 
Timekeeping > Base Wage                                       | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `baseWageRates` > `hourlyRate`                             |
Timekeeping > Pay Rule                                        | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `payRuleName`                     | 
Timekeeping > Assigned Currency                               | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `employeeCurrencyAssignment` > `currencyCode`          |

## Employee > Information {#employee-information}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Last Name                                                     | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `lastName`                                  | Alphanumeric (30)
First Name                                                    | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `firstName`                                 | Alphanumeric (30)
ID                                                            | *N/A - System Assigned*                      | *N/A - System Assigned*                                                      | You cannot assign the person ID 
Birth Date                                                    | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `birthDate`                                 | Employee's birth date
Hire Date                                                     | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `hireDate`                                  | Employee's original date of hire
Middle Name                                                   | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `middleInitial`                             | The UI field labeled "Middle Name" stores a person's middle initial; Alphanumeric (1)
Short Name                                                    | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `shortName`                                 | Alphanumeric (20)
Employee Status > Employment Status                           | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `employmentStatusList` > `employmentStatusName`        | Active, Inactive, Terminated; Alphanumeric (30)
Employee Status > Effective Date                              | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `employmentStatusList` > `effectiveDate`               | 
Username                                                      | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `userName`                                          | Alphanumeric (50)
Logon Profile                                                 | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `logonProfileName`                                  | 
Authentication Type                                           | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `personAuthenticationTypes` > `authenticationTypeName` | 
Password                                                      | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `userPassword`                                      | Alphanumeric (35)
Last Password Change (Date-Time)                              | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `passwordUpdatedDateTime`                           | Read-only
Last Password Change > Require Password Change at Next Logon  | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `passwordUpdateFlag`                                | Boolean
Last Password Change > Account Locked                         | *N/A*                                        | *N/A*                                                                        | Boolean, Read-only
Last Password Change > Clock Only User                        | *Create Person* (`POST /v1/commons/persons`) | `user` > `userAccount` > `clockOnlyUser`                                     | Boolean
User Account Status                                           | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `userAccountStatusList` > `userAccountStatusName`      | Active, Inactive, Terminated
User Account Status Effective Date                            | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `userAccountStatusList` > `effectiveDate`              | 
Primary Job                                                   | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `primaryLaborAccounts` > `organizationPath`                | 
Primary Job Category                                          | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `primaryLaborAccounts` > `laborCategoryName`               | 
Primary Job Effective Date                                    | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `primaryLaborAccounts` > `effectiveDate`                   | 
Signed Off Date                                               | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `managerSignoffThruDateTime`                | Read-only
Show Primary Job Name > Current Name or When Job was Assigned | *N/A*                                        | *N/A*                                                                        | Not accessible via the API
Time Zone                                                     | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `timeZoneName`                    | Alphanumeric (30)
Reports To                                                    | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `supervisorName`                  | 
Seniority Date                                                | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `seniorityRankDate`               | 
Analytics Labor Type                                          | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `analyticsLaborTypeList` > `analyticsLaborTypeName`    | 
Analytics Labor Type Effective Date                           | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `analyticsLaborTypeList` > `effectiveDate`             | 

## Employee > Contacts {#employee-contacts}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Address                                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `postalAddresses` > `street`                           | Alphanumeric (100)
City                                                          | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `postalAddresses` > `city`                             | Alphanumeric (25)
State/Province                                                | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `postalAddresses` > `state`                            | Alphanumeric (25)
Zip Code                                                      | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `postalAddresses` > `postalCode`                       | Alphanumeric (25)
Country                                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `postalAddresses` > `country`                          | Alphanumeric (25)
Email                                                         | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `emailAddresses` > `address`                           | Alphanumeric (35)
Phone 1                                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `telephoneNumbers` > `phoneNumber`                     | This array accepts multiple phone numbers; Alphanumeric (35)
Phone 2                                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `telephoneNumbers` > `phoneNumber`                     | This array accepts multiple phone numbers; Alphanumeric (35)
Phone 3                                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `telephoneNumbers` > `phoneNumber`                     | This array accepts multiple phone numbers; Alphanumeric (35)

## Employee > Additional Information {#employee-additional-information}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Custom Data Fields                                            | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `customDataList` > `customDataTypeName`                | Each paired with `customDataList` > `text` in an array; Alphanumeric (80)
KnowledgePass Learning Path                                   | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `kpassAccount` > `learningPath`                        |
Restricted User                                               | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `kpassAccount` > `isRestrictedUser`                    | Boolean

## Employee > Person's Dates {#employee-person-dates}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Date Name                                                     | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `customDateList` > `customDateTypeName`                | Associated with `positionCustomDates` > `customDateTypeName`
Description                                                   | *N/A - See Note*                             | *N/A - See Note*                                                             | The system only returns overridden dates
Default Date                                                  | *N/A - See Note*                             | *N/A - See Note*                                                             | The system only returns overridden dates
Override Date                                                 | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `customDateList` > `date`                              | Associated with `positionCustomDates` > `date`

## Employee > Process Profiles {#employee-process-profiles}

People Information                                            | API Operation                                                                     | API Property                                   | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                  | ----------------                               | ----------------
Employee Profile                                              | *Retrieve Person by Extension* (`GET /v1/commons/persons/{extensionType}`)        | `employeeExtension` > `processEmployeeProfile` | 

## Employee > Access Profiles {#employee-access-profiles}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Function Access Profile                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `accessProfileName`               |
Display Profile                                               | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `preferenceProfileName`           |
Locale Policy                                                 | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `localePolicyName`                |
Notification Profile                                          | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `notificationProfileName`         |
Access Method Profile                                         | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `accessMethodProfileName`         |

## Timekeeping > Approvals & Reviewers {#timekeeping-approvals-reviewers}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Reviewer List Assignments > Reviewer Override                 | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `purposeAssignments` > `purpose`                       |
Reviewer List Assignments > Reviewer List                     | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `purposeAssignments` > `requestReviewerList`           |
Overtime Approvals > Approval Level                           | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `approverList` > `approveLevel`                        |
Overtime Approvals > Overtime Approver                        | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `approverList` > `fullName`                            |
Overtime Approvals > Approve Within (D)                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `approverList` > `dueDateAmount`                       |

## Timekeeping > Timekeeper {#timekeeping-timekeeper}

People Information                                            | API Operation                                | API Property                                                                                                                                                       | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                                                                                                                   | ----------------
Employment Terms                                              | *Create Person* (`POST /v1/commons/persons`) | `positions` > `employmentTermAssignments` > `name`                                                                                                                 |
(Employment Terms) Start Date                                 | *Create Person* (`POST /v1/commons/persons`) | `positions` > `employmentTermAssignments` > `startDate`                                                                                                            |
(Employment Terms) End Date                                   | *Create Person* (`POST /v1/commons/persons`) | `positions` > `employmentTermAssignments` > `endDate`                                                                                                              |
Pay Rule                                                      | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `payRuleName`                                                                                                           | 
(Pay Rule) Effective Date                                     | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `payRuleEffectiveDate`                                                                                                  | 
Assigned Currency                                             | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `employeeCurrencyAssignment` > `currencyCode`                                                                                                |
Base Wage                                                     | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `baseWageRates` > `hourlyRate`                                                                                                                   | 
(Base Wage) Effective Date                                    | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `baseWageRates` > `effectiveDate`                                                                                                                | 
Overtime Rules displayed as of (Date)                         | *N/A*                                        | *N/A*                                                                                                                                                              | 
Reset Interval                                                | *N/A - See Note*                             | *N/A - See Note*                                                                                                                                                   | Personal Overtime is often based on scheduled hours and overtime limits are set when an employee is scheduled.
Overtime Rule                                                 | *N/A - See Note*                             | *N/A - See Note*                                                                                                                                                   | Personal Overtime is often based on scheduled hours and overtime limits are set when an employee is scheduled.
Overtime Personal Rule                                        | *N/A - See Note*                             | *N/A - See Note*                                                                                                                                                   | Personal Overtime is often based on scheduled hours and overtime limits are set when an employee is scheduled.
(Overtime) Effective Date                                     | *N/A - See Note*                             | *N/A - See Note*                                                                                                                                                   | Personal Overtime is often based on scheduled hours and overtime limits are set when an employee is scheduled.
Percentage Allocation Rule                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `percentageAllocationRule` > `assignments` > `processor`                                 |
(Percentage Allocation Rule) Effective Date                   | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `percentageAllocationRule` > `assignments` > `effectiveDate`                             |
Adjustment Rule                                               | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `adjustmentRule` > `assignments` > `processor`                                           |
(Adjustment Rule) Effective Date                              | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `adjustmentRule` > `assignments` > `effectiveDate`                                       |
Paycode Values Profile                                        | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `payCodeValue` > `payCodeValueProfile`                                                   |

## Timekeeping > Employee Role {#timekeeping-employee-role}

People Information                                            | API Operation                                | API Property                                                                                                      | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                                                                  | ----------------
Time Entry Method                                             | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `effectiveDatedTimeEntryMethods` > `timeEntryTypeName`                 |
Activity Tracking Status                                      | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `effectiveDatedTimeEntryMethods` > `timeEntryActivityTrackingStatus`   |
(Time Entry Method) Effective Date                            | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `effectiveDatedTimeEntryMethods` > `effectiveDate`                     |
Paycodes "Edit" Profile                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `professionalPayCodeName`                                              |
Work Rule Profile                                             | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `professionalWorkRuleName`                                             |
Labor Category Profile                                        | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `employeeLaborCategoryProfileName`                                     |
Labor Category Profile - Manager Additions                    | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `mgrEmplLaborCategoryProfileName`                                      |
Approval Method                                               | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `accessAssignment` > `approvalMethodName`                                                   |
Attestation Profile                                           | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `attestationProfile` > `attestationProfileAssignments` > `profile`                       |
(Attestation Profile) Effective Date                          | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `attestationProfile` > `attestationProfileAssignments` > `effectiveDate`                 |
Employee Job Transfer Set                                     | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `personAccessAssignments` > `professionalTransferOrganizationSetName`                                                                        |
Manager Additions                                             | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `personAccessAssignments` > `empMgrTransferOrganizationSetName`                                                                              |
(Employee Job Transfer Set) Effective Date                    | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `personAccessAssignments` > `professionalTransferOrganizationSetEffectiveDate`                                                               |
Override Wage & Work Rules                                    | *N/A*                                        | *N/A*                                                                                                             | 
Selected Job Transfer Set                                     | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 
(Selected Job Transfer Set) As of (Date)                      | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 
Location                                                      | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 
Job                                                           | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 
Seniority Date                                                | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 
Job Preference                                                | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 
Scheduling Context                                            | *N/A - This is a display function only*      | *N/A - This is a display function only*                                                                           | 

## Activities > Activities {#activities-activities}

People Information                                            | API Operation                                                                                   | API Property                                                                              | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                                | ----------------                                                                          | ----------------
Activity Profile                                              | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `profileName`                                      | 

## Activities > Defaults {#activities-defaults}

People Information                                            | API Operation                                                                                   | API Property                                                                              | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                                | ----------------                                                                          | ----------------
Default Activity                                              | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `defaultActivityName`                              | 
Current List Query                                            | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `currentListQueryName`                             | 
Idle Time                                                     | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `idleActivityName`                                 | 
Meal                                                          | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `unpaidActivityName`                               | 
Paid Break                                                    | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `paidActivityName`                                 | 
Auto Resolve                                                  | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `workEmployee` > `autoResolveActivityName`                          | 

## Scheduling > Skills & Certifications {#scheduling-skills-certs}

People Information                                            | API Operation                                                                                   | API Property                                                                              | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                                | ----------------                                                                          | ----------------
Skills                                                        | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `skills` > `assignments` > `skill`                                 |
(Skills) Display Name                                         | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `skills` > `assignments` > `skill`                                 |
(Skills) Proficiency Level                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `skills` > `assignments` > `proficiencyLevel`                      |
(Skills) Status                                               | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `skills` > `assignments` > `active`                                |
(Skills) Effective Date                                       | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `skills` > `assignments` > `active`                                |
Certification                                                 | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `certification`                 |
(Certification) Display Name                                  | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `certification`                 |
(Certification) Number                                        | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `certification`                 |
(Certification) Proficiency Level                             | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `proficiencyLevel`              |
(Certification) Grant Date                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `effectiveDate`                 |
(Certification) Expiration Date                               | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `certifications` > `assignments` > `expirationDate`                |

## Scheduling > Scheduler {#scheduling-scheduler}

People Information                                            | API Operation                                                                                   | API Property                                                                              | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                                | ----------------                                                                          | ----------------
Worker Type                                                   | *Create Person* (`POST /v1/commons/persons`)                                                    | `jobAssignment` > `jobAssignmentDetails` > `workerTypeName`                               | Alphanumeric (50)
(Standard Hours) Daily                                        | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `expectedHoursList` > `timePeriodTypeName`                          | The value passed is `Daily`
(Standard Hours) Weekly                                       | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `expectedHoursList` > `timePeriodTypeName`                          | The value passed is `Weekly`
(Standard Hours) Per Pay Period                               | *Create Person* (`POST /v1/commons/persons`)                                                    | `personInformation` > `expectedHoursList` > `timePeriodTypeName`                          | The value passed is `Pay Period`
Group Assignment                                              | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleGroup` > `assignments` > `scheduleGroup`                  | The Schedule Group Name can also be set using *Create Person* (`POST /v1/commons/persons`) `jobAssignment` > `scheduleGroupName`, but not the start or end dates
(Group Assignment) Start Date                                 | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleGroup` > `assignments` > `effectiveDate`                  |
(Group Assignment) End Date                                   | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleGroup` > `assignments` > `expirationDate`                 |
Schedule Rule Set                                             | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleRuleSet` > `scheduleRuleSetAssignments` > `ruleSet`       |
(Schedule Rule Set) Effective Date                            | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `scheduleRuleSet` > `scheduleRuleSetAssignments` > `effectiveDate` |
Process Predictive Scheduling Changes                         | *Create Person* (`POST /v1/commons/persons`)                                                    | `jobAssignment` > `predictiveSchedulingEligibilityList` > `isEligible`                    | Boolean
(Process Predictive Scheduling Changes) Effective Date        | *Create Person* (`POST /v1/commons/persons`)                                                    | `jobAssignment` > `predictiveSchedulingEligibilityList` > `effectiveDate`                 |
Predictive Scheduling Rule Override                           | *Create Person* (`POST /v1/commons/persons`)                                                    | `jobAssignment` > `predictiveSchedulingRuleOverrideList` > `predictiveSchedulingRule`     |
(Predictive Scheduling Rule Override) Effective Date          | *Create Person* (`POST /v1/commons/persons`)                                                    | `jobAssignment` > `predictiveSchedulingRuleOverrideList` > `effectiveDate`                |
Minors > Minor Rule Set                                       | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `minorRule` > `minorRule`                                          |
Minors > School Calendar                                      | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `minorRule` > `schoolCalendar`                                     |
Minors > Emancipated Minor                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`)  | `personAssignments`  > `minorRule` > `emancipatedMinor`                                   | Boolean

## Scheduling > Employee Preferences {#scheduling-employee-preferences}

People Information                                            | API Operation                                                                                  | API Property                                                                        | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                               | ----------------                                                                    | ----------------
Override Employee Preferences in Schedule Generation Strategy | *N/A*                                                                                          | *N/A*                                                                               | 
Preference                                                    | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleEmployeePreference`                                 | 
(Preference) Weight                                           | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleEmployeePreference`                                 | 
Preferred Zone Category                                       | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleEmployeePreference` > `zoneCategory`                | 
Preferred Zone                                                | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleEmployeePreference` > `zone`                        | 

## Scheduling > Schedule Rule Overrides {#scheduling-schedule-rule-overrides}

People Information                                            | API Operation                                                                                  | API Property                                                                        | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                               | ----------------                                                                    | ----------------
Schedule Rules                                                | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleRuleOverrides` > `overrideRules`                    | 
(Schedule Rules) Values                                       | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleRuleOverrides` > `overrideDetails` > `value`        | 
(Schedule Rules) Effective Date                               | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleRuleOverrides` > `overrideRules` > `effectiveDate`  | 
(Schedule Rules) Expiration Date                              | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleRuleOverrides` > `overrideRules` > `expirationDate` | 
(View Audits > Schedule Rule Override Audits) Date            | *N/A*                                                                                          | *N/A*                                                                               | 
(View Audits > Schedule Rule Override Audits) Type            | *N/A*                                                                                          | *N/A*                                                                               | 
(View Audits > Schedule Rule Override Audits) Schedule Rules  | *N/A*                                                                                          | *N/A*                                                                               | 
(View Audits > Schedule Rule Override Audits) Parameter       | *N/A*                                                                                          | *N/A*                                                                               | 
(View Audits > Schedule Rule Override Audits) Old Value       | *N/A*                                                                                          | *N/A*                                                                               | 
(View Audits > Schedule Rule Override Audits) New Value       | *N/A*                                                                                          | *N/A*                                                                               | 
(View Audits > Schedule Rule Override Audits) User            | *N/A*                                                                                          | *N/A*                                                                               | 
Schedule Rule Set Optimization Override                       | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleRuleOverrides` > `overrideRules`                    | 
(Schedule Rule Set Optimization Override) Effective Date      | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `scheduleRuleOverrides` > `overrideRules` > `effectiveDate`  | 

## Accruals > Accruals Information {#accruals-info}

People Information                                            | API Operation                                                                                  | API Property                                                                       | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                               | ----------------                                                                   | ----------------
Accrual Profile                                               | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `accrualProfileName`                              | 
(Accrual Profile) Start Date                                  | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `accrualProfileEffectiveDate`                     | 
(Accrual Profile) End Date                                    | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `accrualProfileEndDate`                           | 
Full-Time Equivalency > Percentage                            | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `fullTimeEquivalencies` > `fullTimePercentage`    | 
Full-Time Equivalency > Employee Hours                        | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `fullTimeEquivalencies` > `employeeStandardHours` | 
Full-Time Equivalency > Full-Time Hours                       | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `fullTimeEquivalencies` > `fullTimeStandardHours` | 
Full-Time Equivalency > Effective Date                        | *Create Person* (`POST /v1/commons/persons`)                                                   | `personInformation` > `person` > `fullTimeEquivalencies` > `effectiveDate`         | 
Cascade Profile                                               | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `cascadeProfile` > `assignmentProfile`                      | 

## Leave > Leave Information {#leave-info}

People Information                                            | API Operation                                                                                  | API Property                                                                                   | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                               | ----------------                                                                               | ----------------
Leave Administrator                                           | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `leaveAdmin` > `administrator`                                          | 
Leave Profile                                                 | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `leaveProfile` > `assignmentProfile`                                    | 

## Attendance > Attendance Information {#attendance-info}

People Information                                            | API Operation                                                                                  | API Property                                                                                   | Notes; Data Type (Max Length)
----------------                                              | ----------------                                                                               | ----------------                                                                               | ----------------
Attendance Administrator                                      | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `attendanceAdmin` > `administrator`                                     | 
Attendance Profile                                            | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `attendanceProfile` > `attendanceProfileAssignments` > `profileName`    | 
(Attendance Profile) Effective Date                           | *Modify Assignments for Multiple People* (`POST /v1/commons/persons/assignments/multi_upsert`) | `personAssignments`  > `attendanceProfile` > `attendanceProfileAssignments` > `effectiveDate`  | 

## Devices > Biometrics {#devices-biometrics}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Finger Scan Biometric Employee                                | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `fingerRequiredFlag`                        | Boolean
Finger Scan Consent Status:                                   | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Finger Scan Enrollment Status:                                | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Finger Scan Consent Details > Consent Date                    | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Finger Scan Consent Details > Location                        | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Finger Scan Consent Details > Finger Scan Consent Form        | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Name                        | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Date                        | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Location                    | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Verification Threshold      | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Content Score               | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Quality Score               | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Verification > Finger > Template Type               | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Name                      | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Date                      | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Location                  | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Verification Threshold    | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Content Score             | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Quality Score             | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Biometric Identification > Finger > Template Type             | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Employee                                       | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `person` > `faceRequiredFlag`                          | Boolean
Face Consent Status                                           | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Enrollment Status:                                       | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Identification > Consent Date                  | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Identification > Enrollment Date               | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Identification > Location                      | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Identification > Verification Threshold        | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Identification > Quality Score                 | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.
Face Biometric Identification > Face Consent Form             | *N/A - See Note*                             | *N/A - See Note*                                                             | This cannot be specified with the API.

## Devices > TeleTime IP {#devices-teletime-ip}

People Information                                            | API Operation                                | API Property                                                                    | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                                | ----------------
TeleTime IP Employee                                          | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `teletimeIPEmployee`                 | Boolean
Require password change at the next TeleTime IP logon         | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `teletimeIPChangePasswordIsRequired` | Boolean
TeleTime IP ID                                                | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `teletimeIPId`                       |
TeleTime IP User Profile                                      | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `teletimeIPProfileName`              |

## Devices > Device Information {#devices-device-information}

People Information                                            | API Operation                                | API Property                                                                 | Notes; Data Type (Max Length)
----------------                                              | ----------------                             | ----------------                                                             | ----------------
Badge Number                                                  | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `badgeAssignments` > `badgeNumber`                     | Numeric 0-9 (10)
Start Date                                                    | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `badgeAssignments` > `effectiveDate`                   | 
Start Time                                                    | *N/A*                                        | *N/A*                                                                        | 
End Date                                                      | *Create Person* (`POST /v1/commons/persons`) | `personInformation` > `badgeAssignments` > `expirationDate`                  | 
End Time                                                      | *N/A*                                        | *N/A*                                                                        | 
Expire the active badge                                       | *N/A*                                        | *N/A*                                                                        | 
Device Group                                                  | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `deviceGroupName`                 |
Individual Profile                                            | *Create Person* (`POST /v1/commons/persons`) | `jobAssignment` > `jobAssignmentDetails` > `deviceProfileName`               |