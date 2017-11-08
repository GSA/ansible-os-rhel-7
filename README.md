RHEL 7 GSA Benchmark
====================

This ansible content will configure RHEL/Centos 7 machine to be GSA compliant.

This role **will make changes to the system** that could break things.

For compliance auditing, use a tool such as [nessus](https://www.tenable.com/products/nessus-vulnerability-scanner) or [CIS-CAT](https://learn.cisecurity.org/cis-cat-landing-page)

This code is based on the GSA Red Hat Enterprise Linux Security Benchmark v1.0 and the [CIS RedHat Enterprise Linux 7 Benchmark v2.1.1 ](https://www.cisecurity.org/cis-benchmarks/).

Important Information
---------------------

You should carefully read through the tasks to make sure these changes will not break your systems before running this playbook.

Role Variables
--------------
There are many role variables defined in defaults/main.yml.

##### The current default configuration will:
* Enable IPv6 settings
* Enable iptables
* Enable auditing with rsyslog.
* Lock users inactive for over 30 days.

##### The configuration will not:
* Install and configure AIDE
* Install and configure NTP
* Configure the /etc/group wheel configurations

Other settings and services are listed. Please review to ensure they meet your organizational requirements.

Note, a subset of controls were removed due to operational impact or organizational dependent variables. Those are listed [here](https://docs.google.com/spreadsheets/d/1hHbPDnm5WspzGt6F67_Dw2GgLA1E0-NCAsIGeHJLK7s/edit#gid=0) *Note: Must have a GSA account to access.


Dependencies
------------

Ansible > 2.4

Example Playbook
-------------------------

```
---
- name: Harden Server
  hosts: all
  become: yes

  roles:
    - ansible-os-rhel-7
```
How to test locally
--------------------------
```
ansible-playbook playbook.yml --connection=local
```

License
-------

MIT
