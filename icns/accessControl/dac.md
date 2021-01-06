---
date: 2021-01-06T08:51
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
  - dac
---

# DAC
Model in which subjects can give rights to other subjects (DISCRETIONARY). DAC is known as too flexible model and is used typically in operating systems.

![DAC](./static/dac.png){.ui .image .centered}

The policy is that owner of a resource decides how it can be shared implemented through ACL.

Groups can be defined in order to simplify the management of users' rights.

## Pros and cons
| Pros | Cons|
|:---:|:---:|
|Flexible|Subjective: owner of a file decide on his taste the protection level|
|Implementation well understood|Vulnerabile to Trojans[^trojan]|
|Intuitive|

[^trojan]: Resource R only readable by Alice. Bob induces Alice to run a trojan that can read R and copy information to R' readable by Bob. Bob can rad R' and thus also the information in R.
