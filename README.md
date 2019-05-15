<BS># Ansible role `squid`

[![N|Solid](http://basilicata.ninux.org/images/Logo_Ninux_Basilicata_600-192.png)](http://basilicata.ninux.org)

E' un ruolo per installare e configurare un Server Proxy con SQUID, testato su una Rasbperry e su una macchina virtuale con Debian 9.

## Installazione di Ansible su Debian
Add the following line to /etc/apt/sources.list
~~~
deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main

$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
$ sudo apt-get update
$ sudo apt-get install ansible


file hosts
```
[proxy]
proxy.domain.local ansible_user=root ansible_port=22 ansible_host=10.27.22.6
```

#Playbook
```Yaml
- hosts: raspy
  become: "{{ sudo | default('yes') }}"
  roles:
    - squid
```

