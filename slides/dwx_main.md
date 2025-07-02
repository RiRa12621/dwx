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
* Container Layers
  * Where to we find them
* Filesystems
  * Union Filesystem
  * OverlayFS
* Demo
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
FROM golang

WORKDIR /app

COPY . .

RUN go get -v && \
      CGO_ENABLED=0 GOOS=linux go build -o dwx

RUN ./dwx
```

---

# Container Layers
## Where do we find them?

** Everywhere **


---
# Container Layers
## Where do we find them?

* Running containers are made of layers
* Every instruction in dockerfile creates a new layer
* Should we optimize for amount of layers?

---
# Container Layers
## Where do we find them?

Example from before: 

```dockerfile
FROM golang

WORKDIR /app

COPY . .

RUN go get -v && \
      CGO_ENABLED=0 GOOS=linux go build -o dwx

RUN ./dwx
```

---
# Filesystems
## Union Filesystem

* Also called "union mount"
* Not an actual filesystem, just the concept
  * Multiple sources "virtually" get merged into a single result
* Where could this be useful?
  * `/home/rick` and `/home/mywife` get mered into `/newHome`

---
# Filesystems
## Overlay and friends

* Actual implementations:
  * UnionFS
    * git.fsl.cs.sunysb.edu dead so most likely dead as a whole
  * OverlayFS
    * part of the kernel :yay:
    * used by docker storage driver `overlay2`
    * better performance than other drivers
    * very efficient use of page cashes
  * aufFS
    * Re-implementation of UnionFS
    * used to be default for docker
    * reject from mainline Kernel
    * Advantages:
      * shares images across running containers
        * fast startup times
        * little space usage
  * More:
    * zfs
    * btrfs
    * ...
