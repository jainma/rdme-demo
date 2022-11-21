---
title: "Manage Dimensions UI Sessions"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "6377481862a5b60063c50020"
---
 

# Manage Dimensions UI sessions

The API allows you to manage certain aspects of Dimensions UI sessions. 

Currently, the API supports logging out a session.

* [Prerequisites](#Prerequisites)
* [Log out a session](#LogOut)
    * [Model properties](#modelProperties)
        * [Required properties](#requiredProperties)
* [Code examples](#CodeExamples)

## Prerequisites {#Prerequisites}

The following headers are required to manage Dimensions UI sessions using the API:

**Headers**

* `Content-Type : application/json`
* `appkey : <<app_key>>`
* `Authorization : <<access_token>>`

*__Note:__ Obtain an `<<appkey>>` from an employee with the appropriate Developer Admin permissions. Refer to the [Generate and access app keys](C:a44a9f41-6442-42e3-91b1-9c946de54763) topic for more information.*

## Log out a session {#LogOut}

To log out of the system, POST a call to the following URL:

`https://<<hostName>>.mykronos.com/api/v1/auth/logout`

The request body should follow the following model:

``` json
{
  "cookies": [
    {
      "name": "authn_ssid",
      "value": "{{ authn_ssid  }}",
      "comment": null,
      "domain": "{{ devDomain  }}",
      "maxAge": -1,
      "path": "{{ path  }}",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "AUTHN_TOKEN",
      "value": "{{ AUTHN_TOKEN  }}",
      "comment": null,
      "domain": "{{ devDomain  }}",
      "maxAge": -1,
      "path": "{{ path  }}",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "IDP_URI",
      "value": "{{ IDP_URI  }}",
      "comment": null,
      "domain": "{{ dimensionsDomain  }}",
      "maxAge": -1,
      "path": "{{ path  }}",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "TENANT_AUTHORIZATION",
      "value": "{{ TENANT_AUTHORIZATION  }}",
      "comment": null,
      "domain": "{{ devDomain  }}",
      "maxAge": -1,
      "path": "{{ path  }}",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "kronosAuthToken",
      "value": "{{ kronosAuthToken  }}",
      "comment": null,
      "domain": "{{ vanityDomain  }}",
      "maxAge": -1,
      "path": "{{ path  }}",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "JSESSIONID",
      "value": "{{ JSESSIONID  }}",
      "comment": null,
      "domain": "{{ vanityDomain  }}",
      "maxAge": -1,
      "path": "{{ path  }}",
      "secure": false,
      "version": 0,
      "httpOnly": false
    }
  ]
}
```
A successful call returns an HTTP 200 SUCCESS response. An unsuccessful call returns an HTTP 401 error response indicating that no session could be found associated with the data sent in the request payload.

### Model properties {#modelProperties}

**Notes:**

* The property `path` defaults to a value of `"/"` if no value is passed.

#### Required properties {#requiredProperties}

The following properties are required:

* `name`
* `value`

## Code examples {#CodeExamples}

The following code examples demonstrate logging out a Dimensions UI session using cURL and Java OkHttp.

*__Note:__ The follow examples include the entire request payload model, but only the `name` and `value` properties are required.*

**cURL**
<?prettify lang=curl linenums=true?>
``` curl
curl --location --request POST 'https://<<hostName>>.mykronos.com/api/v1/auth/logout' \
--header 'appkey: <<app_key>> ' \
--header 'Content-Type: application/json' \
--header 'Authorization: <<access_token>> \
--header 'Accept: */*' \
--data-raw '{
  "cookies": [
    {
      "name": "authn_ssid",
      "value": ""{{authn SSID}}"",
      "comment": null,
      "domain": "<<AbbreviatedHostName>>.mykronos.com",
      "maxAge": -1,
      "path": "/",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "AUTHN_TOKEN",
      "value": "{{authentication token}}",
      "comment": null,
      "domain": "<<AbbreviatedHostName>>.mykronos.com",
      "maxAge": -1,
      "path": "/",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "IDP_URI",
      "value": "{{IDP token}}",
      "comment": null,
      "domain": "mykronos.com",
      "maxAge": -1,
      "path": "/",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "TENANT_AUTHORIZATION",
      "value": "{{tenant authorization token}}",
      "comment": null,
      "domain": "<<AbbreviatedHostName>>.mykronos.com",
      "maxAge": -1,
      "path": "/",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "kronosAuthToken",
      "value": "{{kronos authorization token}}",
      "comment": null,
      "domain": "<<hostName>>.mykronos.com",
      "maxAge": -1,
      "path": "/",
      "secure": false,
      "version": 0,
      "httpOnly": false
    },
    {
      "name": "JSESSIONID",
      "value": "{{JSessionId}}",
      "comment": null,
      "domain": "<<hostName>>.mykronos.com",
      "maxAge": -1,
      "path": "/",
      "secure": false,
      "version": 0,
      "httpOnly": false
    }
  ]
}'
```

**Java OkHttp**
<?prettify lang=java linenums=true?>
``` java
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n  \"cookies\": [\n    {\n      \"name\": \"authn_ssid\",\n      \"value\": \"\"{{authn SSID}}\"\",\n      \"comment\": null,\n      \"domain\": \"<<AbbreviatedHostName>>.mykronos.com\",\n      \"maxAge\": -1,\n      \"path\": \"/\",\n      \"secure\": false,\n      \"version\": 0,\n      \"httpOnly\": false\n    },\n    {\n      \"name\": \"AUTHN_TOKEN\",\n      \"value\": \"{{authentication token}}\",\n      \"comment\": null,\n      \"domain\": \"<<AbbreviatedHostName>>.mykronos.com\",\n      \"maxAge\": -1,\n      \"path\": \"/\",\n      \"secure\": false,\n      \"version\": 0,\n      \"httpOnly\": false\n    },\n    {\n      \"name\": \"IDP_URI\",\n      \"value\": \"{{IDP token}}\",\n      \"comment\": null,\n      \"domain\": \"mykronos.com\",\n      \"maxAge\": -1,\n      \"path\": \"/\",\n      \"secure\": false,\n      \"version\": 0,\n      \"httpOnly\": false\n    },\n    {\n      \"name\": \"TENANT_AUTHORIZATION\",\n      \"value\": \"{{tenant authorization token}}\",\n      \"comment\": null,\n      \"domain\": \"<<AbbreviatedHostName>>.mykronos.com\",\n      \"maxAge\": -1,\n      \"path\": \"/\",\n      \"secure\": false,\n      \"version\": 0,\n      \"httpOnly\": false\n    },\n    {\n      \"name\": \"kronosAuthToken\",\n      \"value\": \"{{dimensions authorization token}}\",\n      \"comment\": null,\n      \"domain\": \"<<hostName>>.mykronos.com\",\n      \"maxAge\": -1,\n      \"path\": \"/\",\n      \"secure\": false,\n      \"version\": 0,\n      \"httpOnly\": false\n    },\n    {\n      \"name\": \"JSESSIONID\",\n      \"value\": \"{{JSessionId}}\",\n      \"comment\": null,\n      \"domain\": \"<<hostName>>.mykronos.com\",\n      \"maxAge\": -1,\n      \"path\": \"/\",\n      \"secure\": false,\n      \"version\": 0,\n      \"httpOnly\": false\n    }\n  ]\n}");
Request request = new Request.Builder()
  .url("https://<<hostName>>.mykronos.com/api/v1/auth/logout")
  .method("POST", body)
  .addHeader("appkey", "<<app_key>>")
  .addHeader("Content-Type", "application/json")
  .addHeader("Authorization", "<<access_token>>")
  .addHeader("Accept", "*/*")
  .build();
Response response = client.newCall(request).execute();
```

A successful call returns an HTTP 200 status code.