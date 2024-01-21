# Zabbix on Vagrant with multiple hosts and PSK security, configured with Ansible

This is a demo installation of Zabbix (agent + server + web) and two other Ubuntu virtual machines with zabbix-agent2 installed. One of the agents is configured to use encryption with a pre-shared key.

This is all facilitated by Ansible community collections and roles (see `requirements.yml`) and produced for reference only.

## Requirements

* [Ansible](https://docs.ansible.com)
* [Vagrant](https://www.vagrantup.com)

## Installation

```shell
ansible-galaxy install -r requirements.yml
vagrant up
```

Visit Zabbix at [http://127.0.0.1:8080](http://127.0.0.1:8080) once at least the `server` virtual machine is provisioned. Credentials are the default:

**Username**: Admin
**Password**: zabbix
