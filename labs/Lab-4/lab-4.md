# Lab 4 : Install Nginx using Ansible Role

* Search for ansible role on ansible galaxy

* Install/Import ansible role on Local 

```
ansible-galaxy install nginxinc.nginx
```

* Create ansible project directory 

```
mkdir lab-4
cd lab-4
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

* Create ansible playbook

```
vi playbook.yml
# Add below contents
===
---
- name: Install WebServer 
  hosts: Redhat
  remote_user: root

  roles:
    - nginxinc.nginx

===
```

* Run playbook 

```
ansible-playbook -i inventory playbook.yml
```