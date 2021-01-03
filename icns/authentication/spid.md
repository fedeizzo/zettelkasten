---
date: 2021-01-02T21:34
tags:
  - university/introductionComputerNetworkSecurity/authentication
  - cryptography
  - authentication
  - saml
  - spid
---

# SPID
SPID means *Sistema Pubblico Identità Digitale*, it is based on SAML 2.0

![SPID](./static/spid.png)

In this system Identity providers are private and there are different type of assurance levels:

* Level 1: some confidence in asserted identity's validity
* Level 2: high confidence in asserted identity's validity
* Level 3: very high confidence in asserted identity's validity

## Register
Register is a repository of all the information related to the entities adhering to the SPID and represents the evidence of the so-called **circle of trust** established therein.
This relationship of trust on which the federation established in SPID is achieved through the intermediation of Agency, third party guarantor, through the process of accreditation of digital identity providers, the attribute authorities and service providers.

So an adhesion to SPID constitutes the establishment of a relationship of trust with all existing members accredited by Agency.

Inside federation registry there is the list of entities that have passed the accreditation process and are therefore part of the SPID federation.

Each entry of the registry, called AuthorityInfo, contains:

* SAML identifier of the entity
* name of the subject to which the federation entity refers
* type of entity (Identity provider, Attribute Authority, Service Provider)
* URL of the metadata provider service
* list of qualified attributes which can be certified by an Attribute Authority
