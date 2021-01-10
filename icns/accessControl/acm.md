---
date: 2021-01-06T08:51
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
  - acm
---

# ACM
An **Access Control Matrix** (ACM) can be used to store if a subject can perform some actions on an object.

![ACM](./static/ACM.png){.ui .image .centered}

To check the *ACM* to ways are possible:

* capabilities → user is linked to the file:
    * owned
    * can read
    * can write

![ACM capabilities](./static/capabilitiesACM.png){.ui .image .centered}

* access control list → file is linked to the user that:
    * own it
    * can read it
    * can write it

![ACM access control list](./static/accessControlListACM.png){.ui .image .centered}

There is a vulnerability that exploit the privilege of a file using privilege escalation. A user can use another program to overwrite a file without the permission (only if the program used has the permission to do that).

![Privilege escalation](./static/privilegeEscalation.png){.ui .image .centered}

For this operation following queries are performed:

* (Kenny, x, Compiler)
* (Compiler, r, In)
* (Compiler, w, Bill)

All of these are granted assuming the following ACLs:

* Compiler → [Kenny | x]
* In → [Kenny | o, r, w]
* Bill → [Compiler | w]

So the compiler is delegated by Kenny to read its source file In and at the same tie by the OS to write the billing file Bill.

In order to solve this problem a different ACLs can be used:
* Kenny → [Compiler | x] → [In | r]
* Compiler → [Bill | w]
