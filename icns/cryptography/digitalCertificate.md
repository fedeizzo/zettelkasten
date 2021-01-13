---
date: 2020-01-13T18:06
tags:
  - university/introductionComputerNetworkSecurity/cryptography
  - cryptography
  - asymmetric-key
  - digital-certification
---

# Digital certificates
A digital certificate is a binding between an entity's Public Key and one or more Attributes concerning its Identity. Entity can be a person, a hardware component, a service, etc.
A digital certificate is issued and signed by someone, usually is a **Trusted Third Party (TTP)**

![Digital certificate](./static/digitalCertificate.png){.ui .image .centered}

The standard for certificate is **X.509** and its main components are:

* Unique ID
* Name
* Signature (Only CA)
* Public Key (Only subject)
* Algorithm used to compute signature/public key

Some questions arise with the use of digital certificate:

* How are digital certificate issued?
* Who is issuing them?
* Why should I trust the certificate issuer?
* How can I check if a certificate is valid?
* How can I revoke a certificate?
* Who is revoking certificates?

All these questions have one answer: **Public Key Infrastructure (PKI)**

## PKI
A PKI is an arrangement that binds public keys with respective identities of entities. This binding is established through a process of registration and issuance of certificates at any by a **Certificate Authority (CA)**. The PKI role that assures valid and correct registration is called a **Registration Authority (RA)**, RA is responsible for accepting request for digital certificates and authenticating the entity making the request. Finally a third-party **Validation Authority (VA)** can provide an entity information on behalf of the CA.

A **Certificate distribution system** is the repository for certificates and the **Certificate Revocation List (CRL)**.

A **Cryptographic Practices Statement (CPS)** is a declaration of the security that the organization is implementing for all certificates issued by the CA holding the CPS.

![PKI](./static/pki.png){.ui .image .centered}

Another interesting definition list (==TODO== choose better version for this zettel):

* CA: Certification Authority, third party that associates an identity with its public key and generates the certificate, signing it
* RA: Registration Authority, responsible for accepting requests for digital certificates and authenticating the entity, assuring valid and correct registration
* VA: Validation Authority, provide entity information on behalf of the CA. Interrogates the CRL, checks signatures, validity and distribution of certificates. Usually it's the browser role
* CPS: Cryptographic Practices Statement, telling everyone which security is implementing for issuing certificates;
* Certification Repository: Where the certificates are stored;
* Certificate Revocation List (CRL): where are stored all the revoked/not valid certificates.
## Obtaining a certificate

1. User-A generates a public and private key-pair or is assigned by some authority in their organization;
2. User-A first request the certificate of the *CA* server;
3. *CA* responds with its certificate including its public key and its digital signature signed using its private key;
4. User-A gathers all information required by the *CA* server to obtain its certificate;
5. User-A sends a certificate request to *CA* consisting of her public key and additional information. The certificate request is signed by *CA*'s public key;
6. *CA* gets the certificate request, verify User-A's identity and generates a certificate for User-A, binding her identity and her public key. The signature of *CA* verifies the authenticity of the certificate;
7. *CA* issues the certificate to User-A.

![PKI](./static/obtainingCertificate.png){.ui .image .centered}

![PKI](./static/obtainingCertificate2.png){.ui .image .centered}
