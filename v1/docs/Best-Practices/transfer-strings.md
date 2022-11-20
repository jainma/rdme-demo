---
title: "Transfer Strings"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "63638713c59bff0262ce8c29"
---

# Transfer Strings

Transfer strings consist of an ordered, semi-colon separated list of transfer types, including business structure, work rule, cost center, and labor categories. Each transfer type is separated by a semicolon, and the transfer string ends with a semicolon. There can be 0 to 6 labor categories, each separated by commas.
 
The format is:

``` 
Business Structure;Work Rule;Cost Center;Labor Category1,2,...,6;
``` 

When specifying a subset of the transfer types, you only need to provide a value in the appropriate location. You must always include all of the semicolons. If including a labor category, you must always include all of the commas. 

For example, to transfer only a cost center, the format is:

``` 
;;Cost Center;;
``` 

If a more complex transfer includes a business structure path, a work rule, a cost center, and two labor categories, the format is:

``` 
Attestation/DA DeptA/DA Dept A Job1;Support;CC_Production;Attest Contract1,Attest Project1,,,,;
``` 

**Note:** When entering transfer strings, make sure there are no leading or trailing spaces, as these spaces invalidate the transfer type values.