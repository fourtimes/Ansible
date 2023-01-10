## Create a multiple repository

Filename - `ansible.cfg`
```cfg
[defaults]
inventory = hosts

[privilege_escalation]
become=True
become_method=sudo
become_user=root
become_ask_pass=False
```
Filename - `hosts`
```
192.168.1.9 ansible_ssh_user=dodo ansible_password=.
```
**To Verify the local connection command**
```
ansible all -m ping
```
After the verification, We need to add the below file
Filename - `main.yml`
```yml
---
- name: Dir
  hosts: 192.168.1.9
  tasks:
  - name : Ansible create multiple directories with_items
    file:
      path: /home/dodo/Desktop/Ashli-Ansible/ansible-basics/{{item}}
      state: directory
    with_items:
      - "mysql"     
      - "repository"     
      - "config"
```
**Run the below command to create a repo**
```
ansible-playbook main.yml
```
