---
date: 2021-01-04T08:59
tags:
  - university/introductionComputerNetworkSecurity
  - cryptography
  - asymmetric-key
  - rsa
---

# RSA (Rivest, Shamir, Adleman)
RSA is based on mathematical trick that is easy to compute products compared to computing factorizations. It is used widely for key exchange, digital signatures or encryption of small blocks of data.

RSA uses variable size encryption block and variable size key. Public and private keys are built from a very large number calculated from the product of two primes (from 100 to 200 digits).

## Factorization
Let $p$ and $q$ to large primes. Let $N=p*q$ be the modules. Choose a relatively prime to $(p-1)*(q-1)$ and find $d$ from $e*d=1\ mod\ (p-1)(q-1)$. Public key an private key are respectively:

* $(N,e)$
* $d$

To encrypt plaintext $0<M<N$:
$$
C=M^e mod\ N
$$
To decrypt cipherText $C$:
$$
M=C^d mod\ N
$$
because
$$
C^d mod\ N=(M^e mod\ N)^d mod\ N=M^{e*d} mod\ N=M mod\ N=M
$$
in which N and e is public.

## Vulnerability
In early 2012 a vulnerability over RSA was discovered. It involves key generation including 1024 and 2048 bits length. This vulnerability needs only public key and from that is possible to get the private one. The problem that can insorge are:

* private key can be misused for impersonation of legitimate owner, decryption of sensitive messages, forgery of signatures and other related attacks;
* currently confirmed number of vulnerabilities keys found is about 760.000 but possibly up to two to three magnitudes more and vulnerable.
