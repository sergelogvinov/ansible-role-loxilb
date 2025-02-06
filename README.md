# Ansible role Loxilb

LoxiLB is an open source hyper-scale software load-balancer for cloud-native workloads. It uses eBPF as its core-engine and is based on Golang.

## Install

```shell
ansible-galaxy role install git+https://github.com/sergelogvinov/ansible-role-loxilb.git,main
```

Or galaxy storage

```shell
ansible-galaxy role install sergelogvinov.loxilb
```

## Options

Useful variables:

* `loxilb_version` - version of distributive (default: `latest`)
* `loxilb_args` - arguments for loxilb

## Install Loxilb

```yaml
# debian.yml

- hosts: all
  vars:
    loxilb_args: "--host=127.0.0.1"

  roles:
    - ansible-role-loxilb
```

```yaml
# debian.ini

[all]
debian   ansible_host=1.2.3.4 ansible_ssh_user=debian # ansible_port=112233
```

Deploy Loxilb to the server

```shell
ansible-playbook -Dv -i debian.ini debian.yml
```

## References

* https://www.loxilb.io
