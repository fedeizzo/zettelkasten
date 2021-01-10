---
date: 2021-01-06T08:51
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
  - abac
  - xacml
---

# XACML
XACML stands for extensible access control markup language. It is used to define [[abac]] policies for data sharing across different organizational domains (in reality it can be used to specify more than simple policies, for example decisions and requests).

The main components are:

1. XACML policy language → specify access contro rules + algorithms for combining policies;
2. XACML requests/response protocol → used to query a decision engine that evaluates user access requests against policies. It is composed by attributes of subject, resource, action and environment which is stored inside Policy Information Point (**PIP**);
3. XACML reference architecture → for deployment of software modules to house policies and attributes and compute and enforce control decisions.

Main entities involved in XACML are:

* **resource** → data or system component needing protection;
* **subject** → an actor who requests access to specific resources;
* **action** → an operation on a resource;
* **environment** → properties not belonging to resources, subjects or actions that are important for authorization decisions;
* **attributes** → characteristics of the resource, subject, action or the environment;
* **target** → defines conditions that determinate whether policy applies to the request.

![](./static/xacmlPolicyStructure.png){.ui .image .centered}

As explained in figure above XACML policies are structured as *PolicySets*. Policy may contains:

* Other policies.
* Other PolicySets.

Policies are composed by rules. They are composed as set of boolean conditions that can be evaluated as true/false or indeterminate. Multiple rules can be combined with combining algorithm, the more common are:

* Deny overrides → AND operation on permit;
* Permit overrides → OR operation on permit;
* First applicable → result is the result of the first decision;
* Only one applicable → if more than one decision applies, then the result is Indeterminate.

Finally target defines a boolean condition:

* if true, the request gets evaluated by a **PDP**;
* if false, the decision is **Not Applicable**.

Another important concept is obligation. An obligation describes what must be carried out before or after an access request is approved and denied.
