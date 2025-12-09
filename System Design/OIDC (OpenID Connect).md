OIDC, or OpenID Connect, is an [[Authentication vs Authorization|authentication]] protocol built on top of [OAuth 2.0](https://nordvpn.com/blog/what-is-oauth-2-0/). It enables applications to verify a user’s identity based on information given by an identity provider (such as Google or Microsoft) and to obtain basic profile details in a secure way. Unlike simple logins, OIDC provides a standardized process that lets users access multiple services with a single set of user credentials, reducing password fatigue while improving overall user authentication security.

### OIDC examples

You may not notice it, but OIDC is behind many of the login buttons you see every day. When you click “Sign in with Google,” “Continue with Apple,” or “Log in with Microsoft,” the application relies on an OpenID provider to authenticate users and confirm their identity. 

The provider works with an authorization server to issue an ID token and sometimes an access token, which the app uses to complete the login.

Popular platforms that use the OpenID Connect protocol include:

- Google — the most widely recognized OpenID provider.
- Microsoft Azure Active Directory — used by businesses for secure single sign-on.
- Apple ID — built into devices and apps across the Apple ecosystem.
- Amazon Cognito — helps developers add [user authentication](https://nordvpn.com/blog/what-is-user-authentication/) to apps and websites.

## How does OIDC work?

OIDC works by connecting an application with an identity provider to verify a user’s identity. The process involves tokens, scopes, and an authorization server that coordinates the login.

The authentication flow typically follows these steps:

1. **User login.** The user clicks “Sign in with Google” (or another provider) on an app or website.
2. **Authorization request.** The app redirects the user to the authorization server of the chosen provider, which manages the authentication process.
3. **User authentication.** The provider verifies the user’s identity by checking their credentials.
4. **Scopes and consent.** The app requests certain scopes (such as email address or profile information), and the user may be asked to approve sharing that data.
5. **Token exchange.** Once approved, the provider issues an ID token (used to identify the user) and sometimes an access token (used to access resources). This step is known as [token-based authentication](https://nordvpn.com/blog/token-based-authentication/).
6. **Application access.** The app receives the tokens, validates them, and grants the user access without needing a separate account or password.

This flow makes user authentication more secure and flexible, while also significantly reducing the number of passwords users need to manage.

### What are the main components of OIDC?

The OpenID Connect protocol involves three main components that work together to complete the authentication process:

- End user — the person who wants to log in to an application.
- OpenID provider — the trusted service, like Google or Microsoft, that verifies the user’s identity through its authorization server.
- Relying party — the application or website that relies on the provider to authenticate users and grant access.

These three parts communicate through ID tokens and sometimes access tokens, making it possible for users to sign in securely with the same identity across different platforms.

## OIDC Flows

OIDC offers different “flows,” or login patterns, that describe how tokens are exchanged between the app or website, the OpenID provider, and the user. Each flow defines the steps an application takes to authenticate users and request the right type of token, such as an ID token for identity or an access token for protected resources. The most common option is the authorization code flow, but other flows exist to suit different devices, apps, and security needs.

### OIDC authorization code flow

The authorization code flow is the most common and secure way to use OIDC. The application receives an authorization code from the authorization server, then exchanges it for an ID token and an access token to authenticate the user. This method is widely recommended for web and mobile apps that need strong protection.

![](https://miro.medium.com/v2/resize:fit:1400/1*Pxdsn71Qm1liZu6glfvjag.png)

### Implicit Flow

The implicit flow was designed for browser-based apps that cannot safely store a client secret. Tokens are returned directly to the application without an extra exchange, which makes it faster but less secure. Because of these security risks, implicit flow is less common today and often replaced by other flows.

![](https://miro.medium.com/v2/resize:fit:1400/1*kNt-5dQ5GjNPNgl98QmVkg.png)

### Hybrid Flow

The hybrid flow combines elements of both the authorization code and implicit flows. It lets the application receive some tokens right away while still using a code exchange for added security. This exact balance makes it useful for apps that need both speed and reliability.

### Client Credentials Flow

Client credentials flow is used when an application needs to authenticate itself rather than a user. In this case, the app communicates with the OpenID provider to get an access token, which it uses to connect securely to protected resources. Client credentials flow is commonly used for server-to-server communication.


## References
https://nordvpn.com/it/blog/what-is-oidc/
https://darutk.medium.com/diagrams-of-all-the-openid-connect-flows-6968e3990660