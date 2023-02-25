# Lab 2 : Write First Ansible Playbook

* Create project directory 

```
mkdir lab-2 
cd lab-2
```

* create ansible inventory file

```
vi inventory
# Add below contents
---

[Redhat]
10.10.0.11
10.10.0.12

[Debian]
10.10.0.13
10.10.0.14

---

:wq # To save file
```

* Create first ansible playbook

```
vi playbook.yml
# Add below contents
===
---
- name: Install WebServer 
  hosts: Redhat
  remote_user: root

  tasks:
    - name: Ensure Apache is at the latest version
       yum:
        name: httpd
        state: latest
    - name: Ensure Apache is enable & running 
       service:
        name: httpd
        state: started
        enabled: yes 

===
```

* Run playbook 

```
ansible-playbook -i inventory playbook.yml
```

