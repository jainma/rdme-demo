---
title: "Getting started with the Dimensions REST API"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
---

# Getting started with the Dimensions REST API

The Dimensions REST API gives you direct access to the backend powering our array of cloud services, allowing you to extend the Dimensions platform by building your own sophisticated applications.

* [Basic concepts](#BasicConceptsAndOrganization)
	* [A word on CRUD](#CRUD)
* [Pragmatic REST](#PragmaticREST)
* [Anatomy of an API call](#AnatomyOfAnAPICall)
* [Operations](#Operations)
	* [Syntax](#Syntax)
	* [Granularity](#Granularity)
		* [Single entity](#SingleEntity)
		* [Multiple entities](#MultipleEntities)
		* [Levels of aggregation](#LevelsOfAggregation)
	* [Object references](#ObjectReferences)
	* [Concurrency control](#ConcurrencyControl)
	* [Viewing an operation](#OperationView)
* [Resources](#Resources)
* [HTTP headers](#HTTPHeaders)
* [Authentication and Security](#AuthenticationAndSecurity)
* [App keys, client ID, and client secret](#AppKeys)
* [Versioning](#Versioning)
* [HTTP status codes and error handling](#Errors)
* [Asynchronous requests](#AsynchronusRequests)
	* [Asynchronous request flow](#AsynchronusRequestFlow)
* [Internationalization and Localization](#I18NAndL10N)
	* [Standards](#Standards)
	* [Language](#Language)
	* [Currency](#Currency)
	* [Numbers](#Numbers)
	* [Date and time](#DateAndTime)
* [Conventions related to time](#ConventionsRelatedToTime)
	* [Beginning and end of time](#BeginningAndEndOfTime)
	* [Timeframe](#Timeframe)
	* [Effective and expiration dates](#EffectiveAndExpirationDates)
* [Service limits](#ServiceLimits)
* [Throttling](#Throttling)
* [Tracking, logging, and support](#TrackingLoggingSupport)
* [Next steps](#NextSteps)

## Basic concepts and organization {#BasicConceptsAndOrganization}

If you are new to building web-based applications or need a refresher, be sure to familiarize yourself with basic [representational state transfer (REST)](https://en.wikipedia.org/wiki/Representational_State_Transfer) and [Hypertext transfer protocol (HTTP)](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) concepts before continuing, starting with our [Introduction to REST APIs](C:b7eb0c5e-88af-4953-b89c-9b4b68ffa701).

Each functional area within the API is divided into **resources**, each of which represents a business entity that is stored or computed.

* Stored entities include punches, accrual balances, and shifts
* Computed entities include the schedule and the Attendance processor

Each resource is accessed using one or more **operations**, each of which consists of an HTTP method plus a URL. A complete list of operations is available in the API reference documentation. 

* HTTP methods include GET, POST, DELETE, and PUT
* The URL consists of two parts: a root which is unique to your organization and an endpoint representing a resource
* HTTP methods are often described as verbs and URLs as nouns. Like the basic action of an English sentence, the HTTP method, as a verb, represents an action upon an object, or noun, which is represented by the URL

Our REST operations allow arguments to be passed in the URL or request body. Auxiliary data, such as authorization tokens and API version, is passed in HTTP headers. API operations always return the HTTP status, usually return a response body, and sometimes return response headers.

### A word on CRUD {#CRUD}

REST emphasizes CRUD (**C**reate/**R**ead/**U**pdate/**D**elete) operations, mapping them to HTTP verbs:

CRUD operations  | HTTP verbs
---------------- | ----------------
Create           | POST
Read             | GET/POST
Update           | PUT/POST/PATCH
Delete           | DELETE/POST

POST is a catch-all capable of representing any of the CRUD concepts.

GET is read-only and most appropriate for read operations, but there are cases when POST is used for read operations containing very large arguments. 

For updates, PUT represents a total replacement of the resource and PATCH represents a partial update of the resource. 

Non-CRUD operations are undefined in REST. Since any complex API must represent non-CRUD operations, API implementations improvise as needed. 

## Pragmatic REST {#PragmaticREST}

Our REST implementation approaches the real-world challenges facing any large-scale API sensibly and realistically in a way that is based on practical rather than purely theoretical considerations.

* Resources are business entities that are stored or computed
* We provide clear URLs for resources
* Versioning is built in to our architecture
* We do not support [Hypermedia as the Engine of Application State (HATEOAS)](https://en.wikipedia.org/wiki/HATEOAS)
* Verbs in URLs are discouraged and only used when absolutely necessary
* We support [internationalization (I18N)](https://www.w3.org/International/questions/qa-i18n) and [localization (L10N)](https://www.w3.org/International/questions/qa-i18n)
* We support only the [JavaScript Object Notation (JSON)](http://www.json.org/) content type, a conscious decision in line with industry standards and which provides many advantages
* We define extensions for large or complex arguments and operations on sets of data
* Our errors provide both the HTTP status and an error body, which allows for sophisticated error handling
* We support asynchronous operations
* We include a support mechanism via the request correlation ID

Refer to the [Pragmatic REST](C:86106a78-330e-4ebe-b41c-e7a07f27ee0e) topic in the [Overview](C:0df07e3a-7e83-47c8-9ae6-ecf71ce5f4e7) for more information.

## Anatomy of an API call {#AnatomyOfAnAPICall}

1. Your application requests and receives an OAuth token from the authentication server.
2. Your application invokes the API by making a properly-formatted call consisting of an verb (HTTP method) and a noun (API resource in the form of a URL) along with all necessary HTTP headers, parameters, and any required JSON body.
3. Your authorization token is validated.
4. If valid, the Dimensions ecosystem receives and processes your application's API request.
5. Dimensions returns an API response to your application.

## Operations {#Operations}

API operations act on resources, which are business entities that are stored or computed. Each operation consists of an HTTP method plus a URL. A complete list of operations is available in the API reference documentation.

### Syntax and URL form {#Syntax}

The API's syntax is elegant in its simplicity: 
	
*HTTP method + URL*

`GET /v1/commons/persons/210` returns data associated with person number 210

Our URLs are likewise constructed according to a consistent format:
	
*`https://{DNSName}/{major version}/{business domain}/{resource}[/{subresource}]`*

### Granularity {#Granularity}

We support operations that access single or multiple entities in one call. We also support different levels of data aggregation.

#### Single entity {#SingleEntity}

For operations on a single entity, the standard and most RESTful format is used: 

**Format**    
	*HTTP method + URL* 

**Example**    
	`GET /v1/scheduling/schedule` returns the schedule for a single employee, Hyperfind, or location

#### Multiple entities {#MultipleEntities}

For operations on a set of entities, we add an additional verb subresource to the URL:

**Format**    
	*HTTP method + URL* 

**Example**    
	`POST /v1/scheduling/schedule/multi_read` returns the schedule for multiple employees or locations

Note that:

* The HTTP method is usually POST
* Within the URL, the resource is followed by a verb subresource according to the following format:
	
	**multi_{CRUD verb}**    
	CRUD verbs: **create**, **read**, **update**, and **delete**     
	For example:    
	`/v1/attendance/markers/multi_create`    
	`/v1/attendance/markers/multi_delete`    
	`/v1/attendance/markers/multi_read`

* The body consists of a list of individual data items or a set of SQL-like clauses

Refer to the [Pragmatic REST](C:86106a78-330e-4ebe-b41c-e7a07f27ee0e) topic for more information.

#### Levels of aggregation {#LevelsOfAggregation}

Our API supports different levels of data aggregation. 

There is no aggregation at the entity level. For example, we do not aggregate data for operations on individual punches, shifts, leave cases, and so on.

Computed business entities provide an intermediate level of aggregation. Such computed entities include operations on the schedule, the employee_schedule, and so on.

At the far end of the scale lies the Aggregated Data resource, which provides highly customizable, collectively retrievable data from multiple domains simultaneously, including Timekeeping, Scheduling, Attendance, Leave, and KPI data. This resource is part of the Information Access domain, grouped within the Common Resources of our API.

The Aggregated Data resource uses SQL-like clauses that allow for complex constraints, sorting, pagination, and many other options. Refer to the [Information Access](C:38186b1e-324f-426e-919e-3ee82e47e877) overview for more information.

### Object references {#ObjectReferences}

Our API uses object references to encapsulate a reference to an object. An object represents an instance of a business entity.

Object references contain one or at the most two keys identifying the referenced object. This format helps ensure solid API composition, which allows the output of one operation to serve as part or all of the input for another operation without any further processing.

The JSON structure for object reference keys takes the following forms:

* `{"id": "…"}` 
* `{"qualifier": "…"}`
* `{"id": "…", "qualifier": "…"}`

Refer to the [Object references](C:3aeac7eb-3330-46ba-8606-ab4d269afc91) topic for more information.

### Concurrency control {#ConcurrencyControl}

Several client requests may attempt to act upon a single resource at the same time, or concurrently. Each of these several clients as well as the server may have different records of the resource's state. The API solves this dilemma using concurrency control and optimistic locking.

Concurrency control is accomplished at the entity level using a field called `versionCount`, which allows support for optimistic locking.

A request that performs a concurrent write operation returns an HTTP status of 409 if the conditions for optimistic locking are not met. Refer to the [HTTP status codes and error handling](C:ab842096-366f-496f-a471-e73ac58b8540) topic for more information.

### Viewing an operation {#OperationView}

When you navigate to a specific operation against an API resource, the name, HTTP method, and URL appear at the top of the pane. These are followed by a text description of the operation and a number of possible subsections, such as **Query Parameters** or **Resource Details**. 

A wealth of information is available when viewing an operation. Refer to the [Viewing an operation](C:b7eafb85-0dc7-40dd-a79c-53ef6aa5ad40) topic for more information.

## Resources {#Resources}

Resources are business entities that are stored or computed. 

Resources in the URL appear in lower [snake case](https://en.wikipedia.org/wiki/Snake_case): balance_resets, balance_expirations, discipline_levels.

Subresources are used sparingly:

* To group related business entities
* As action names for operations that are not defined in CRUD
	* GET is used for operations with no effect on the server, such as a computation
	* POST is used for operations that change data or when arguments are large or complex

Resources are normally part of collections that represent multiple instances of the same business entity.

* The name is plural, with only a few rare exceptions: Accrual Balances, Shifts, Punches
* Individual members are accessed by ID:     
	`/v1/scheduling/schedule/shifts/{shiftId}`
	* Or, optionally, they may be accessed by query parameter:     
		`{key name}={value}`

Our search, sort, and paging parameters follow common paradigms. For example:

* **GET**
	***short form***
	**field1**=value&…**field2**=value + optional *sort*/*by*/*index*/*count*:
	/v1/scheduling/shifts?from=01/20/2015&to=05/20/2015&*sort*=ascending&*by*=name&*index*=0&*count*=20
	***long form***
	*where*/*sort*/*by*/*index*/*count*:
	/v1/scheduling/shifts?*where*="from=01/20/2015 and to=05/20/2015"&*sort*=ascending&*by*=name&*index*=0&*count*=20

Query parameters where the name of a field equals a value. We have specialized keys--sort, by, index, and count--which allow you to order by specified criteria and paginate. We also include a longer form that provides a more complex search method which uses keys that are similar to SQL clauses.

* **POST**
	SQL-like clauses: *where/from/sort/by/index/count*

## HTTP headers {#HTTPHeaders}

Our API supports a variety of [HTTP headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields).

Refer to the [HTTP headers](C:4dc8ebe0-067a-4a90-b82d-6f4692bdd534) topic for more information.

## Authentication and Security {#AuthenticationAndSecurity}

Requests against the Dimensions API must be authenticated and made over HTTPS. If these requirements are not met, the request fails.

Our API's authentication is built on the OAuth 2.0 standard. Each API request must include an HTTP Authorization header containing an OAuth 2.0 access token.

Successful token requests generate an access token and a refresh token. The access token is usable from the moment it is generated until the number of seconds defined by `expires_in` elapses. The refresh token can be used to generate new access tokens and refresh tokens until the session expires. Refresh tokens expire after a much longer period of time.

Refer to the [Authentication and Security](C:a4943b5b-f44d-4eab-8ccd-24da43b26e64) topic for more information.

## App keys, client ID, and client secret {#AppKeys}

Requests against the Dimensions API require a valid app key passed in the HTTP `appkey` header. This application key allows you to track your API usage per application. The app key must be generated by an employee with the appropriate Developer Admin permissions. 

Requests against the Dimensions API also require a valid client ID and client secret passed in the HTTP `client_id` and `client_secret` headers. This information is provided when a tenant is provisioned. If you do not have access to these details, contact your system administrator. If for some reason these details have been lost, open a case with UKG support.

Refer to the [App keys, client ID, and client secret](C:a44a9f41-6442-42e3-91b1-9c946de54763) topic for more information.

## Versioning {#Versioning}

When UKG makes backwards-incompatible changes to the API, we release a new version. Our architecture supports both major and minor versions. When new versions are released, older versions may still be accessed for as long as they are supported. 

Any plans to eliminate support for older versions of the API are communicated well in advance to provide ample opportunity to bring your application in line with a supported release.  

* Major versions are large, backwards-incompatible departures from previous releases of the API and represent signficant steps forward. Such major changes are rare and are communicated well before each release.
	* The major version is specified in the URL:    
		**/v1**/scheduling/shifts

## HTTP status codes and error handling {#Errors}

When the API returns an error, it consists of an HTTP status code plus a JSON body. 

The HTTP status maps to client errors (4XX) and server errors (5XX) per [IETF standards](https://www.ietf.org/about/standards-process.html).

The body of the error includes the following fields:

* **code:** a fixed-length code associated with the error
* **message:** a description of the error
* **detail:** an optional JSON object with specific data about the error. This field enables sophisticated error handling, including multiple errors and partial results
* **infolink:** an optional link to documentation related to the error

Refer to the [HTTP status codes](C:ab842096-366f-496f-a471-e73ac58b8540) and the [Error handling](C:5337497a-fc55-4f05-95a3-9d0cadee52cd) topics for more information.

## Asynchronous requests {#AsynchronusRequests}

We support asynchronous requests that follow the polling paradigm. According to this method, the client submits a request and receives a ticket. The client then checks back at regular intervals to determine if the server is ready to return the result of the request.  

For current APIs that support asynchronous POST requests, `/async` is added to the end of the URI. For example: 

`POST {DNSName}/v1/commons/persons/base_persons/multi_read/async`    
`POST {DNSName}/v1/commons/persons/async`

*__Note:__ The URI methodology described above applies only to current APIs that support asynchronus requests. A permanent standard will be made available soon.*

### Asynchronous request flow {#AsynchronusRequestFlow}

1. A POST request returns HTTP 202 (Accepted) and a URL in a `Content-Location` header that allows retrieval of the status.
2. Subsequent requests poll the URL for status, encoded as the triplet:
	* **state:** one of PENDING, SUCCESSFUL, or FAILED 
	* **message:** a string about the operation to being processed
	* **next-ping:** optional integer with recommended next polling request in seconds
3. When the state is returned as SUCCESSFUL, the `Content-Location` header contains the URI of the result.

The URI returned in the `Content-Location` header represents the status of the operation. The caller issues GET operations using the `next-ping` header values to retrieve the status and the URI of the result. When the task finishes successfully, the ping returns an HTTP status code of 303 and the `Location` header contains the URI of the result. When the task is pending, the HTTP status code is 200, the `Content-Location` header has the same URI, and the body contains the status as shown above. When the task fails, the HTTP status and the error in the body are the same as when the call is synchronous.

## Internationalization and Localization (I18N and L10N) {#I18NAndL10N}

Our I18N/L10N support is built on common standards for languages, currencies, numbers, and dates.

### Standards {#Standards}

Requests and responses contain neutrally formatted data according to the following standards:

* [**ISO 639:**](https://en.wikipedia.org/wiki/ISO_639) Language codes 
* [**ISO 31661alpha2:**](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) Country codes 
* [**ISO 4217:**](https://en.wikipedia.org/wiki/ISO_4217) Currency codes 

### Language {#Language}

Language is processed via the `Accept-Language` HTTP header.

### Currency {#Currency}

Currency support defaults are based on context, but can be overridden via the custom header `currency-name` with supported [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) codes.

### Numbers {#Numbers}

Numbers are supported as fixed point according to the decimal standard described [here](https://www.w3.org/TR/xmlschema-2/#decimal). 

Floating point and doubles are supported according to the [IEEE 754-1985](https://en.wikipedia.org/wiki/IEEE_754-1985) standard.

### Date and time {#DateAndTime}

Our date and time support conforms to the [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) standard's 24-hour format, not zoned:    
	YYYY-MM-DD HH:MM:SS

## Conventions related to time {#ConventionsRelatedToTime}

### Beginning and end of time {#BeginningAndEndOfTime}

The assumed values for the earliest possible date (also known as the "beginning of time") and the latest possible date (also known as the "end of time") are 1900-01-01 and 3000-01-01, respectively. Any date value outside this range is rounded up or down, as appropriate.

### Timeframe {#Timeframe}

A timeframe is represented as a disjunction between a start and end date and a symbolic time reference. The name of the JSON key is `dateRange`. In JSON, the key `symbolicPeriod` is mutually exclusive with a pair of start and end dates:

``` json
"dateRange": {
   "symbolicPeriod": {
      "id": "100", // internal database ID. Resolves to startDate and endDate
      "qualifier": "…" // symbolic timeframe: "current_scheduled_period", and so on
    },
    "startDate": "…",
    "endDate": "…"
}
```

When the API encounters mutually exclusive fields, such as the simultaneous presence of start and end dates and a `symbolicPeriod`, a runtime error is generated and returned.

### Effective and expiration dates {#EffectiveAndExpirationDates}

The following rules define the use of effective and expiration dates:

* Effective dates are inclusive
* Expiration dates are exclusive
* Naming: 
	* `expirationDate`
	* `effectiveDate`

## Service limits {#ServiceLimits}

Service limits establish sensible, safe constraints on data returned by the API. These limits play an important role in preserving the health of our ecosystem and help ensure all users experience consistently high performance.

Generally, service limits constrain the number of employees and the time range that can be returned by a single request to ensure each request does not exceed reasonable limits. You cannot retrieve more data than the limits specified by these constraints in a single call.

The HTTP status code for service limits is 413. Refer to the [Service limits](C:fd45ab6e-6a20-4ce2-97e9-e2c2a95dacd5) topic for more information.

## Throttling {#Throttling}

Throttling mechanisms work alongside service limits to preserve the health of the Dimensions ecosystem and help ensure all users experience consistently high performance.
 
Throttling avoids service failures and severe slowdowns by ensuring usage of a resource does not exceed the load capacity of backend services.
 
The HTTP status code for throttling is 429. Refer to the [HTTP status codes and error handling](C:ab842096-366f-496f-a471-e73ac58b8540) topic for more information.
 
### Rate limits
 
If you exceed a rate limit, the API returns a header informing the caller of the amount of time it must wait before attempting the call again. 

## Tracking, logging, and support {#TrackingLoggingSupport}

Every API request contains an internal tracking ID, the `kronos-tid`, that is propagated to all intermediate requests that serve the originating request.

The `kronos-tid` is attached to all logs associated with the original call and subsequent requests, tracing those intermediate actions wherever they go within the Dimensions ecosystem to enhance support for your applications.

In addition, all requests and logs for a given user interaction or service call can be aggregated by `kronos-tid`. This grants even more visibility into the behavior of any given call.

## Next steps {#NextSteps}

If you're ready to put these principles into practice and make an API call against your Dimensions environment, proceed to the [Authentication and Security](C:a4943b5b-f44d-4eab-8ccd-24da43b26e64) topic or the [Make an API call](C:3ca261ba-fc8b-4354-a2b1-6892e006c046) topic.