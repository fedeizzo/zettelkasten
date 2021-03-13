---
date: 2020-12-22T10:05
tags:
  - university/introductionComputerNetworkSecurity/access-control
  - access-control
---

# Access Control

## Definition
Access control is the process of mediating requests to resources and data of system and determining whether a request should be granted or denied.

The flow can be summarized as follow: subject *s* wants to perform action *a* on resource *r*

1. access request *(s, a, r)* is sent to access control module
2. access control module returns grant/deny
3. if response is grant system allow *s* to perform *a* on *r*

The main purpose of *AC* is to protect resources from unauthorized accesses.

## Explanation
Access control can be explained in a very simple way as follow:

![AC](./static/accessControl.png){.ui .image .centered .big}

There are some important boundaries:

* outer one prevent the by-passing of the **Guard**. All authorization must pass through it and some privileges are required in order to by-pass the Guard;
* inner one guarantees the integrity of the audit log. Inside it is written what happen and why. Contrary to the outer boundary, the inner one cannot be by-passed in any way.

A good example can be an operative system. Inside it may be multiple users operating in different environments. The OS must provide some protections between users:

* memory protection
* file protection
* general control and access to objects
* user authentication

So a tradeoff must be set during the design of an OS between *sharing* and *protection*. A three levels of protection are:

* no protection
* isolation → each process own portion of memory, files, etc. And OS provides boundaries
* share → some resources still need to be shared. For example libraries, files, database, etc.

If a share approach is used a good principle is ***Least Priviledge***: every subject must be able to access only the information and resources that are necessary for its legitimate purpose. This principle can be implemented through resource encapsulation and OS can apply it also on users management (not only resources management).

## Structure
The structure of an *AC* is:

* policy → rules that contro what actions, subjects may perform on resources containing information;
* model → formal representation of the policy and its working;
* enforcement → low level functions that implements the controls imposed by the policy.

![AC structure](./static/acStructure.png){.ui .image .centered}

When policy and model are mathematically defined an automated reasoning can be used as enforcement.

## AC models
List of access control models and relative topics:

* [[acm]]#
* [[dac]]#
* [[macACModel]]#
* [[rbac]]#
* [[abac]]#
* [[xacml]]#
