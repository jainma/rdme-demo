---
title: "Pragmatic REST"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb68482bf5e0061c0324a"
---

# Pragmatic REST

Our REST implementation approaches the real-world challenges facing any large-scale API sensibly and realistically in a way that is based on practical rather than purely theoretical considerations.

## Operations that do not fit the REST paradigm

When an API operation cannot be described in terms of a CRUD (**C**reate/**R**ead/**U**pdate/**D**elete) action on simple data, we include an additional verb as a URL subresource. This concept is known as "action as a resource."

Perhaps the most common use case involves the execution of the same CRUD operation on each member of a set. 

* The HTTP method is POST
* Within the URL, the resource is followed by a verb subresource according to the following format:    
	**multi_{CRUD verb}**    
	CRUD verbs: **create**, **read**, **update**, and **delete**    
	For example:    
	`/v1/attendance/markers/multi_create`    
	`/v1/attendance/markers/multi_delete`    
	`/v1/attendance/markers/multi_read`
* The body consists of a list of individual data items or a set of SQL-like clauses

A much more rare use case involves non-CRUD operations on one or more data items.

* The HTTP method is POST
* Within the URL, the resource is followed by a verb subresource