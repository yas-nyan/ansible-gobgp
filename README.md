# Ansible GoBGP

This is an ansible role for install and bootstrap GoBGP.

GoBGP Pojects: [GitHub](https://github.com/osrg/gobgp)

## Requirements
- Ansible: `2.7` or newer
- Host OS: 
  - `Ubuntu 16.04 amd64` or newer
  - `Debian 8 ` or newer


## Role Variables
```yml
GOBGP_VERSION: 2.11.0
AS_NUMBER: 65000
ROUTER_ID: "192.0.2.1"

PEERS:
  - ADDRESS: "192.0.2.2"
    AS_NUMBER: 65001
  - ADDRESS: "192.0.2.3"
    AS_NUMBER: 65002
  - ADDRESS: "192.0.2.4"
    AS_NUMBER: 65003

```

`GOBGP_VERSIONS`: see also https://github.com/osrg/gobgp/releases/


## Exaple Playbook
```yml
---
- hosts: routers
  become: true
  roles:
    - gobgp

```


## LINCENSE
MIT

## Au