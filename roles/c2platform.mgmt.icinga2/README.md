# Ansible Role Icinga2

This role installs and configures Icinga2 on the BKWI bastion hosts.

<!-- MarkdownTOC levels="2,3" autolink="true" -->

- [Requirements](#requirements)
- [Dependencies](#dependencies)
- [Example Playbook](#example-playbook)

<!-- /MarkdownTOC -->

## Requirements

Port 5665/TCP must be opened in both directions between the BKWI bastions and the Icinga2 master 145.21.178.14


## Example Playbook

The playbook is part of the Suwinet playbook.
```yaml
    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
```
