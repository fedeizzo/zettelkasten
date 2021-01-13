---
date: 2020-01-13T18:06
tags:
  - university/introductionComputerNetworkSecurity/cryptography
  - cryptography
  - asymmetric-key
  - cie
---

# CIE 3.0
CIE is way to store personal information for different validity periods like:

* name
* surname
* place and date of birth
* residency
* holder's picture
* two fingerprints

CIE supports NFC (Near Field Communication), a short range communication protocols. A NFC device can acta as electronic identity documents and keycards.
CIE supports cryptography. Some of the algorithm are:

* AES
* SHA-2 or SHA-1
* DH 2048 bits
* Elliptic Curve DH 192 bits
* RSA
* X.509 certificate with personal data singed by official CA

One scenario can be Authentication to on-line services by X.509 certificates

![CIE sample](./static/cieSample.png){.ui .image .centered}

## Challenge response authentication
Challenge response authentication is a family of protocols in which one party presents a question ("challenge") and another party must provide a valid answer ("response") to be authenticated.

![Example](./static/challengeResponseAuthentication.png){.ui .image .centered}

This concept can be also extended to one time passwords as $2^{nd}$ factor authentication: generate an OTP by challenge-response mechanism. This contains:

* code with a short expiration;
* proofs of the possession of the OTP generator and/or of the device that received it;
* optionally proofs the knowledge of the PIN used to activate the OTP generator.

![CIE second factor](./static/cieSecondFactor.png){.ui .image .centered}
