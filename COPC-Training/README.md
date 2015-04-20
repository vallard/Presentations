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


* Supported OS Images
  * AMI/AKI/ARI (AWS)
  * ISO
  * QCOW2
  * RAW 
  * VMDK (VMware)
  * VDI (Oracle)
  * VHD (Microsoft)

* Guest Formats
  * Disk Format: partition and block data
  * Container Format: Metadata & Block Devices

* Raw VS QCOW2
  * Raw Perf
  * QCOW2: Features:
    * encryption
    * snapshots with delta backing file
    * compression
    * thin provisioned deltas 

* AMI Format
  * Three things
    * AMI: Raw disk
    * AKI: Amazon Kernel image (vmlinuz)
    * ARI: Amazon Ramdisk Image (initrd)


* Image Preparation
  * cloud-init

* Get images:
  https://cloud-images.ubuntu.com/vivid/current/


## Deployment Use Cases

* Chef Example
Example from: https://cloudinit.readthedocs.org/en/latest/topics/examples.html

```bash
#cloud-config
#
# This is an example file to automatically install chef-client and run a 
# list of recipes when the instance boots for the first time.
# Make sure that this file is valid yaml before starting instances.
# It should be passed as user-data when starting the instance.
#
# This example assumes the instance is 12.04 (precise)


# The default is to install from packages. 

# Key from http://apt.opscode.com/packages@opscode.com.gpg.key
apt_sources:
 - source: "deb http://apt.opscode.com/ $RELEASE-0.10 main"
   key: |
     -----BEGIN PGP PUBLIC KEY BLOCK-----
     Version: GnuPG v1.4.9 (GNU/Linux)
     ... some key
     -----END PGP PUBLIC KEY BLOCK-----

chef:

 # Valid values are 'gems' and 'packages' and 'omnibus'
 install_type: "packages"

 # Boolean: run 'install_type' code even if chef-client
 #          appears already installed.
 force_install: false

 # Chef settings
 server_url: "https://chef.yourorg.com:4000"

 # Node Name
 # Defaults to the instance-id if not present
 node_name: "your-node-name"

 # Environment
 # Defaults to '_default' if not present
 environment: "production"

 # Default validation name is chef-validator
 validation_name: "yourorg-validator"
 validation_key: |
     -----BEGIN RSA PRIVATE KEY-----
     YOUR-ORGS-VALIDATION-KEY-HERE
     -----END RSA PRIVATE KEY-----
 
 # A run list for a first boot json
 run_list:
  - "recipe[apache2]"
  - "role[db]"

 # Specify a list of initial attributes used by the cookbooks
 initial_attributes:
    apache:
      prefork:
        maxclients: 100
      keepalive: "off"

 # if install_type is 'omnibus', change the url to download
 omnibus_url: "https://www.opscode.com/chef/install.sh"


# Capture all subprocess output into a logfile
# Useful for troubleshooting cloud-init issues
output: {all: '| tee -a /var/log/cloud-init-output.log'}
```

