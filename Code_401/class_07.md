# Bearer Authorization
---

## Write the Following Steps in Order

1. Register your application to get a client_id and client_secret
1. Ask the client if they want to sign in via a third party
1. Redirect to a third party authentication endpoint
1. Make a request to a third-party API endpoint
1. Receive authorization code
1. Make a request to the access token endpoint
1. Receive access token

## What Can You Do With an Authorization Code?

An authorization code is a temporary code that the client will exchange for an access token.
[*"Authorization Code Grant"*](https://www.oauth.com/oauth2-servers/server-side-apps/authorization-code/)

## What Can You Do With an Access Token?

Access tokens are the thing that applications use to make API requests on behalf of a user. The access token represents the authorization of a specific application to access specific parts of a user’s data.
[*"Access Tokens"*](https://www.oauth.com/oauth2-servers/access-tokens/)

## What is a Benefit of Using OAuth Instead of Your Own Basic Authentication?

The access to the resources is realized via HTTP / HTTPS with the token indicated in the headers. This allows OAuth usage in almost any solutions: in mobile and desktop applications, on various sites, and even in browser plug-ins.
[*"Oauth 2.0 Basic Understanding"*](https://stfalcon.com/en/blog/post/oauth-2.0)

## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Client ID** | *The client_id is a public identifier for apps. It must be unique across all clients that the authorization server handles.* [*"The Client ID and Secret"*](https://www.oauth.com/oauth2-servers/client-registration/client-id-secret/) |
| **Client Secret** | *The client_secret is a secret known only to the application and the authorization server. It must be sufficiently random to not be guessable.* [*"The Client ID and Secret"*](https://www.oauth.com/oauth2-servers/client-registration/client-id-secret/) |
| **Authentication Endpoint** | *The authorization endpoint can be used to request either access tokens or authorization codes (implicit and authorization code flow).* [*"Authorization/Authentication Endpoint"*](https://identityserver.github.io/Documentation/docsv2/endpoints/authorization.html) |
| **Access Token Endpoint** | *The token endpoint is used by the application in order to get an access token or a refresh token. In the Authorization Code Flow, the application exchanges the authorization code it got from the authorization endpoint for an access token.* [*"OAuth 2.0 Authorization Framework"*](https://auth0.com/docs/protocols/protocol-oauth2) |
| **API Endpoint** | *Simply put, an endpoint is one end of a communication channel. When an API interacts with another system, the touchpoints of this communication are considered endpoints. For APIs, an endpoint can include a URL of a server or service. Each endpoint is the location from which APIs can access the resources they need to carry out their function.* [*"API Endpoints - What Are They? Why Do They Matter?"*](https://smartbear.com/learn/performance-monitoring/api-endpoints/) |
| **Authorization Code** | *The authorization code is a temporary code that the client will exchange for an access token. The code itself is obtained from the authorization server where the user gets a chance to see what the information the client is requesting, and approve or deny the request.* [*"Authorization Code Grant"*](https://www.oauth.com/oauth2-servers/server-side-apps/authorization-code/) |
| **Access Token** | *Access tokens are the thing that applications use to make API requests on behalf of a user. The access token represents the authorization of a specific application to access specific parts of a user’s data.* [*"Access Tokens"*](https://www.oauth.com/oauth2-servers/access-tokens/) |



[Back to Main](../README.md)