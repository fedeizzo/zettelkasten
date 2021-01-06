---
date: 2021-01-06T08:51
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
  - abac
---

# ABAC
With a DAC or MAC the complexity grown according the subjects and objects numbers grow. For large number of subjects and objects, the number of authorizations may become very large

![Dac mac problems](./static/dacMacProblems.png){.ui .image .centered}

RBAC resolves these problems using roles. The complexity goes from O(m*n) to O(m+n).

![](./static/rbacOverDacMac.png){.ui .image .centered}

But there is also a problem with RBAC, roles may not be enough for easily expressing authorization conditions.

To solve this problem **Attribute Based Access Control (ABAC)** was invented. ABAC defines authorization that express conditions on properties of both the resource and subject. The main strengths points are:

* flexibility and expressive power;
* possibility to combine different patterns of authorization conditions in a natural way;
* possibility to consider authorization conditions depending on environment attributes.

The three different attribute types are:

* user attributes
* attributes associated with the resource to be accessed
* environment conditions

![ABAC Model](./static/abacModel.png){.ui .image .centered}

In ABAC subjects, objects and environment are associated with attributes and authorization is expressed as conditions on these attributes.

## Policy
Policies are a set of rules that govern allowable behavior within organization. They are based on the privileges of subjects, objects and environments. Typically written from the perspective of the object that needs protection and the privileges available to subjects.

## Attributes
Attributes are applied to different fields:

* subject → a subject is an active entity that causes information to flow among objects or changes the system state. Identity and characteristics are defined by attributes: name, organization, job title, etc.;
* object → an object is a passive information system-related entity containing or receiving information. Access control can take vantage by attributes defined on an object: title, author, date of creation;
* environment → describe the operational, technical, and even situational environment or context in which the information access occurs: current date, current virus/hacker activities, network security level.
