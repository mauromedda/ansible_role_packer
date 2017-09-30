ansible_role_packer
===================

This is a simple ansible role to install packer into a RedHat-like 7+ box.


Requirements
------------

This module hasn't specific requirements just Ansible.

Role Variables
--------------

```yaml
packer_version: 1.1.0
```
 * packer_version: Specify the packer version to install

```yaml
packer_dist_file: "packer_{{packer_version}}_linux_amd64.zip"
```
 * packer_dist_file: Terraform distribution archive

```yaml
packer_repo_url: "https://releases.hashicorp.com/packer/{{packer_version}}/{{ packer_dist_file }}"
```
 * packer_repo_url: Terraform distribution URL. Used to fetch the Terraform binary

```yaml
packer_base_install_dir: /opt/hashicorp/packer
```

 * packer_base_install_dir: Root of the Terraform installation

```yaml
packer_bin: /usr/bin/packer
```
 * packer_bin: Terraform binary location

```yaml
packer_requirements:
  - unzip
```

 * packer_requirements: Terraform playbook requirements

```yaml
packer_purge_old: true
```

 * packer_purge_old: Delete the oldest version installed in the system. Default: true

```yaml
packer_cleanup: true
```
 * packer_cleanup: Remove the Terraform distribution archive. Default: true



Example Playbook
----------------

```yaml
---
- hosts: localhost
  become: true
  connection: local

  roles:
    - mauromedda.ansible_role_packer
```


License
-------

BSD

Author Information
------------------

Author: Mauro Medda 
