+++
title = "Microservices Arch"
date = "2020-01-20"
draft = false
pinned = false
image = "/img/nodejs.png"
+++
## Build a Timestamp Moicorservice Architechtu
## Microservices
is a pattern for organizing computer systems into servises that can scal with demand.

Back in the 1990's an internet company would run a big monolithic program on a server that the company maintained on-promise

To serve an increase in traffic popular company would simply add more instances of the monolith

Monolithic architectures do have some positive features  
- A monolith centralizes the codebase so it is in one place
- Engineers can step through any part of the code when they are debugging
- Also user requests that are completly served by a monolith do not have to make many calls across a network which reduce the chance of Network failures 

Most software companies have their code in a monolith today
* When those monoliths get big problems can start to occur
- Centralized code leads to right coupling that are hard to break up
- If the program is too big, it will be impossibe torun on a typical machine
- Internet giants in the early 2000s began breaking up their applications into services
instead of scaling the monolithic application, a service oriented architecture could scale the parts of an application that were under load.

Operating system Virtualization made service-oriented architecture more economical

***One server*** could host multiple virtualized operating system instances and each of those instances could run a server, but this also meant that engineers had to manage more and more layers of infrastructure 
the virtual machine hosts, the hypervisor layer and the hardware itself

Failure become more complex, debugging got harder


In 2006 ***Amazon Web Services*** lanched the Elastic Compute cloud
**EC2** allows programmers to rent ***virual machines*** in Amazon's data centers. With Amazon taking care of failures at the hardware level, and the hypervisor level
programmers could focus on the virtual machine hosts themselves where their application code was running

But using an entire virtual machine to run a small piece of application code is wasteful.

**Container** allow a virtual machine to be sliced up into isolated filesystem regions

A container can be as larg as the entire VM or as small as your smallest service. Hence the term micro services

**Micro Service** run in ***containers*** which run on a **virtual machine** which runs on a ***hypervisor*** which runs on a ***server***
Which sits in Iraq, Which sits in a data center, which is a part of a network of data centers called the **cloud**

**Containerized** architecture led to a new problem
Companies that run thousands of micro services in containers on the cloud did not have a simple way to manage them

**Kubernetes** is an open source project from Google that gives engineers a centralized system for managing containers
Kubernetes also makes those services portable
creating a competive tension between Amazon Web Services and Google Cloud Platfrom
both of which can host kubernetes clusters

The days of micro services are just getting started
Software development has never been easier and the two biggest companies in the cloud are competing for users

Its going to keep getting easier and cheaper






VM: