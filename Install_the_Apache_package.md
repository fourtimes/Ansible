## Installing the package using the Ansible template

Filename - `ansible.cfg`
```cfg
[defaults]
inventory = hosts
```
Filename - `hosts`
```
[apache]
192.168.1.9 ansible_ssh_user=dodo ansible_password=.
```
**To Verify the local connection command**
```
ansible all -m ping
```
After the verification, To install apache2 packages we need to do below files.

Filename - `apache.yml`
```yml
---
- hosts: 192.168.1.9
  become: true
  tasks:
    - name: install apache2
      apt: name=apache2 update_cache=yes state=latest

    - name: enabled mod_rewrite
      apache2_module: name=rewrite state=present
      notify:
        - restart apache2

  handlers:
    - name: restart apache2
      service: name=apache2 state=restarted
```
**Run the below command to install the apache2 packages**
```
ansible-playbook apache.yml  -K
```
**Note**
i) -k, --ask-pass: ask for connection password
ii) -K, --ask-become-pass: ask for privilege escalation password