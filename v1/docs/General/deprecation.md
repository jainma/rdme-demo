---
title: "Deprecation"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb662255dd00016e0b208"
---

# Deprecation

The UKG Dimensions Developer Portal informs API consumers that an API operation has been deprecated and what operation should be used in its place. The primary and most up-to-date information on deprecated operations is available on the Developer Portal.

This Frequently Asked Questions (FAQ) topic defines “deprecation” and explains where to find information related to deprecated operations.

## Questions

* [What level within the API structure is deprecated?](#Question1)
* [What does it mean if an API operation has been deprecated?](#Question2)
* [What is the reason for deprecating a Dimensions API operation?](#Question3)
* [Why should I use the new version of an API operation if the existing version still works?](#Question4)
* [Do I have to update my code to use the new version of the API operation?](#Question5)
* [Where can I find information that an API operation has been deprecated?](#Question6)

## What level within the API structure is deprecated? {#Question1}

Within the Developer Portal, the API is organized by domains, resources, and operations. Deprecation happens at the operation level. An operation is commonly referred to as an endpoint and consists of an HTTP method plus a URL.

## What does it mean if an API operation has been deprecated? {#Question2}

“Deprecation” means that the API operation has been replaced by a newer, better version. Deprecated operations continue to be supported but will not be enhanced with new features. On the Developer Portal, API consumers are informed that a new version of the operation exists and where to find the new version.

## What is the reason for deprecating a Dimensions API operation? {#Question3}

API operations are deprecated when a change is made to an existing operation, but backwards compatibility cannot be maintained. These "breaking changes" are typically driven by performance, security, or new functionality changes that require the request or response payloads to be updated in a way that is not backwards compatible with the prior version.

## Why should I use the new version of an API operation if the existing version still works? {#Question4}

We recommend you update your implementations to utilize the latest version of an operation as it provides better security, performance, and functionality.

## Do I have to update my code to use the new version of the API operation? {#Question5}

While we recommend applications be updated as soon as possible to use the new API operation, because a deprecated operation continues to be supported, it is up to the API consumer to determine when to update applications to call the new version. Customers seeking assistance in updating their applications can reach out to UKG Services or a Business Partner.

## Where can I find information that an API operation has been deprecated? {#Question6}

Deprecated API operations are announced in the Dimensions Developer Portal Version History, Important Notes, and in the Dimensions Release Notes. While the Dimensions Release Notes provides summary information, the Developer Portal provides deprecation information as follows:

* Important notes: This topic has a section for each Dimensions release with summary information related to deprecated API operations
* Version History: This topic includes information regarding new versions of the API. 
    * Version 2 resources and operations: This is a child topic of Version History where you can find a list of v2 operations and the v1 operation they replace. It also specifies in which Dimensions release each v2 operation was added.
    ![Version 2 Resources and Operations](I:4e3ae323-a32a-4f13-ae5e-e420412f84a4 "Version 2 Resources and Operations")
* API reference documentation - side menu: If an API operation has been deprecated, the operation’s name is followed by “Deprecated” in parentheses.
    
    ![Menu - Cost Centers](I:123c0daf-db33-4eae-b497-644543572f55 "Menu - Cost Centers")
* API reference documentation - operation page: If an API operation has been deprecated, the name is followed by “Deprecated” in parentheses, the replacement operation is specified, and a note is present recommending you update your implementations.
    ![Example Deprecated Operation](I:518134e8-f796-42e0-8525-b0dcbba5eb3e "Example Deprecated Operation")