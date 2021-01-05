---
date: 2021-01-04T15:44
tags:
  - university/introductionComputerNetworkSecurity
  - cryptography
  - symmetric-key
  - des
---

# DES (Data Encryption Standard)
DES is based on **Feistel block-cipher** employing a 56-bit key that operates on 64-bit blocks. DES has 16 rounds of Feistel.

## Feistel
Feistel is a block ciphers base on deterministic algorithm operation on fixed-length groups of bits based on a symmetric key.

### Working
A round of Feistel is composed by:

1. block of plain text to be encrypted is split into two equal-sized halves $(L,R)$;
2. round function $F$ (substitution) is applied on one half using subkey $K$. Then output is XORed with the other half;
3. two halves are then swapped.

![Feistel](./static/feistel.png){.ui .image .centered}

## Cracking
Electronic frontier foundation find that the easiest way to build a practical DES cracker is to have it try every key until it finds the right one. A computer through parallelization can easily find key in a relative short period of time.

## History
Designed by IBM int the 1970s and adopted by NIST in 1977 for commercial and unclassified government applications. It was designed to be faster on hardware than software.
