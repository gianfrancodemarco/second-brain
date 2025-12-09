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
5. 5*Token exchange.** Once approved, the provider issues an ID token (used to identify the user) and sometimes an access token (used to access resources). This step is known as [token-based authentication](https://nordvpn.com/blog/token-based-authentication/).
6. 6.**Application access.** The app receives the tokens, validates them, and grants the user access without needing a separate account or password.

This flow makes user authentication more secure and flexible, while also significantly reducing the number of passwords users need to manage.
### References
https://nordvpn.com/it/blog/what-is-oidc/