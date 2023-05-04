# Kubernetes

- helps you to deploy app
- operates on two nodes: master & slaves
- One of the main components of its architectiure is the worker servers or nodes: which is a simple server/vm - basic component 

Each nodes as multiple **pods** running on it. (*creates this running environment or a layer on the top of the container*)
>  They are the one that actually do the work.

They have three process that must run on it:
- Container runtime need to be installed on every node 
- but the **process that schedules** it is **kubelet** (*a process of kubernetes that interact with the container runtime and the machine*)

The way communication between the nodes work is by services which is sort of a load balancer that catches the request directed to the app and forwards it to the pod

- **Kube Proxy** *responsible for fowrading request* 

## **Master Processes** 
is one that manages processes. They have four processes:
- **API Server** - client inetracts with it(*more of a cluster gateway*). IT gets the request from the client and acts as a gatekeeper for authetication. After validating your requests,it hands it to the: 
- **Scheduler** - decides on which node new pods should be scheduled and start the application on the node (_Answers_ *Where dto put the pod*)
- **Controler Manager** - Detects when pods on a node dies and reschedules them. (*It detects state cluster changes*)
- **etcd** - A key value store of a cluster state(i.e stores the cluster info). It's the cluster brain

> **Ingress** handles every incoming request
## Benefits of Kubernetes
1. High availability - works on replication
2. Diaster recovery - crates etcd backup and keeping it on remote storage by an adminstaration