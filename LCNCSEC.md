# [LCNC-SEC-01: ACCOUNT IMPERSONATION](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-01-Account-Impersonation.md)
## The developers manage both platform and application users 
- The developer creates the service user with a personal account and configures the service user to request data within the platform or third-party services. The application users will 
request data with the developer’s identity.
- The developer creates multiple test accounts using personal or fake email addresses. 
- The developer shares the account with the team.
## How to prevent
- Enforce the least privileges principle to developers. (Prevent developers from having user management permissions)
- Periodically audit user accounts and remove unnecessary or outdated permissions.
- Integrate SAML/SSO authentication in the platform to apply centralized company user access controls. 
# [LCNC-SEC-02: AUTHORIZATION MISUSE](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-02-Authorization-Misuse.md)
## The developer misuses application permissions and roles.
In the multi-tenant application environment, the developer creates role A for application A and grants role A to global access permission in the platform. The application user with role A will implicitly grant existing applications access or future applications in the platform.
## The developer integrates with third-party services with no restriction(full access)
The developer adds the third-party account full access to its service into application service integration. The malicious users in the application could discover the integration API traffics and request service API directly and gain full access to which they do not have access.
## How to prevent
Enforce the least privileges principle to application roles.
Create unique roles per application.
Configure “No Access” by default and avoid granting global access to the roles.
Do not directly call REST APIS from the client side.
Train developers on the risks of third-party service sharing.
# [LCNC-SEC-03: DATA LEAKAGE AND UNEXPECTED CONSEQUENCE](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-03-Data-Leakage-and-Unexpected-Consequences.md)
## The developer creates service integrations into the application.
The developer creates the application to pull the application data via platform APIs or third-party data via service integrations.
The developer adds the third-party integration to export the application data to the third-party location.
## How to prevent
Enforce the least privileges principle to developers. (Prevent developers from having service integration permissions)
Identify application data and determine the sensitivity of data BEFORE building the application
Monitor data traffic on both the platform and the third-party service.
Train developers on data security. 
# Security Misconfiguration
## [LCNC-SEC-04: Authentication and Secure Communication Failure](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-04-Authentication-and-Secure-Communication-Failures.md)
## [LCNC-SEC-05: Security Misconfiguration](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-05-Security-Misconfiguration.md)
## [LCNC-SEC-08: Data and Secret Handling Failures](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-08-Data-and-Secret-Handling-Failures.md)
## The developer integrates with insecure third-party services/APIs.
- The developer configures the third-party service using the insecure protocol(e.g, FTP, telnet, SNMPv1 or v2, etc.).
- The developer configures no authentication service.
## The developer stores secret data in an insecure place
- The developer adds hard-coded secret data to the insecure place in the platform or adds it in the custom code.
- The developer adds secret data into the response message.
## How to prevent
- Enforce the least privileges principle to developers.  (Prevent developers from having service integration permissions)
- Training the developers on the risks of insecure third-party service and security best practices
- Review the application configuration before deploying them to the production environment.
# [LCNC-SEC-06: INJECTION HANDLING FAILURES](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-06-Injection-Handling-Failures.md)
## The developer does not add input validations in the application
- The developer does not add file restrictions on file upload components. The malicious application users can upload malware files to the application.
- The developer does not sanitize user input
- The malicious application user submits injection payloads to the application form. The payload could be exploited on the client side when rendering it or on the server side when passing data to the server side and running the process.
## How to prevent
- Sanitize user inputs
= Training developers on the risks of unsanitized user input and security best practices 
# ASSET MANAGEMENT FAILURES
## [LCNC-SEC-07: Vulnerable and Untrusted Components](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-07-Vulnerable-and-Untrusted-Components.md)
## [LCNC-SEC-09: Asset Management Failures](https://github.com/OWASP/www-project-top-10-low-code-no-code-security-risks/blob/main/content/en/LCNC-SEC-09-Asset-Management-Failures.md)
## Bypass internal security review process
- The developer skips the internal security review and directly uploads custom assets(custom codes/libraries) into the platform.
- The developer installs LCNC templates from the internet.
## How to prevent
- Enforce the least privileges principle to LCNC developers. (Prevent LCNC developers from installing marketplace templates)
- Restrict use of pre-approved marketplace templates or components.
- Maintain platform asset inventories.
- Enforce the internal security review process of the custom asset.
