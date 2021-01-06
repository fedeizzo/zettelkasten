---
date: 2021-01-06T08:51
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
  - rbac
---

# RBAC
## Role Based
Permissions are assigned to roles rather than to individual users, after that roles are assigned to users. This level of indirection simplify the management and provide additional security benefits.

![Role model](./static/roleModel.png){.ui .image .centered}

### Role Definition
A role is a job function within the context of an organization, with some associated semantics regarding the authority and responsibility conferred to the subjects to whom the role is assigned.

### Roles vs groups
Groups are collections of users, roles instead are a collection of users and a collection of permissions.

### User-role-permission relation
The user-role relation is a many-to-many.

The role-permission relation is many-to-many.

### Sessions
A user can invoke multiple sessions and in each session a user can invoke any subset of roles that the user is a member of.

---

## Core RBAC
![Core RBAC](./static/coreRBAC.png){.ui .image .centered}

Where:

* *U, R, P, S* means users, roles, permissions and sessions
* $U\times R \supseteq UA$ is a many-to-many user-role assignment binary relation
* $P\times R \supseteq PA$ is a many-to-many permissions-role assignment binary relation
* $user : S \to U$ is a function mapping each session s to a user
* $roles : S \to 2^R$ is a function mapping each session s to a set of roles roles(s) such that $\{r | (user(s), r) \in UA\} \supseteq roles(s)$
* $permissions: S \to 2^P$ is a function mapping each sessions s to a set of permissions(s) which is the union of the set $\{p | (p, r) \in PA\}\ \forall r \in roles(s)$

## RBAC
![RBAC](./static/RBAC.png){.ui .image .centered}

Where:

* *U, R, P, S, UA, PA* same as core RBAC
* $R\times R \supseteq RH$ is a partial order on R
* $roles : S \to 2^R$ is a function mapping each session s to a set of roles roles(s) such that $\{r | \exists\ r'\ s.t.r' \ge r \land (user(s), r') \in UA\} \supseteq roles(s)$
* $permissions: S \to 2^P$ is a function mapping each sessions s to a set of permissions(s) which is the union of the set $\{p | \exists\ r'\ s.t.r \ge r' \land (p, r') \in PA\}\ \forall r \in roles(s)$

In RBAC there are some constraints: separation of duty (SoD). They are known also as 4 eyes principle, it is widely recognized and captures conflic or interest policies to restrict authority of a single entity (key of fraud prevention).

The main pros and cons are:

| Pros | Cons|
|:----:|:---:|
|Easy to grasp the idea of roles|Difficult to decide the granularity of roles|
|Easy to mange in principle|Role meaning is fuzzy|
|Easy to tell through roles which permissions a subject has and way||
