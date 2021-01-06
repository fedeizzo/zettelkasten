---
date: 2021-01-06T08:51
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
  - mac
---

# MAC
Model in which user operates in an organization and it is the latter that decides how data should be shared. Usually enforced by using security labels.

![MAC](./static/mac.png){.ui .image .centered}

## Multi-Level Security
Model in which there are various sensitivity levels and users have various degrees of trustworthiness. Them management is made with a policy create to prevent the release of sensitive information to untrusted users.

Information is compartmentalized into separate containers labeled according to their sensitivity label *L = (S, N)* where S takes values over a linearly ordered set. With this technique at creation time a resource is associated to a sensitivity label by resource originator according to some criteria. If a document contain high and low sensitivity information at the same time the label must be the highest sensitivity (at the same time the label can be downgraded).
After label is set the next step is assign clearances in order to choice which users are authorized to access which resources. Each user is associated to a clearance *C = (S, N)* where:

* S is a hierarchical security level indicating the degree of trustworthiness to which the user has been vetted
* N is a set of need-to-know categories indicating domains of interest in which the user is authorized to operate

The policies are defined by using sensitivity labels and clearances. The two property are:

* ***No Read Up Property*** → subject *s* can read resource *r* if *(Ss, Ns)* dominates *(Sr, Nr)*[^domination]. *s* asking to read the content of *r* must show its clearance dominates the sensitivity label of *r*. 
* ***No Write Down Property*** → subject *s* can write to resource *r*  if *(Sr, Nr)* dominates *(Ss, Ns)*. *s* asking to write to a resource must show that its clearance is dominated by the sensitivity label of the resource.

No write down property exist to prevent that a subject to a top Secret file may copy the information into an unclassified file. It is also needed the tranquility principle, it prevents the ability to change security labels arbitrarily as this can subvert security (subject with high levels cannot move into a lower level to pass confidential information).

## Bell-La Padula model
Bell-La Padula model is based on no read up, no write down and tranquility principle.

## Pros and Cons
| Pros | Cons|
|:---:|:---:|
|Not vulnerable to trojans (because no write down)|Information leakage still possible by covert channel|
|Rigid: easy keep control|Rigid: may hinder business continuity|

[^trojan]: Resource R only readable by Alice. Bob induces Alice to run a trojan that can read R and copy information to R' readable by Bob. Bob can rad R' and thus also the information in R.
[^domination]: $(S1, N1)$ dominates $(S2, N2)$ if and only if: $S1 \ge S2 \land N1 \supseteq N2$
