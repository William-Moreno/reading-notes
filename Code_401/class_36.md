# Application State with Redux

## What are the advantages of storing tokens in "Cookies" vs "Local Storage"?

- Size Constraints - Even when usting JWTs, cookies' size limitation of 4kb is more than enough for storing session tokens
- Automatic Management - Unlike local storage, cookies are automatically saved, sent and removed by the browser
- Server-side Rendered Apps - Only cookies are sent when doing browser-level navigation, local storage won't work
- Sharing the Same Session Across Subdomains - This can be achieved easily by properly setting the cookie domain
- No Token Misuse via XSS Atack - because cookies have a httpOnly flag, frontend JS cannot read the cookie's value

[SuperTokens](https://supertokens.io/blog/cookies-vs-localstorage-for-sessions-everything-you-need-to-know)

## Explain third party cookies

Third-party cookies are cookies that are set by a website other than the one you are currently on. The most common third-party entities are advertisers, marketers, and social media platforms.

[Cookie Script](https://cookie-script.com/all-you-need-to-know-about-third-party-cookies)

## How do Pixel Tags Work?

When a user opens an email, visits a website, views your digital ad, or takes any other action, they are actually requesting the server to download any tracking pixel which happens to be attached to the content. These tracking pixels are commonly used for marketing.

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **cookies** | *a small piece of data stored on the user's computer designed to be a device used to remember stateful information or to record the user's browsing activity* [Wikipedia](https://en.wikipedia.org/wiki/HTTP_cookie) |
| **authorization** | *the process of designating what resources a particular authenticated user has access to* |
| **access control** | *a system such as RBAC (role-based access control) which uses assigned roles which already have associateed profiles detailing the authorization, or resources they have access to. A given user then merely needs to be assigned one of these roles to define what acess or aurthorization they have.* |
| **conditional rendering** | *Conditional rendering is a term to describe the ability to render different user interface (UI) markup if a condition is true or false. In React, it allows us to render different elements or components based on a condition.* [Digital Ocean](https://www.digitalocean.com/community/tutorials/7-ways-to-implement-conditional-rendering-in-react-applications) |


[Back to Main](../README.md)