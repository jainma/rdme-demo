---
title: "An Introduction to Representational State Transfer (REST) APIs"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
---

# An Introduction to Representational State Transfer (REST) APIs

* [What are APIs? Why should we care?](#WhatAreAPIs)
* [How do RESTful web APIs work?](#HowDoWebAPIsWork)
	* [HTTP](#HTTP)
	* [Web APIs](#WebAPIs)
	* [REST](#REST)
* [Other Resources](#OtherResources)

## What are APIs? Why should we care? {#WhatAreAPIs}

Web APIs have accelerated dramatically in popularity in recent years and have become an integral part of the modern software development world. From their introduction in 2005 to late 2013, the number of new web APIs introduced to the market exploded--the first 1,000 APIs were introduced over a 4-year period, whereas by 2013 over 1,000 APIs were introduced in the latter half of the year alone. [(source)](https://www.programmableweb.com/api-research)

But what are APIs, and what are web APIs in particular? 

At their most basic level, application programming interfaces (APIs) allow one application to talk to another or allow parts of a distributed application to talk to other parts. Web APIs allow an application to expose parts of its internal functionality to other applications over the internet. Recent API research reports that over 90% of all new APIs are Representational State Transfer (REST) APIs, which are web APIs conforming to a strict set of constraints that ensure high performance and easy maintainability. 

This shift to web-based API frameworks goes hand-in-hand with the emerging Cloud computing market. As UKG in particular and the software field in general become more Cloud-centric, understanding the part these HTTP-based APIs play in software architecture is useful for anyone seeking to extend their technology platform.

## How do RESTful web APIs work? {#HowDoWebAPIsWork}

### HTTP {#HTTP}

Web APIs, including REST APIs, communicate via the [Hypertext Transfer Protocol (HTTP)](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol). HTTP is a client-server, request-response protocol that serves as the foundation of data communication for the World Wide Web.

Consider a common scenario: a web browser communicating with a server to render a web page. In this example, the web browser is the client and an application running on a computer hosting a web site is the server. The client submits an HTTP request message to the server. The server, which provides resources such as HTML files or performs other functions on behalf of the client, returns a response message to the client. The response contains status information about the request and may also contain requested content in its message body.

HTTP is a stateless protocol. A stateless protocol does not require the HTTP server to retain information or status about each user outside of the context of a single request.

### Web APIs {#WebAPIs}

An [API](https://en.wikipedia.org/wiki/Application_programming_interface) is a set of routines, protocols, and tools for building software applications. An API expresses a software component in terms of its operations, inputs, outputs, and underlying types.

A web API, however, is a simpler concept: it defines a specification of remote calls exposed via the web and defines the structure of response messages, which are usually in an [Extensible Markup Language (XML)](https://en.wikipedia.org/wiki/XML) or [JavaScript Object Notation (JSON)](https://en.wikipedia.org/wiki/JSON) format. These calls allow applications to communicate and exchange data over the internet.

A RESTful web API communicates over the Hypertext Transfer Protocol with the same HTTP verbs (GET, POST, PUT, DELETE, and so on) used by web browsers to retrieve web pages and send data to remote servers.

HTTP verbs are also known as request methods and are divided into safe and unsafe methods. Safe methods retrieve information and are not intended to change anything on the server. Unsafe methods perform actions that are capable of changing data on the server.

Safe Methods  | Unsafe Methods
------------- | -------------
HEAD          | POST
GET           | PUT
OPTIONS       | DELETE
TRACE         | PATCH

### REST {#REST}

Representational State Transfer (REST) is a style of software architecture for creating scalable web services. REST is a coordinated set of constraints that ensure high performance and easy maintainability. These constraints are applied to the design of components in a distributed software system.

A distributed software system contains components that are located on networked computers that communicate and coordinate their actions by passing messages. A RESTful web API forms the communication layer of a distributed system and can also allow different distributed systems to interact and communicate with each other.

REST interfaces usually involve collections of resources with identifiers which can be operated upon using standard HTTP verbs. For example, the resource `/people/paul` can be operated upon with the request method DELETE: `DELETE /people/paul`. In REST terminology, DELETE is the HTTP verb and resources such as `/people/paul` are nouns.

A REST endpoint is a specific URI that a REST API utilizes to perform request methods. The REST API needs to know its endpoints to know how to fetch, deliver, or alter data via HTTP in a RESTful way.

A web API is said to be RESTful when it properly conforms to the constraints defined by REST.

The REST architectural style was developed by the [W3C Technical Architecture Group (TAG)](https://www.w3.org/) in parallel with HTTP 1.1. The World Wide Web represents the largest implementation of a system conforming to the REST architectural style.

## Other Resources {#OtherResources}

From here you may wish to proceed to the [Getting started](C:636f581c-50a8-41a7-af43-e5057f9c20bd) topic or read more about our particular implementation of REST in the [Pragmatic REST](C:86106a78-330e-4ebe-b41c-e7a07f27ee0e) topic of the [Overview](C:0df07e3a-7e83-47c8-9ae6-ecf71ce5f4e7). 