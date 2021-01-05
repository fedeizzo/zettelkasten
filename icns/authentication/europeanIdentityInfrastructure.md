---
date: 2021-01-02T21:34
tags:
  - university/introductionComputerNetworkSecurity/authentication
  - cryptography
  - authentication
  - saml
  - spid
  - EII
---

# European Identity Infrastructure

In the following example an Italian citizen wants to authenticate against a German online service:

1. German eIDAS-Node is directed by the web application to initiate the authentication process
2. it sends a request to the Italian eIDAS-Node
3. Italian eIDAS-Node forwards the user to a system that can used to authenticate him
4. after user authentication German eIDAS-Node receives the citizen's information which it forwards to the web application

The communication between the two eIDAS relies on SAML.

![EID example](./static/eidExample.png){.ui .image .centered}

![EID example 2](./static/eidExample2.png){.ui .image .centered}

## Vulnerability
European commission has provided the eIDAS-Node Integration Package in order to allow each member state to provide its own eIDAS-Node. A vulnerability was found, an attacker can send a manipulated SAML response to an eIDAS-Connector to authenticate as anybody.
Vulnerable code was used to verify the trust of the certificate the SAML response:

1. the certificate is accepted if it is in the local trust store
2. otherwise, the issuer certificate of the entity certificate is retrieved from either the local trust store of from the supplemental certificates in the SAML message
3. if a trust path can be established between the issuer certificate and a certificate in the trust store, the entity certificate is accepted

In step 2 the application does not verify whether the entity certificate has been correctly signed by the issuer certificate. An attacker can therefore sign a manipulated SAML response with a forget certificate
