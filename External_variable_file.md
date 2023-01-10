Filename - `vars/variables.yml`
```yml
---
docker_version: 20.10.12
http_port: 80
app_version: 2.9
```
Filename - `main.yml`
```yml
---
- name: Example External Variables file
  hosts: all
  vars_files:
    - ./vars/variables.yml
  tasks:
    - name: Print the value of variable docker_version
      debug:
        msg: "{{ docker_version }}"

    - name: Print thevalue of variable http_port
      debug:
        msg: "{{ http_port }}"

    - name: Print the value of variable app_version
      debug:
        msg: "{{ app_version }}"

```

**Output**
![image](https://user-images.githubusercontent.com/91359308/211616615-e77ea9e6-387a-4eac-8e3d-1fda4cab0557.png)
