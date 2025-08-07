
# Day 10: Deep Dive into SAML and Identity Protocols

## What is SAML?
SAML (Security Assertion Markup Language) is an open standard used for exchanging authentication and authorization data between an Identity Provider (IdP) and a Service Provider (SP). It enables Single Sign-On (SSO), allowing users to log in once and gain access to multiple applications without logging in again.

## What is a Protocol in IAM?
A protocol is a set of rules and standards used for communication between identity systems. In IAM, protocols define how identity and authentication information is exchanged between different entities.

## Common Identity Protocols
### 1. **SAML (Security Assertion Markup Language)**
- **Use case:** Enterprise SSO (corporate systems, internal portals)
- **How it works:** Uses XML to transmit authentication data via SAML assertions between IdP and SP.

### 2. **OAuth 2.0**
- **Use case:** Authorization for APIs and third-party apps (e.g., Google login for a news app)
- **How it works:** Grants access tokens for users to allow specific actions without sharing passwords.

### 3. **OpenID Connect (OIDC)**
- **Use case:** Federated identity with OAuth 2.0 for modern web/mobile apps.
- **How it works:** Extension of OAuth 2.0 that adds user authentication and ID token.

### 4. **WS-Federation**
- **Use case:** Federated identity in enterprise applications (older Microsoft ecosystems)
- **How it works:** Uses SOAP-based web services for exchanging security tokens.

### 5. **Shibboleth**
- **Use case:** Academic and research institution SSO
- **How it works:** Built on top of SAML; widely used in education.

## Components in SAML Flow
- **Identity Provider (IdP):** Authenticates the user and issues the SAML assertion.
- **Service Provider (SP):** Receives the assertion and grants access to the service.
- **Entity ID:** A unique identifier for an IdP or SP in a SAML federation setup.

## How SAML Works – Step-by-Step Flow
1. **User Accesses SP:** The user tries to access a protected resource on the Service Provider.
2. **Redirect to IdP:** SP redirects the user to the Identity Provider for authentication.
3. **User Authenticates:** IdP prompts user for credentials.
4. **SAML Assertion Created:** After successful login, IdP generates a SAML assertion.
5. **Assertion Sent to SP:** The assertion is sent back to the SP via the user's browser.
6. **Access Granted:** SP validates the assertion and allows access.

## Real-Life Use Case (Generic)
A remote employee tries to access their company’s HR portal. They are redirected to the identity provider where they log in using their enterprise credentials. After authentication, they’re redirected back to the HR portal which reads the SAML assertion and grants access — all without another login prompt.

## Technical Touches: What’s Inside a SAML Assertion?
- **Authentication Statement:** Confirms that the user has been authenticated.
- **Attribute Statement:** Contains user attributes like email, role, department.
- **Conditions:** Validity period, audience restriction, etc.
- **Signature:** The assertion is digitally signed to ensure authenticity.

## How It's Performed Using IAM Tools (Generic Process)
1. **Configure IdP and SP:** Register both ends in the IAM tool (like ForgeRock, Saviynt, etc.)
2. **Exchange Metadata:** Share IdP and SP metadata files containing endpoint URLs, certificates, etc.
3. **Define Mappings:** Set up attribute mappings (e.g., map email, department, role).
4. **Setup Entity ID & Certificates:** Configure the unique identifiers and sign/encrypt assertions.
5. **Test SSO:** Launch the login flow and ensure successful redirection and access.
6. **Monitor Logs & Assertions:** Use IAM tool’s dashboard to trace SAML responses and failures.

---

