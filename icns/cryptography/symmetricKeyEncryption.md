---
date: 2020-12-12T10:44
tags:
  - university/introductionComputerNetworkSecurity
  - cryptography
  - symmetric-key
---

# Symmetric key encryption
Symmetric key encryption is based on one single *key* (k) used for **E** and **D**:
$$
D(k, E(k,p)) = p
$$
All receivers have access to key, for this reason the management of keys is the most important and critic phase.

![Symmetric cipher](./static/symmetricCipher.png){.ui .image .centered}

There are two types of ciphers:

* stream ciphers;
* block ciphers.

## Stream ciphers
Encrypt sequences of short data (1 bit/byte) blocks under a changing key stream. Security relies on design of key stream generator and encryption that are computationally simple.

The same plain text bit will be encrypt to a different bit, every time it is encrypted. This types of ciphers is very fast, more than any block ciphers is hardware

![Stream cipher](./static/streamCipher.png){.ui .image .centered}

In the image a simple representation were made using *XOR* operation.

## Block cipher
A block of plain text is treated as a whole and used to produce a ciphertext block of equal length (between 64 and 256 bits).
A message $M$ is break down into multiple blocks $M_1,M_2,\dots , M_n$ and each one is encrypted with the same key $k$.  

## Implementations

* [[[des]]]
* [[[aes]]]
