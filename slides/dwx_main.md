# Intro
## Rick Rackow

- Lead Site Reliability engineer
- Author: **Operating OpenShift** (O’Reilly)
- Previously: eBay Classifieds Group, Red Hat, TomTom
- Monitoring Lover
- Container Enthusiast

📍 Based in Berlin

🔗 [Blog: https://yelling.cloud](https://yelling.cloud)

🔗 [linkedin.com/in/RiRa12621](https://linkedin.com/in/rickrackow)

🔗 [github.com/rira12621](https://github.com/rickrackow)



---
# Introduction
## Agenda

* Containers and what we can do with them
* Dockerfiles
* Where we find container layers
* What is a layer
* Filesystems
  * UnionFS
  * OverlayFS
* Demo
* More Demo
* Q & A

---
# Entry
## Containers and what we can do with them

* Simplified: just a packaging format when built
* Jailed to a certain extent when running
* Can be used to
  * package applications
  * create
  * ease creation of dev environments
  * Used as "light" version of VM

---
# Entry 
## Containers and what we can do with them


```dockerfile
FROM ubuntu


```
