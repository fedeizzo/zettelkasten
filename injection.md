---
date: 2020-12-27T21:25
tags:
  - university/introductionComputerNetworkSecurity
  - webapps
  - attack
  - injection
---

# Injection
The most famous type of injection is **SQL Injection**. The main goal is to get data from app db by tricking the SQL interpreter with a carefully crafted query.

The main problem is that client inputs SQL code using parameters (for example a form). Then these parameters are used to dynamically construct SQL queries.

The main consequences are:

* loss of confidentiality → attackers can access sensitive data
* authentication and authorization → attackers can gain access to privileged accounts or systems without passwords
* integrity → attackers can modify the information stored in the database

Two possible mitigations are:

* input sanitization (escaping arguments)
* apply the principle of least privileged
