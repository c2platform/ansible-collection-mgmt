# Ansible Role server_update

Update servers using [ansible.builtin.apt](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html) and [ansible.builtin.yum](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_module.html). Optionally reboot machine if necessary ( kernel update ) using [ansible.builtin.reboot](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/reboot_module.html)

<!-- MarkdownTOC levels="2,3" autolink="true" -->

- [Requirements](#requirements)
- [Role Variables](#role-variables)
- [Dependencies](#dependencies)
- [Example Playbook](#example-playbook)

<!-- /MarkdownTOC -->

## Requirements

<!-- Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required. -->

## Role Variables

<!--  A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well. -->

|Variable                       |Default|
|-------------------------------|-------|
|server_update_debug            | no    |
|server_update_update_enabled   |TRUE   |
|server_update_reboot_enabled   |TRUE   |
|server_update_reboot_pre_delay |0      |
|server_update_reboot_post_delay|10     |
|server_update_reboot_timeout   |600    |
|server_update_proxy_environment| {}    |
|server_update_reboot_command   |       |

## Dependencies

<!--   A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles. -->

## Example Playbook

<!--   Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too: -->

```yaml
- import_playbook: stop.yml

- name: Update hosts
  hosts: all
  become: yes

  roles:
    - { role: c2platform.mgmt.server_update }

  vars:
    server_update_debug: yes
    server_update_update_enabled: true
    server_update_reboot_enabled: true
    server_update_reboot_pre_delay: 0
    server_update_reboot_post_delay: 10
    server_update_reboot_timeout: 600
```