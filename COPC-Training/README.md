# COPC Training

## Technical Architecture Overview

* Remote Monitoring Access
* Availability Zones
  * What's in an Availability Zone
* Hardware Requirements
* Cloud Controller Architecture
  * Corosync, Pacemaker, HA Proxy, Keep-Alive
* Cloud Controller failure scenarios
* MultiTenant / Multi Project
  * Each Project is its own VLAN
* Networking Options
  * Hardware Gateway
  * COPC Gateway 
* Storage Options
  * Ephemeral
  * Ceph
  * NFS
* Enhancements To Dashboard

## How to use COPC as a cloud user

* Navigating Dashboard
* Overview
  * Show limits that were given by administrator
  * Show instances history
* Instances
  * Show clicking on current instance
    * Show security groups, etc
  * Create a new instance

* Orchestration (Heat)

```shell
heat_template_version: 2015-04-20

description: Simple template to deploy a single compute instance

resources:
  my_instance:
    type: OS::Nova::Server
    properties:
      key_name: tco-gold 
      image: "Ubuntu 14.04"
      flavor: m1.small
```

## Cloud OS Images

* Get images:
  https://cloud-images.ubuntu.com/vivid/current/


## Deployment Use Cases
