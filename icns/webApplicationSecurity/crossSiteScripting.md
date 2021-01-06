---
date: 2020-12-27T21:05
tags:
  - university/introductionComputerNetworkSecurity/webapps
  - webapps
  - attack
  - cross-site-scripting
  - xss
---

# Cross-Site Scripting XSS
An attacker attaches a script with an HTTP response. The script is executed in an environment which may contain some privileged information, for example read cookie of a web application. Since cookie often contain authentication information this can be a problem.

There are two XSS variants:

* **Reflected** → using a constructed URL
* **Stored** → using POST to store the bad URL inside a comment/forum

Main mitigation is to filter all input parameters from HTTP GET and POST (even when using client-side validation). This can be made using regex patterns for example.
