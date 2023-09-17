_**Create a multiple files**_
```yml
---
- hosts: localhost
  tasks:
    - name: Create a multitple files
      file:
        path: "{{ item }}"
        state: touch
      with_items:
        - test01.txt
        - test02.txt
```
_**Create a one files with content**_
```yaml
---
- hosts: localhost
  tasks:
    - name: Creating a file with content
      copy:
        dest: "/home/rad7955/Documents/study/ansible/case1/demo.txt"
        content: |
          ashli
          victor
          joe
```
