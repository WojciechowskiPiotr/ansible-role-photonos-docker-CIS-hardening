# ansible-role-photonos-docker-CIS-hardening

[![Build Status](https://travis-ci.org/WojciechowskiPiotr/ansible-role-photonos-docker-CIS-hardening.svg?branch=master)](https://travis-ci.org/WojciechowskiPiotr/ansible-role-photonos-docker-CIS-hardening)


Ansible role to harden out-of-the-box VMware PhotonOS installation based on CIS Docker Community Edition benchmark

Please note this is an early stage version of the role. This role harden the configuration of PhotonOS minimal installation based on results of the scan. 

## Requirements

Root account must be configured and accessible for this version
This role should be used only on fresh PhotonOS installation

## Dependencies

docker-py >= 1.7.0

Install
-------

```sh
ansible-galaxy install ansible-galaxy install WojciechowskiPiotr.photonos-docker-CIS-hardening
```

## Example Playbook

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
    - photonos-docker-CIS-hardening
```


