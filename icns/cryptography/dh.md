---
date: 2021-01-04T08:59
tags:
  - university/introductionComputerNetworkSecurity/cryptography
  - cryptography
  - asymmetric-key
  - diffie-helman
---

# DH (Diffie-Hellman)
DH was invented after RSA and now it is used for secret-key key exchange only, not for authentication or digital signatures. The mathematical trick on which DH rely is the simplicity of computing exponents over computing discrete logarithms.

## Math
Finite field $F=GF(p)=\ integers\ modulo\ p$. At this point exponential is the one way function easy to compute:
$$
x \to g^x (mod\ p)
$$
Instead, the difficult one is **Discrete Logarithm Problem (DLP)**. Given $p,g,X$ find the discrete logarithm $x$ so that
$$
X = g^x mod\ p
$$
where $p$ is prime and $g$ is a generator.

![Dh math](./static/dhMath.png)

## Security
Security of *DH* depends on the difficult of *DLP*. *DH* is a key agreement protocol: assuming that *DHP* is difficult, an attacker observing the messages exchanged does not learn the key.

Another important point is that *DH* does not provide authentication[^auth], parties do not know whom they are establishing a key with. For this reason **Man-In-The-Middle** (MITM) can be used.

![MITM](./static/mitm.png)
