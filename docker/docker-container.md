**_List the docker container. start and stop the docker container_**
```yml
- hosts: localhost
  tasks:
    - name: get container status
      command: sudo docker ps -a
      register: command_output
    # - debug:
    #     var: command_output

    - name: Start the container if it is in stoped state.
      shell:
        cmd: sudo docker start demo
      when: command_output.stdout != "true"

    - name: Stop the container if it is in started state.
      shell:
        cmd: sudo docker stop demo
      when: command_output.stdout != "false"

```
