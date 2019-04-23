RHEL 7 GSA Benchmark [![CircleCI](https://circleci.com/gh/GSA/ansible-os-rhel-7.svg?style=shield)](https://circleci.com/gh/GSA/ansible-os-rhel-7)
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

Ansible >= 2.7

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
CircleCI Intergration
--------------
This repository has been updated to optionally utilize Continuous Intergration with CircleCI and tests the ansbile tasks against a privledged CentOS-7 Container.  A low number of tasks are incompatiable when ran against a container vs a vm or bare-metal and have ignore_errors turned on.

##### Using CircleCI:
* Fork this repository or create a branch
* Sign up for an account and follow the getting started guide at https://circleci.com/docs/2.0/first-steps/#section=getting-started
* Add the repository to your projects and click start building. https://circleci.com/docs/2.0/project-build/#section=getting-started
* New Commits will trigger the CircleCI build and run the playbook.yml and the result will pass or fail.

License
-------

MIT
