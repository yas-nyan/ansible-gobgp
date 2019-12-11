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
    ROUTE_REFLECTOR_CLIENT: True
    ROUTE_REFLECTOR_CLUSTER_ID: 192.0.2.1
    AFI_SAFIS:
      - NAME: ipv4-unicast
  - ADDRESS: "192.0.2.3"
    AS_NUMBER: 65001
    ROUTE_REFLECTOR_CLIENT: True
    ROUTE_REFLECTOR_CLUSTER_ID: 192.0.2.1
    AFI_SAFIS:
      - NAME: ipv4-unicast
  - ADDRESS: "2001:df8::1"
    AS_NUMBER: 65002
    AFI_SAFIS:
      - NAME: ipv6-unicast

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