---
date: 2020-12-11T15:27
tags:
  - university/introductionComputerNetworkSecurity
---

# Introduction to network and computer security
Introduction to network and computer security course of university of Trento.

Some important and very basic definitions:

#### Information security
Practice of preventing unauthorized access, use, disclosure, disruption, modification, inspection, recording or destruction of information.

#### Computer security
Protection of computer system s and information from harm, theft and unauthorized use. Hardware is protected by some physical tool like doors, locks, etc. Informations instead are protected through some system access control.

#### Network security
Practice of preventing physical and software unauthorized access, misure, malfunction, modification, destruction or improper disclosure of networking infrastructure.

#### Cyberspace
Global domain within the information environment. It involves internet infrastructure, telecommunication networks, computer systems and embedded processors and controllers.

#### Cyber attacks
An attacks targeting an organization use of cyberspace purpose of disrupting, disabling, destroying or maliciously controlling a computing environment/infrastructure.

#### Cyber security readiness (CSR)
Ability to have critical information and tools rapidly available and in place in order to proactively identify any types of attacks or problems. Is a parameter used to remain compliant with policy, regulations and laws.

Systems may fail due various reasons:

* *reliability* deals with accidental failures;
* *usability* addresses problems arising from operation mistakes made by users;
* *security* deals with intentional failures: there is at some stage a decision by a person do something he is not suppose to do.

---

A tool used to identify security levels and context is [[[ciaTrade]]]. Through a study of it is possible to decrease attacks [[[risk]]]. 

Cyber security is based a lot on [[[cryptography]]] concepts.

## Useful questions/tips for exam

* definition and relationships among computer, network and cyber security
* definition of CIA and one example of it
* what is the risk-based approach to security?
* what is a security policy and how does it relate CIA properties? What is a security mechanism?
* what is a cryptosystem?
* why key management is crucial for cryptography?
* what does it mean for a cryptographic technique to be computationally secure?
* what are substitution and transposition ciphers? (with examples)
* what is symmetric cryptography?
* what re block and stream ciphers?
* why is DES deprecated? Why is AES still used?
* what is asymmetric (or public key) cryptography?
* what are the main advantages and disadvantages of symmetric and asymmetric criptography?
* what is RSA and for what is can be used?
* what is Diffie-Hellman and for what it can be used? A possibile attack on it?
* what is a one-way function? One used in RSA and one used in DH
* what are the advantages and disadvantage of Symmetric and Asymmetric Cryptography?
* how can PKC be used to sign messages? What is the role of hash functions?
* what is a digital certificate and what are its main components?
* what is the public key infrastructure and which are its main entities?
* what is SSL/TLS? Where is it used?
* how does the handshake protocol of TLS works? What is the role of DH technique?
* what are the potential security problems of TLS?
* what are the goals of saml?
* what is the structure of a SAML assertion?
* what is a SAML profile? give an example
* what is the difference between IdP-Initiated and SP-Initiated Web SSO?
* what is the flow of an IdP-Initiated Web SSO?
* what is the flow of an SP-Initiated Web SSO?
* what are the main security concerns underlying the deployment of SAML? What are the main mitigations measures?
* what is SPID? What is eIDAS? Is there a relationship between the two?
* Give an example of scenario in which eIDAS is useful
* what is access control and what is its basic architecture
* what is an access control matrix? ACLs? Capabilities?
* what is DAC?
* what is MAC? define no read up and no write down properties
* what are the differences, advantages and disadvantages of DAC and MAC?
* what is RBAC? how does it simplify administration?
* define principle of least priviledge
* what is the confused deputy?
* what is a trojan?
* what is a covert channel?
* how access control can mitigare command injection attacks?
* what is a problem solved by OAuth? Which entities are in involved?
* what is an OAuth token? Is it opaque for which entity involved in OAuth?
* what is ABAC? What is ABAC policy? What are the advantages of ABAC over RBAC?
* what is XACML? What is a XACML target, effect, condition, rule policy and policy set? What are the XACML policy combining algorithms?
* describe the XACML architecture
* what is web application security?
* for which kind of security threats found in web applications, TLS is not an adequate countermeasures?
* which kind of attackers threaten web applications?
* what is an injection attacks, give at least two examples of such an attack
* what is CSRF attack? Give a high level description of how to mount it
* what is XSS attack? Give a high level description of how to mount it
* what is a Phishing attack? Give a high level description how to mount it
* what are the main mitigation measures for injection attacks? And for CSRF attacks? And for XSS attacks? And for Phishing attacks?

## TODO list
- [ ] in cybersec perspectives slides there is a reference to GDPR. Check if the content is the same inside GDPR and privacy slides
- [ ] think to move CIE 3.0 from sslTLS zettel to a new one
- [ ] write better SAML part
