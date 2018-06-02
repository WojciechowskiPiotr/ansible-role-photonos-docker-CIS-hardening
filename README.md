# docker-CIS-hardening

[![Build Status](https://travis-ci.org/WojciechowskiPiotr/docker-CIS-hardening.svg?branch=master)](https://travis-ci.org/WojciechowskiPiotr/docker-CIS-hardening)
[![GitHub license](https://img.shields.io/github/license/WojciechowskiPiotr/docker-CIS-hardening.svg)](https://github.com/WojciechowskiPiotr/docker-CIS-hardening/blob/master/LICENSE)


Ansible role to harden out-of-the-box Docker installation. Initial version is dedicated for VMware PhotonOS installation based on CIS Docker Community Edition benchmark

Please note this is an early stage version of the role. This role harden the configuration of PhotonOS minimal installation based on results of the scan. 

OS compatibility
----------------

* VMware PhotonOS 2.0


Benchmark version
-----------------

This role implements benchmark v1.1.0 for Docker Community Edition

Requirements
-----------------


Root account must be configured and accessible for this version
This role should be used only on fresh PhotonOS installation

Dependencies
-----------------


docker-py >= 1.7.0
This role uses [[docker-bench-security]](https://github.com/docker/docker-bench-security) for CIS benchmark

Install
-------

```sh
ansible-galaxy install WojciechowskiPiotr.docker-CIS-hardening
```

Example Playbook
-----------------

An example how to use the role in the playbook

```yaml
---
- name: Updating and hardening PhotonOS Docker installation based on CIS
  hosts: all
  remote_user: root
  gather_facts: no
  vars:
    request_debug_output: false
  roles:
    - docker-CIS-hardening
```
The role is thoroughly tagged so that you can run certain sections or certain levels of checks:

Test only items from section 4
```sh
ansible-playbook -i hosts -C playbook.yml -t section4
```   

Apply changes only from items in section 4, 5, and 6
```sh
ansible-playbook -i hosts playbook.yml -t section4,section5,section6
``` 
