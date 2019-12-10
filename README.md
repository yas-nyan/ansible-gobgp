# Ansible GoBGP

This is an ansible role for install and bootstrap GoBGP.

GoBGP Pojects: [GitHub](https://github.com/osrg/gobgp)

## example
### variable
```yml
GOBGP_VERSION: 2.11.0
AS_NUMBER: 65000
ROUTER_ID: "192.0.0.1"

PEERS:
  - ADDRESS: "192.0.0.2"
    AS_NUMBER: 65001
```


### playbook
```yml
---
- hosts: routers
  become: true
  roles:
    - gobgp

```

## requirements
- Ansible: `2.7` or newer
- OS: `Ubuntu 16.04 amd64` or newer

## LINCENSE
MIT

