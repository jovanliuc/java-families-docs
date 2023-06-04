[Back to Home](../README.md#security)
# OAuth (Open Authorization)
OAuth (Open Authorization) is an open standard protocol
that enables secure authorization and delegation of 
access to resources on behalf of a user. 
It provides a framework for users to grant limited access
to their protected resources to third-party applications
or services without sharing their credentials directly.

The core concept of OAuth revolves around the separation
of the roles involved:

1. Resource Owner: The resource owner is the user who
owns the protected resources, such as personal data or services.

2. Client: The client is the third-party application 
or service that wants to access the protected resources
on behalf of the resource owner.

3. Authorization Server: The authorization server is 
responsible for authenticating the resource owner and 
issuing access tokens to authorized clients.

4. Resource Server: The resource server hosts the protected
resources and validates access tokens to allow or deny 
access to those resources.

The OAuth workflow typically involves the following steps:

1. Registration: The client registers with the authorization 
server and obtains a client ID and client secret, 
which are used to authenticate the client.

2. Authorization Request: The client redirects the resource
owner to the authorization server to request permission 
to access the protected resources.

3. User Consent: The resource owner authenticates themselves 
on the authorization server and grants or denies authorization 
to the client.

4. Access Token Issuance: If the resource owner grants 
authorization, the authorization server issues an 
access token to the client.

5. Resource Access: The client presents the access token
to the resource server when requesting access to the
protected resources.

6. Resource Response: The resource server validates the 
access token and, if valid, provides the requested resources
to the client.

OAuth provides several advantages, including:

- Improved security: User credentials are not shared with 
the client, reducing the risk of password theft.
- User control: Users have the ability to grant or revoke
access to their resources.
- Third-party integration: Developers can leverage 
OAuth to integrate their applications or services with 
popular platforms that support OAuth.

OAuth has become a widely adopted standard for authentication 
and authorization in various domains, including social media
logins, API authorization, and delegated access scenarios.
It allows users to access services from multiple providers
without the need to create and manage separate credentials
for each application or service.
