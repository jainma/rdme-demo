---
title: "Authenticate with federated user accounts"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
category: "637a4341809da900abfdc4bf"
---

# Authenticate with federated user accounts

Requests against the Dimensions API must be authenticated and made over HTTPS. If these requirements are not met, the request fails.

If you are using a token provided by an OAuth compatible federated identity management (IDP) system that has been properly interfaced with your tenant, include the federated token as your `access_token` value just as you would use a Dimensions-generated `access_token`.

Follow the instructions in this topic if you are building an application intended to interface with a wide vatiety of tenants, each of which might use a different IDP with a variety of possible configurations, or if your application needs to be able to request a set of tokens from a tenant interfaced with a federated identity management system that is not able to provide tokens directly.

Successful token requests generate an access token and a refresh token. The access token is usable from the moment it is generated until the number of seconds defined by `expiresInSeconds` elapses. The refresh token can be used to generate new access tokens and refresh tokens until the session expires. Refresh tokens expire after 8 hours.

* [Prerequisites](#Prerequisites)
* [Log in and generate tokens](#GenerateTokens)
    * [Refresh a token](#RefreshAToken)
    * [Legacy method (Deprecated)](#OldMethod)
* [Make an API call](#MakeAnAPICall)

## Prerequisites {#Prerequisites}

The following must be in place before an application can authenticate with federated user accounts:

* Federation must be configured correctly for each tenant accessed by your application. 
* Users must be able to log in to the Dimensions UI using a tenant's configured IDP. 
* Your application must expose a URI to which responses and token information is directed, and this URI must be whitelisted in each tenant. To whitelist a URI for this purpose, go to Application Setup > System settings > Global Values in the Dimensions UI and update the following tenant-specific system setting: `global.oAuth.authCode.redirection.uris`.

## Log in and generate tokens {#GenerateTokens}

In your application, route to the following URI:

`https://<<hostName>>.mykronos.com/oauth2/authorize?response_type=code&client_id=<<client ID>>&redirect_uri=<<whitelisted URI>>`

> **Note:** Use the tenant's `hostName` configured for users with IDP accounts. This portion of the URI is set up as part of a tenant's federation configuration.

> **Important:** The query parameters in the URI are case-sensitive and must be entered exactly as specified: `response_type`, `client_id`, and `redirect_uri`. 

This URI displays a login screen for the IDP user if the user is not already logged in. After the user logs in, the tenant redirects to to URI defined in `redirect_uri` and includes the following:

`https://<<whitelisted URI>>/?code=<<code>>&iss=<<iss URI>>&client_id=<<client ID>>`

* `code`: An authentication string required for the next call in the sequence to generate an access token.
* `iss`: The authentication Server Issuer Identification.
* `client_id`: A string representing the tenant's client ID.

> **Note:** The authentication `code` has a lifetime of 5 minutes and can only be used once in a call to generate tokens. 

In your application, POST a call to the following authentication URI:

`https://<<hostName>>.mykronos.com/api/authentication/access_token`

Include the following HTTP headers:

* `Content-Type : application/x-www-form-urlencoded`
* `appkey : <<app_key>>`

Include the following in the request body:

* `redirect_uri=<<whitelisted URI>>`
* `client_id=<<client ID>>`
* `client_secret=<<client password>>`
* `grant_type=authorization_code`
* `code=<<code>>`

A successful call to the authentication URI returns:

* `access_token`: A string representing the access token.
* `refresh_token`: A string used to obtain a new access token when the current access token becomes invalid or expires. Refresh tokens are optional, are issued at the discretion of the server, and expire after 8 hours.
* `scope`: The server uses this response parameter to inform the client of the scope of the issued `access_token`. 
* `token_type`: Defines the type of token profile issued by the server, such as `Bearer` or `mac`. This enables the client to successfully utilize the `access token`.
* `expires_in`: Lifetime in seconds of the `access_token`.

Even though your tokens are time-limited, they are very powerful. Do not share your `access_token` or `refresh_token`. Protect them as you would a username and password combination. 

### Refresh a token {#RefreshAToken}

To use a refresh token to generate a new access token and refresh token based on the credentials of the user who generated the initial refresh token, POST a call to the following authentication URI:

`https://<<hostName>>.mykronos.com/api/authentication/access_token`

Include the following HTTP headers:

* `Content-Type : application/x-www-form-urlencoded`
* `appkey : <<app_key>>`

Include the following in the request body:

* `refresh_token : <<refreshToken>>`
* `client_id : <<client ID>>`
* `client_secret : <<client password>>`
* `grant_type : refresh_token`
* `auth_chain : OAuthLdapService`

A successful call to the authentication URI returns:

* `access_token`: A string representing the access token.
* `refresh_token`: A string used to obtain a new access token when the current access token becomes invalid or expires. Refresh tokens are optional, are issued at the discretion of the server, and expire after 8 hours.
* `scope`: The server uses this response parameter to inform the client of the scope of the issued `access_token`. 
* `token_type`: Defines the type of token profile issued by the server, such as `Bearer` or `mac`. This enables the client to successfully utilize the `access token`.
* `expires_in`: Lifetime in seconds of the `access_token`.

### Legacy method (Deprecated) {#OldMethod}

> **Note:** This **deprecated** legacy method is less secure and should no longer be used.

#### Prerequisities

For the deprecated legacy method, your application must also expose a URI to which responses and token information is directed, and this URI must be whitelisted in each tenant. To whitelist a URI for this purpose, you must enter a ticket to request an update to the following tenant-specific system setting: `global.oAuthToken.redirection.domain.whiteList`.

#### Legacy method

In your application, route to the following URI:

`https://<<hostName>>.mykronos.com/accessToken?clientId=<<client ID>>&targetURL=<<whitelisted URL>>`

> **Note:** Use the tenant's `hostName` configured for users with IDP accounts. This portion of the URI is set up as part of a tenant's federation configuration.

> **Important:** The query parameters in the URI are case-sensitive and must be entered exactly as specified: `clientId` and `targetURL`. 

This URL displays a login screen for the IDP user. After the user logs in, the tenant returns:

* `accessToken`: A string representing the access token.
* `refreshToken`: A string used to obtain a new access token when the current access token becomes invalid or expires. Refresh tokens are optional, are issued at the discretion of the server, and expire after 8 hours.
* `tokenType`: Defines the type of token profile issued by the server, such as `Bearer` or `mac`. This enables the client to successfully utilize the `access token`.
* `expiresInSeconds`: Lifetime in seconds of the `access_token`.
* `username`: The user name of the logged-in user.

Even though your tokens are time-limited, they are very powerful. Do not share your `access_token` or `refresh_token`. Protect them as you would a username and password combination. 

## Make an API call {#MakeAnAPICall}

If you are ready to use your generated access token to make an API call against a tenant, proceed to the [Make an API call](C:3ca261ba-fc8b-4354-a2b1-6892e006c046) topic.