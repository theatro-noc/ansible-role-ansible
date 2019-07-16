# ansible-role-ansible

Ansible role to automate upgrading Ansible and necessary libraries.

## Requirements

This role currently supports these distros: Debian/Ubuntu, RedHat/CentOS, and Photon.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    update_package_cache: True

Whether to update the aptitude, yum, pacman or other package cache before running any install tasks.

    ansible_services:
      - lxdm

The services (that should get installed and loaded in addition to basic Ansible needs.
For instance, lxdm will install and set enable the Lightweight X Desktop Manager for
login and general window services on a development machine.

## Example playbook

```
---
- hosts: ansible
  become: True
  connection: local
  roles:
    - ansible
    - repo
  vars:
    - aptitude_update: False
```

# License and Copyright
 
Copyright 2015 VMware, Inc.  All rights reserved.
Copyright 2018 Theatro Labs, Inc.

SPDX-License-Identifier: Apache-2.0 OR GPL-3.0-only

This code is Dual Licensed Apache-2.0 or GPLv3

## Author Information

This role was created in 2015 by [Tom Hite / VMware](http://www.vmware.com/).
Modified by [Jacob Floyd](https://github.com/cognifloyd), employed by [Theatro](theatro.com), in 2018.
