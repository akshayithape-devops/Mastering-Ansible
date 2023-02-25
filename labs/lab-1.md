# Lab 1 : Run Your First Ansible Command

* Run ad-hoc command with localhost

```
ansible localhost -m ping
```

* Add `Ubuntu Node` IP address to `/etc/ansible/hosts` file.


* Take the SSH access of `Ubuntu Node`, remove `python3` from that server & exit. 

* Run ad-hoc command with `Ubuntu Node`

```
ansible 10.10.0.13 -m ping
```

* Take the SSH access of `Ubuntu Node`, install `python3` from that server & exit. 

```
ansible 10.10.0.13 -m ping
```

* Run ad-hoc command with `command` module

```
ansible 10.10.0.13 -m command  -a 'sleep 1000'
```

* Take the SSH access of `Ubuntu Node`, go to `~/.ansible/tmp` & run `watch ls -la`.

* Exit the SSH