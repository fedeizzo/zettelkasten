---
date: 2021-01-04T15:44
tags:
  - university/introductionComputerNetworkSecurity
  - cryptography
  - symmetric-key
  - aes
---

# AES (Advanced Encryption Standard)
AES uses a symmetric key crypto scheme called Rijndael, a block cipher designed by Jaon Daemen and Vincent Rijmen. Algorithm can use a variable block and key length:

* key can be 128, 192 or 256 bits;
* block can be 128, 192 or 256 bits;

## Cracking
AES, allowing key more length, is more secure than [[des]]. In AES there are approximately:

* $3.4\times 10^{38}$ possible 128-bit keys;
* $6.2\times 10^{57}$ possible 192-bit keys;
* $1.1\times 10^{77}$ possible 256-bit keys;

Instead in DES there are approximately:

* $7.2\times 10^{16}$ possible keys;

## History
NIST, in 1997, started the develop of AES in order to gain a better cryptosystem for U.S. government applications. AES become a standard in December 2001.
