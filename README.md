Ansible Role: Smallstep CA
========
[![Build Status](https://travis-ci.org/imntreal/ansible-role-smallstep-ca.svg?branch=master)](https://travis-ci.org/imntreal/ansible-smallstep-ca)

This role will deploy and configure Smallstep Certificates.

Requirements
------------

No extra packages required.

Role Variables
--------------

Found in `defaults/main.yml` (can be overridden in inventory):
    smallstep_ca_version: Version of Smallstep Certificates to install
    smallstep_cli_version: Version of Smallstep step cli to install
    smallstep_arch: Architecture to use. Must be amd64, arm64, or arm7.

Required in inventory:
    smallstep_provisioner: Name of initial provisioner to use in CA initialization

Dependencies
------------

No other roles are required

Example Playbook
----------------

inventory:
    all:
      step-ca:
        smallstep_provisioner: imntreal@gmail.com

playbook:
    - hosts: step-ca
      roles: imntreal.smallstep-ca

License
-------

MIT

Author Information
------------------

Jameson Pugh <imntreal@gmail.com>
