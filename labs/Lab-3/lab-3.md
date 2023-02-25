# Lab 3 : Update Ansible Playbook to Support Debian Nodes

* Update `playbook.yml` to support debian nodes.

```
vi playbook.yml
# Add below contents in playbook.yml
===     
- name: Install WebServer on Debian Distro
  hosts: Debian
  remote_user: root

  tasks:
    - name: Ensure Apache is at the latest version
      apt:
        name: apache2
        state: latest
    - name: Ensure Apache is enable & running 
      service:
        name: apache2
        state: started
        enabled: yes 

===
```

* Run playbook 

```
ansible-playbook -i inventory playbook.yml
```

