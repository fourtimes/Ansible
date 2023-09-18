## Variables with ansible

```yml
# pass the variale with array format
---
- hosts: "*"
  vars:
    continents:
      - Africa
      - Asia
      - South America
      - North America
      - Europe
  tasks:
    - name: Ansible List variable Example
      debug:
        msg: "{{ continents[3] }}"

# pass the array variable with key & value pair
---
- hosts: all
  vars:
    greeting: Hello world!

  tasks:
  - name: Ansible Basic Variable Example
    debug:
      msg: "{{ greeting }}"
      
```
