```yml
- hosts: localhost
  tasks:
  - name: update the localhost
    shell: sudo apt update

  - name: upgrade the localhost
    shell: sudo apt upgrade -y
```
