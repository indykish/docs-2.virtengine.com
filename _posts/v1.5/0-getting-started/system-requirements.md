---
title: "System Requirements"
excerpt: ""
---

In order to offer the most to your clients, we recommend that you utilize our recommended setup in order to achieve:

  - Performance
  - Scalability
  - High availability 

#Architecture Overview

We assume that your physical hardware supports Virtualization, which is the only specific system requirement. 

![VirtEngine Architecture for building a public cloud](/images/architecture-overview.png "System Architecture for VirtEngine")

Minimal: 

![VirtEngine Minimum System requirements for Public Cloud](/images/minimal.png "Minimum System Requirements for VirtEngine")

| Application                     | Description                                                                                     | Quantity                     |
| ------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------- |
| Master                          | Hosts our Software Stack, such as our provisioning engine and front-end etc.                    | 1                            |
| Compute Node - Virtual Machines | A compute node to host virtual machines                                                         | > 1                          |

Recommended:

| Application                     | Description                                                                                     | Quantity                       |
| ------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------ |
| Master                          | Hosts our Software Stack, such as our provisioning engine and front-end etc.                    | 1                              |
| Slave                           | Slaves are additional nodes that host the VirtEngine software, they can be used to loadbalance the platofm or       | 1                              |
| Compute Node - Virtual Machines | A compute node to host virtual machines                                                         | > 1                            |
| Compute Node - Containers       | A compute node to host containers                                                               | > 1                            |
| Storage Node                    | A storage node to power High Availability & Storage Solutions                                   | > 1                            |
| Failover Node                   | A compute node that is on idle, it is utilized for high availability when a compute node fails. | > 1 for every 10 compute nodes |

##High Availability Requirements

Achieving High Availability adds onto your system requirements, in order to support High Availability your storage will need to be setup in a specific way. And you need to support a strong private network 
in order to backup data on the go and retrieve them when required.

Minimal: 

* 2xHDD (or) 2xSSD per Compute Storage Node

or 

* 1xHDD (or) 1xSSD per Compute Node
* 2xHDD (or) 2xSSD Storage Node (SAN)

and

* 1GBps Private Network capacity.

Recommended:

* 1xSSD & 2xHDD (or) 3xSSD per Compute Node - Seperate the OS in an SSD Drive from the Virtual Machine storage

or

* 1xSSD & 1xHDD (or) 2xSSD per Compute Node
* 4xHDD (or) 4xSSD Storage Node (SAN)

and

* 10GBps Private Network capacity.


##System Requirements

Just have a look at the tables below for the minimum & recommended hardware requirements.

###Standard Setup: 

Minimal Setup: 

|                      | CPU (Cores)   | RAM (GB)     | HDD                                |
| -------------------- | ------------- | ------------ | ---------------------------------- |
| Master (VM)          | 2/4           | 4-8GB        | 1xHDD (160GB) (or) 1xSSD (160GB)   |
| Slave (VM)           | 2/4           | 4-8GB        | 1xHDD (160GB) (or) 1xSSD (160GB)   |
| Compute/Storage Node | > 8/16        | > 16GB       | > 1xHDD (500GB) (or) 1xSSD (240GB) |
| Failover Node        | > 4/8         | > 16GB       | > 1xHDD (500GB) (or) 1xSSD (240GB) |

Recommended Setup: 

|                      | CPU (Cores)   | RAM (GB)     | HDD                                |
| -------------------- | ------------- | ------------ | ---------------------------------- |
| Master (VM)          | 8             | 16-32GB      | 1xSSD (240GB)                      |
| Slave (VM)           | 8             | 16-32GB      | 1xSSD (240GB)                      |
| Compute/Storage Node | > 8/16        | > 64GB       | > 3xHDD (2TB) (or) 3xSSD (750GB)     |
| Failover Node        | > 8/16        | > 64GB       | > 2xHDD (2TB) (or) 2xSSD (750GB)     |

###SAN Setup:

Minimal Setup (SAN): 

|               | CPU (Cores)   | RAM (GB)     | HDD                                |
| ------------- | ------------- | ------------ | ---------------------------------- |
| Master (VM)   | 2/4           | 4-8GB        | 1xHDD (160GB) (or) 1xSSD (160GB)   |
| Slave (VM)    | 2/4           | 4-8GB        | 1xHDD (160GB) (or) 1xSSD (160GB)   |
| Compute Node  | > 4/8         | > 16GB       | > 1xHDD (500GB) (or) 1xSSD (240GB) |
| Storage Node  | > 2/4         | > 8GB        | > 2xHDD (500GB) (or) 2xSSD (240GB) |
| Failover Node | > 4/8         | > 16GB       | > 1xHDD (500GB) (or) 1xSSD (240GB) |

Recommended Setup (SAN): 

|               | CPU (Cores)   | RAM (GB)     | HDD                                |
| ------------- | ------------- | ------------ | ---------------------------------- |
| Master (VM)   | 8             | 16-32GB      | 1xSSD (240GB)                      |
| Slave (VM)    | 8             | 16-32GB      | 1xSSD (240GB)                      |
| Compute Node  | > 8/16        | > 64GB       | > 2xHDD (2TB) (or) 2xSSD (1TB)     |
| Storage Node  | > 8           | > 16GB       | > 4xHDD (2TB) (or) 4xSSD (1TB)     |
| Failover Node | > 8/16        | > 64GB       | > 2xHDD (2TB) (or) 2xSSD (1TB)     |

Compute & Storage nodes are scalable, which means you can add more servers to form a cluster.

Compute Servers can either be used for Virtual Machines, or Containers. 

> We currently support Ubuntu Trusty 14.04, and Xenial 16.04, beta support available for Centos 7.1 7 Debian Jessie.

##Topology

The following depicts a 3 Node topology.  The storage can be in master/slave if you have more drives.

![VirtEngine System Architecture for Public Cloud](/images/systemarchitecture.png "System Architecture VirtEngine Dash")