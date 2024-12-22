Ansible Role: Smallstep CA
========
[![Actions Status - Master](https://github.com/juju4/ansible-role-smallstep-ca/workflows/AnsibleCI/badge.svg)](https://github.com/juju4/ansible-role-smallstep-ca/actions?query=branch%3Amaster)
[![Actions Status - Devel](https://github.com/juju4/ansible-role-smallstep-ca/workflows/AnsibleCI/badge.svg?branch=devel)](https://github.com/juju4/ansible-role-smallstep-ca/actions?query=branch%3Adevel)
[![Build Status](https://travis-ci.org/imntreal/ansible-role-smallstep-ca.svg?branch=master)](https://travis-ci.org/imntreal/ansible-smallstep-ca)

This role will deploy and configure Smallstep Certificates.

Requirements
------------

No extra packages required.

Role Variables
--------------

Found in `defaults/main.yml` (can be overridden in inventory):
* smallstep_ca_version: Version of Smallstep Certificates to install
* smallstep_cli_version: Version of Smallstep step cli to install
* smallstep_arch: Architecture to use. Must be amd64, arm64, or arm7.

Required in inventory:
* smallstep_provisioner: Name of initial provisioner to use in CA initialization

Dependencies
------------

No other roles are required

Example Playbook
----------------

```
inventory:
    all:
      step-ca:
        smallstep_provisioner: imntreal@gmail.com

playbook:
    - hosts: step-ca
      roles: imntreal.smallstep-ca
```

FAQ
---

* List issued certificates
  * `journalctl -xeu step-ca -l --no-pager --since today`
  * [Exporting data out of the badger database of step-ca. ](https://github.com/lukasz-lobocki/step-badger)
  * [Listing all certificates issued by step-ca? #1832](https://github.com/smallstep/certificates/discussions/1832)
* Certificates auto-renewal: https://smallstep.com/docs/step-ca/renewal/
* Monitoring
  * [Telemetry endpoint #790](https://github.com/smallstep/certificates/issues/790), [Implementation of the Prometheus endpoint #1669](https://github.com/smallstep/certificates/pull/1669)

License
-------

MIT

Author Information
------------------

Jameson Pugh <imntreal@gmail.com>
