---
title: "Structure and navigation"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb68482bf5e0061c0324a"
---

# Structure and navigation

The Developer Portal fully documents the Dimensions API and is organized into reference and conceptual documentation, accessed by means of the API and Docs links on the landing page. 

* [Reference documentation](#ReferenceDocumentation)
	* [Structure](#StructureReference)
* [Conceptual documentation](#ConceptualDocumentation)
	* [Structure](#StructureConceptual)
	
## Reference documentation {#ReferenceDocumentation}

Reference documentation describes our API in detail, down to each operation's request and response. Reference documentation is accessed through the API links on the landing page of the Developer Portal and by the persistent API link in the top menu. This area of the Developer Portal houses our library of API resources, organized hierarchically by domain, or major functional area, logical subgroup, API resource, and all available operations against each resource. 

### Structure {#StructureReference}

Each functional area within the suite is known as a **domain**. Domains are further divided into subgroups to organize API resources into logical groupings. Some domains contain no subgroups. Others contain many. Every domain contains **resources**, each of which represents a business entity that is stored or computed.

* Stored entities include punches, accrual balances, and shifts
* Computed entities include the schedule and the Attendance processor

Every resource is accessed using one or more **operations**, each of which consists of an HTTP method plus a URL.

While most domains focus on a specific functional area, Common Resources and Platform do not. 

The Common Resources domain contains resources shared by all domains, allowing you to access and manipulate general employee data, user display profiles, business structures, the Control Center, the Transaction Assistant, and data aggregated across domains. 

The Platform domain contains resources with supporting capabilities that are neutral to workforce management concepts.

## Conceptual documentation {#ConceptualDocumentation}

Conceptual documentation provides writer-crafted user guidance that introduces our API and provides a series of informative and tutorial topics to get you started with the API as quickly as possible. This area of the Developer Portal also provides overviews of our API, including our pragmatic implementation of the REST standard, and of our major domains.

### Structure {#StructureConceptual}

Our [Getting started](C:636f581c-50a8-41a7-af43-e5057f9c20bd) topic introduces the basic concepts undergirding our API platform and provides brief, useful introductions to CRUD operations, the basic flow of our calls, API resources, operations against those resources, authentication and security, app keys, versioning, errors and error handling, asynchronous requests, the internationalization and localization standards we employ, and our tracking, logging, and support strategy. 

The [Overview](C:0df07e3a-7e83-47c8-9ae6-ecf71ce5f4e7) of our API explains the primary domains that comprise our suite, our particular implementation of the REST architectural style, and the structure and navigation of our Developer Portal.

Our collection of [guides](C:92b16358-756a-41bf-9204-b0aaf7262cfa) steps you through building some of our most popular features into your application. Each feature includes instructions for constructing valid requests and demonstrates example responses.