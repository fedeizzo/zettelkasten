---
date: 2020-12-29T22:10
tags:
  - university/introductionComputerNetworkSecurity/webapps
  - webapps
  - attack
  - phishing
---

# Phishing
The main idea is to trick user into insert personal information inside an evil website copied from the original one. The step used to construct a good evil website are:

* copy HTML
* include images from legitimate web site
* include many links refer back to the legitimate web site
* after stealing login info redirect to legitimate logging inside it
* use a very similar URL (low char changed)

Some counter-measure are:

* help user identify a legitimate sites (highlight https with lock and green)
* certificate authority must thoroughly vet the organization obtaining the certificate preventing look-alike names
* browser provides special indicator for extended validation sites
* browser must use some anti-phishing measures
* implement good monitor traffic in legitimate web site in order to notice if many requests occur from the same point
* legitimate sites can incorporate personal information in emails to authenticate them: phishers won't have such information (in case they have phishing become spear phishing)
