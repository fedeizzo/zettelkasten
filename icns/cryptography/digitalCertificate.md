---
date: 2020-01-14T14:59
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
A PKI is an arrangement that binds public keys with respective identities of entities.

![PKI](./static/pki.png){.ui .image .centered}

* **Certification authority CA** → third party that associates an identity with its public key and generates the certificate, signing it
* **Registration authority RA** → responsible for accepting requests for digital certificates and authenticating the entity, assuring valid and correct registration
* **Validation authority VA** → provide entity information on behalf of the CA. Interrogates the CRL, checks signatures, validity and distribution of certificates. Usually it's the browser role
* **Cryptographic practices statement CPS** → telling everyone which security is implementing for issuing certificates;
* **Certification Repository** → where the certificates are stored;
* **Certificate Revocation List (CRL)** → where are stored all the revoked/not valid certificates.

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

## Usage
Digital certificates are used in [[[sslTls]]] and [[[cie3]]]
