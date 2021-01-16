---
date: 2020-12-29T22:10
tags:
  - university/introductionComputerNetworkSecurity/webapps
  - webapps
---

# Web application security
Web application security is very complex because is related to many levels:

* database
* server
* application
* network

And for each level there are several attacks to consider:

| Application layer | Server layer | Network layer | User layer |
|:--:|:--:|:--:|:--:|
|SQL injection|Denial-of-Service (DoS)|Packet-Sniffing|Phishing|
|Cross-Site-Scripting (XSS)|OS expoitation|Man-In-The-Middle Attacks (MITM)|Key-logging|
|Cross-Site Request Forgery (CSRF)||DNS Attack|Malware|
|Broken authentication||||
|Unvalidated input||||

The security requirements remain the same:

* *Authentication* → you want to know who you are communicating with
* *Authorization* → user must have access to only those resources that they are entitled to
* *Confidentiality* → you want to keep information secret
* *Integrity* → you want to know that a message has not been modified in transit
* *Non-repudiation* → if someone has sent a message, it should be impossible to deny it later

## Definition
Web applications is a branch of information security that deals specifically with security of websites, web applications and web services. It applies application security in a Internet and web systems contexts. Application security has the role of finding, fixing and preventing security vulnerabilities.

## Goals
The main goals are:

* safely browse the web
* support secure web apps
* support secure mobile apps

## Attacks
Here are listed some known attacks:

* [[[injection]]]
* [[[crossSiteScripting]]]
* **Cross Site Request Forgery (CSRF)** → send a victim with a specially-crafted URL that contains a malicious request for a target site. Attacker relies on cookie existence and through malicious URL trap user into doing something he does not aspect. The main mitigations are:
    * check every URLs before open them (user persecutive)
    * implement some challenge-response o high-value function, like CAPTCHA (programmer perspective)
* **Unvalidated input** → clients can easily circumvent checks in the HTML code itself and hidden parameters and JS code. For this reason client-side validation is only helpful for performance reasons and not for security ones. The solution is to never trust an input from the user, you always have to check server-side.
* **Broken authentication** → usernames and password combinations are very commonly used an commonly broken. Collection of leaked ones can be found on Internet. Main mitigations are:
    * disallow weak passwords
    * use a stronger hash algorithm
    * salt the passwords
    * use https for encrypting session identifiers to prevent MITM
    * do not expose credentials in untrusted locations
    * implement account lockouts
    * implement multi factor authentication
* **Session management** → poor management of session can bring to problems listed until now. A session identifier must be considered as an important assets that must be managed with strict timeouts and other techniques. Session identifiers are stored inside cookie, so also cookies management become important. Cookie security can be implemented through:
    * use *Domain* and *Path* attributes to restrict the scope of cookies to narrow subdomains
    * use *Secure* attribute to force browsers to send cookies over HTTPS
    * use *HttpOnly* attribute to prevent scripts from accessing the cookies
    * use *X-XSS-Protection* header to allow browsers to detect XSS attacks
    * use *Content-Security-Policy* headers to instruct browsers to only load resources whitelisted locations 
* [[[phishing]]]

## Access control
Also access control is very important for web apps security. In 2017 a data breach of Equifax exposes personal information of 146.6 million of Americans.

Thought an exploited bug in the file upload mechanism a command injection attack was possible and any command can be launched. The solution to the problem was known before attacks and for this reason the usage of OWASP Dependency check could have avoid the breach. Another possible mitigation is apply *little privilege as possible principle*. If it was applied and command have been injected though a user with low privilege the situation could have be better.

### Scenario explained
Image a simple web application delivering content about three page:

* Topic T1
* Topic T2
* Topic T3

In each page there are three sections corresponding to three categories:

* Base
* Middle
* Advanced

![](./static/acWebAppSec.png){.ui .image .centered}

Users can subscribe to one or more topics and can choose the category.

User subscribed to Base content can see only Base content.
User subscribed to Middle content can see both Base and Middle content.
User subscribed to Advanced can see everything.

A good RBAC scheme is:

![](./static/rbacWebSec.png){.ui .image .centered}

And UA (user-role assignment) table is:

|User|Role|
|:--:|:--:|
|User1|R_Page_T1_Mid|
|User1|R_page_T2_Adv|
|User2|R_Page_T3_Bas|
|User3|R_Page_T1_Adv|
