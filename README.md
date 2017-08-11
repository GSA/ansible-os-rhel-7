RHEL 7 GSA Benchmark
====================

## This role is still under development

This ansible content will configure RHEL/Centos 7 machine to be GSA compliant.

This role **will make changes to the system** that could break things. This is not an auditing tool but rather a remediation tool to be used after an audit has been conducted. For complaince auditing, use a tool such as [nessus](https://www.tenable.com/products/nessus-vulnerability-scanner) or [CIS-CAT](https://learn.cisecurity.org/cis-cat-landing-page)

## IMPORTANT INSTALL STEP

Based on the GSA Red Hat Enterpreise Linux Security Benchmark v1.0 and the [CIS RedHat Enterprise Linux 7 Benchmark v2.1.1 - 01-31-2017 ](https://community.cisecurity.org/collab/public/index.php).

This code originated from work done by [Sam Doran](https://github.com/samdoran/ansible-role-stig) and the team at [MindPointGroup](https://github.com/MindPointGroup)

Requirements
------------

You should carefully read through the tasks to make sure these changes will not break your systems before running this playbook.

Role Variables
--------------
There are many role variables defined in defaults/main.yml. This list shows the most important.

By default, many of the variables are turned off. Please review and adjust to meet your organizational requirements.

Note, a subset of controls were removed due to operational impact or organizational dependent variables. Those are listed [here](https://docs.google.com/spreadsheets/d/1hHbPDnm5WspzGt6F67_Dw2GgLA1E0-NCAsIGeHJLK7s/edit#gid=0) *Note: Must have a GSA account to access.


Dependencies
------------

Ansible > 1.9

Example Playbook
-------------------------

```
- name: Harden Server
  hosts: all
  become: yes

  roles:
    - gsa_hardening
```
How to test locally
--------------------------
```
ansible-playbook playbook.yml --connection=local
```

License
-------

MIT
