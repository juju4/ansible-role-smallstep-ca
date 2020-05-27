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

Found in `vars/main.yml`:

    epic_users: Local Epic specific accounts to be setup on each ODB server.

Variables set only in inventory:

    CacheInstances: List of instances on server.
    epic_passwords: Password hashes for local accounts. Hashes for RHEL 7 can be
      generated using: openssl passwd -6 on openssl v1.1 or newer or examples found
      here: https://unix.stackexchange.com/a/76337/358648

Dependencies
------------

No other roles are required

Example Playbook
----------------

inventory:

    ---
    all:
      step-ca:
        CacheInstances:
          - 'prd'

        EpicEnvironments:
          - { Instance: 'PRD', Environment: 'PRD' }

playbook:

    - hosts: step-ca
      roles: imntreal.smallstep-ca

License
-------

MIT

Author Information
------------------

Jameson Pugh <imntreal@gmail.com>
