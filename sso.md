---
date: 2021-01-02T21:34
tags:
  - university/introductionComputerNetworkSecurity
  - cryptography
  - authentication
  - sso
---

# Single sign on (SSO)
Single sign on was born to overcome the difficult of remember or manager many passwords from many sites/services.
The more security domains[^secDomain], the more sign-ons required

![SSO basic idea](./static/ssoBasicIdea.png)

Main properties are:

* credentials never leave the authentication domain
* service providers (affiliated domains) have to trust the authentication domain
* authentication transfer has to be protected

[^secDomain]: an application or collection of applications that all trust a common security token for authentication, authorization or session management. A security token is issued to user after the user has actively authenticated with a user ID and password to the security domain.
