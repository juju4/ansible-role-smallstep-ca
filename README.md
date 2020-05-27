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

    smallstep_version: Version of Smallstep Certificates to install
    smallstep_arch: Architecture to use. Must be amd64, arm64, or arm7.

Dependencies
------------

No other roles are required

Example Playbook
----------------

playbook:

    - hosts: step-ca
      roles: imntreal.smallstep-ca

License
-------

MIT

Author Information
------------------

Jameson Pugh <imntreal@gmail.com>
