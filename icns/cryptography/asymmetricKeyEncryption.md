---
date: 2021-01-04T09:02
tags:
  - university/introductionComputerNetworkSecurity/cryptography
  - cryptography
  - asymmetric-key
---

# Asymmetric key encryption
Asymmetric key encryption, also known as **Public Key Cryptography**, is a two key crypto system in which two parties could engage in a secure communication over a non-secure communications channel without sharing a secret key.

This is possible because there are functions called **one-way functions** which are easy to compute whereas their inverse function is relatively difficult to compute. Two example are:

* multiplication vs. factorization
* exponentiation vs. logarithms

The basic idea is to use two keys: one to encode and the other to decode

![Asymmetric Cipher](./static/asymmetricCipher.png){.ui .image .centered}

Two keys must be not related, so the knowledge of one does not involve the knowledge of other. One become public and can be viewed and used by anyone, other become private and must be store in a secure way. A this point there are two possibile scenarios:

#### Encrypted message

1. Alice encrypts some information with Bob's public key;
2. only Bob, with his private key, can decrypt Alice's message.

![Process](./static/encryptedMessage.png){.ui .image .centered}

#### Signed message

1. Alice encrypt some plain text with her private key;
2. Bob decrypt the message with Alice's public key. For this reason he knows that Alice sent the message (authentication[^auth]), Alice cannot deny having sent the message (non-repudiation[^non-repudiation]) and also none alters the message during the transit (integrity[^integrity]). 

![Process](./static/signedMessage.png){.ui .image .centered}

## Implementations

* [[rsa]]#
* [[dh]]#

## Pros and cons
Principal pros of Public Key Crypto are:

* private key is only known by the owner;
* integrity [^integrity] and confidentiality by encrypting with receiver's public key;
* non-repudiation [^non-repudiation] by encrypting with sender's public key.

Principal cons are:

* algorithms are 2-3 orders of magnitude slower than those for symmetric encryption;
* how public keys are available to public people;
* problem related to authentication[^auth]. Who ensure pair composed by public-private keys and person is valid?

In order to mitigate the cons a digital signature can be used. A data item that vouches the origin and the integrity of the message. But the use of digital signature introduce a new problem: who guarantees that the one using the key is entitled to do so? This can be solved using digital certificates[^digitalCert]

## Summary
A good summary image that reflect an use-case in real life is:

![Use case](./static/useCaseAsymmetric.png){.ui .image .centered}

In real life hash functions are used, requirements for a hash function are:

* **Ease of computation** → given $x$, it is easy to compute $h(x)$.
* **Compression** → $h$ maps inputs $x$ of arbitrary bit-length to outputs $h(x)$ of a fixed bit-length $n$.
* **One-way** → given a value $y$, it is computationally infeasible to find an input $x$ so that $h(x)=y$.
* **Weak collision resistance** → give an input $x$ and $h(x)$, it is computationally  infeasible to find another input $x' \land x \neq x' \land h(x) = h(x')$.
* **Strong collision collision resistance** → it is computationally infeasible to find any two inputs $x$ and $x'$ with $x\neq x' \land h(x)=h(x')$.

An example could be:

* **GOAL** → protect program $x$
* **IDEA** → compute $h(x)$ and store result in a secure place
* **VERIFICATION** → anytime is possible to recompute $h(x)$ and check the result with the result stored in a secure place, if the outputs are different something was compromised

## Usage
A real usage example of asymmetric key encryption is [[digitalCertificate]]#

[^auth]: you can read more about authentication in [[ciaTrade]]# and [[authentication]]#
[^non-repudiation]: you can read more about non-repudiation in [[ciaTrade]]#
[^integrity]: you can read more about integrity in [[ciaTrade]]#
[^digitalCert]: you can read more about digital certificates in [[sslTls]]#
