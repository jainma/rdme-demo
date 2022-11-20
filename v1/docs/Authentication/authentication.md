---
title: "Authentication and security"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "636cb62d75a8640090601e17"
---

# Authentication and security

Requests against the Dimensions API must be authenticated and made over HTTPS. If these requirements are not met, the request fails.

Our API's authentication is built on the OAuth 2.0 standard. Each API request must include an HTTP Authorization header containing an OAuth 2.0 access token.

Successful token requests generate an access token and a refresh token. The access token is usable from the moment it is generated until the number of seconds defined by `expires_in` elapses. The refresh token can be used to generate new access tokens until the session expires. Refresh tokens expire after 7 days.

* [Prerequisites](#Prerequisites)
* [Log in and generate tokens](#GenerateTokens)
    * [Refresh a token](#RefreshAToken)
    * [Revoke a token](#RevokeAToken)
* [Code examples](#CodeExamples)
    * [Generate tokens](#CodeGenerateTokens)
    * [Refresh a token](#CodeRefreshAToken)
    * [Revoke a token](#CodeRevokeAToken)
* [Federated identity management systems](#FederatedIMS)
* [Manage Dimensions UI sessions](#DimensionsUI)
* [Make an API call](#MakeAnAPICall)

## Prerequisites {#Prerequisites}

The following are required to generate tokens:

**Headers**

* `Content-Type : application/x-www-form-urlencoded`
* `appkey : <<app_key>>`

*__Note:__ Obtain an `<<appkey>>` from an employee with the appropriate Developer Admin permissions. Refer to the [Generate and access app keys](C:a44a9f41-6442-42e3-91b1-9c946de54763) topic for more information.*

## Log in and generate tokens {#GenerateTokens}

To log in to the system and obtain an access token and a refresh token, POST a call to the authentication URL:

`https://<<hostName>>.mykronos.com/api/authentication/access_token`

Include the following in the request body, where `<<username>>` and `<<password>>` are the Dimensions username and password of the employee you wish to log in:

* `username : <<username>>`
* `password : <<password>>`
* `client_id : <<client ID>>`
* `client_secret : <<client password>>`
* `grant_type : password`
* `auth_chain : OAuthLdapService`

Include the following HTTP headers:

* `Content-Type : application/x-www-form-urlencoded`
* `appkey : <<app_key>>`

A successful call returns:

* `access_token`: A string representing the access token.
* `refresh_token`: A string used to obtain a new access token when the current access token becomes invalid or expires. Refresh tokens are optional, are issued at the discretion of the server, and expire after 7 days.
* `scope`: The server uses this response parameter to inform the client of the scope of the issued `access_token`. 
* `token_type`: Defines the type of token profile issued by the server, such as `Bearer` or `mac`. This enables the client to successfully utilize the `access token`.
* `expires_in`: Lifetime in seconds of the `access_token`.

Even though your tokens are time-limited, they are very powerful. Do not share your `access_token` or `refresh_token`. Protect them as you would a username and password combination. 

### Refresh a token {#RefreshAToken}

To use a refresh token to generate a new access token, POST a call to the following authentication URL:

`https://<<hostName>>.mykronos.com/api/authentication/access_token`

Include the following HTTP headers:

* `Content-Type : application/x-www-form-urlencoded`
* `appkey : <<app_key>>`

Include the following in the request body:

* `refresh_token : <<refresh_token>>`
* `client_id : <<client ID>>`
* `client_secret : <<client password>>`
* `grant_type : refresh_token`
* `auth_chain : OAuthLdapService`

A successful call returns:

* `access_token`: A string representing the access token.
* `scope`: The server uses this response parameter to inform the client of the scope of the issued `access_token`. 
* `token_type`: Defines the type of token profile issued by the server, such as `Bearer` or `mac`. This enables the client to successfully utilize the `access token`.
* `expires_in`: Lifetime in seconds of the `access_token`.

### Revoke a token {#RevokeAToken}

You can revoke both access and refresh tokens.

Revoking an access token does not revoke the refresh token issued alongside that access token.

Revoking a refresh token also revokes any access tokens generated alongside or through the use of that refresh token.

*__Note:__ If you have multiple access tokens for a single user that were obtained using different authorization grants, you must make multiple calls to the revoke token endpoint to invalidate each token.*

To revoke a token, POST a call to the following authentication URL:

`https://<<hostName>>.mykronos.com/api/authentication/token/revoke`

Include the following HTTP headers:

* `Content-Type : application/x-www-form-urlencoded`
* `appkey : <<app_key>>`

Include the following in the request body:

* `token : <<access_or_refresh_token>>`
* `client_id : <<client ID>>`
* `client_secret : <<client password>>`

A successful call returns an HTTP 200 status code.

## Code examples {#CodeExamples}

The following code examples demonstrate generating and refreshing a token using cURL and Java OkHttp.

* [Generate tokens](#CodeGenerateTokens)
* [Refresh a token](#CodeRefreshAToken)
* [Revoke a token](#CodeRevokeAToken)

### Generate tokens {#CodeGenerateTokens}

The following code examples demonstrate calls that request an access token and refresh token.

**cURL**
<?prettify lang=curl linenums=true?>
``` curl
curl -X POST \
  https://<<hostName>>.mykronos.com/api/authentication/access_token \
  -H 'appkey: <<app_key>>' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'username=<<username>>&password=<<password>>&client_id=<<client ID>>&client_secret=<<client password>>&grant_type=password&auth_chain=OAuthLdapService'
```

**Java OkHttp**
<?prettify lang=java linenums=true?>
``` java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "username=<<username>>&password=<<password>>&client_id=<<client ID>>&client_secret=<<client password>>&grant_type=password&auth_chain=OAuthLdapService");
Request request = new Request.Builder()
  .url("https://<<hostName>>.mykronos.com/api/authentication/access_token")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("appkey", "<<app_key>>")
  .build();

Response response = client.newCall(request).execute();
```

This call returns a response body similar to the following example:

<?prettify lang=json linenums=true?>
``` json
{
    "access_token": "7a398ff1-1ec4-40de-a21a-f1df5f977710",
    "refresh_token": "ae131028-414c-4fb7-b17d-4a0769bbcd96",
    "scope": "givenName mail nonce openid profile sn uid",
    "id_token": "<<value>>",
    "token_type": "Bearer",
    "expires_in": 1799
}
```

You must parse the response to fetch the value of `access_token` for your API calls.

### Refresh a token {#CodeRefreshAToken}

The following code examples demonstrate refreshing an access token using a refresh token.

**cURL**
<?prettify lang=curl linenums=true?>
``` curl
curl -X POST \
  https://<<hostName>>.mykronos.com/api/authentication/access_token \
  -H 'appkey: <<app_key>>' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'refresh_token=<<refresh_token>>&client_id=<<client ID>>&client_secret=<<client password>>&grant_type=refresh_token&auth_chain=OAuthLdapService'
```

**Java OkHttp**
<?prettify lang=java linenums=true?>
``` java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "refresh_token=<<refresh_token>>&client_id=<<client ID>>&client_secret=<<client password>>&grant_type=refresh_token&auth_chain=OAuthLdapService");
Request request = new Request.Builder()
  .url("https://<<hostName>>.mykronos.com/api/authentication/access_token")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("appkey", "<<app_key>>")
  .build();

Response response = client.newCall(request).execute();
```

This call returns a response body similar to the following example:

<?prettify lang=json linenums=true?>
``` json
{
    "access_token": "4bb7e58a-eddf-4ae0-aaf8-14a748d7c25c",
    "scope": "givenName mail nonce openid profile sn uid",
    "id_token": "<<value>>",
    "token_type": "Bearer",
    "expires_in": 1799
}
```

### Revoke a token {#CodeRevokeAToken}

The following code examples demonstrate revoking an access or refresh token.

**cURL**
<?prettify lang=curl linenums=true?>
``` curl
curl -X POST \
  https://<<hostName>>.mykronos.com/api/authentication/token/revoke \
  -H 'appkey: <<app_key>>' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'token=<<access_or_refresh_token>>&client_id=<<client ID>>&client_secret=<<client password>>'
```

**Java OkHttp**
<?prettify lang=java linenums=true?>
``` java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "token=<<access_or_refresh_token>>&client_id=<<client ID>>&client_secret=<<client password>>");
Request request = new Request.Builder()
  .url("https://<<hostName>>.mykronos.com/api/authentication/token/revoke")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("appkey", "<<app_key>>")
  .build();

Response response = client.newCall(request).execute();
```

A successful call returns an HTTP 200 status code.

## Federated identity management systems {#FederatedIMS}

If you are using a token provided by an OAuth compatible federated identity management (IDP) system that has been properly interfaced with your tenant, include the federated token as your `access_token` value just as you would use a Dimensions-generated `access_token`.

If you are building an application intended to interface with a wide vatiety of tenants, each of which might use a different IDP with a variety of possible configurations, or if your application needs to be able to request a set of tokens from a tenant interfaced with a federated identity management system that is not able to provide tokens directly, refer to the [Authenticate with federated user accounts](C:32a1461e-be6d-40f4-a575-215f606d865f) topic.

## Manage Dimensions UI sessions {#DimensionsUI}

The API allows you to manage certain aspects of Dimensions UI sessions. For example, you can log out a UI session using the API call described in the [Manage Dimensions UI sessions](C:054cdf88-4a6d-49c7-ad22-c94787d999fa) topic.

## Make an API call {#MakeAnAPICall}

If you are ready to use your generated access token to make an API call against your Dimensions environment, proceed to the [Make an API call](C:3ca261ba-fc8b-4354-a2b1-6892e006c046) topic.