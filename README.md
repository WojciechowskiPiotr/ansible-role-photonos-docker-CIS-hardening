# ansible-role-photonos-docker-CIS-hardening

[![Build Status](https://travis-ci.org/WojciechowskiPiotr/ansible-role-photonos-docker-CIS-hardening.svg?branch=master)](https://travis-ci.org/WojciechowskiPiotr/ansible-role-photonos-docker-CIS-hardening)


Ansible role to harden out-of-the-box VMware PhotonOS installation based on CIS Docker Community Edition benchmark

## Requirements

Root account must be configured and accessible for this version

## Dependencies

None.

## Example Playbook

An example how to use the role in the playbook

```yaml
---
- name: Updating and hardening PhotonOS Docker installation based on CIS
  hosts: all
  gather_facts: no
  vars:
    request_debug_output: false
  roles:
    - ansible-role-photonos-docker-CIS-hardening
```


