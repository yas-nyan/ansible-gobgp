# Ansible GoBGP

This is an ansible role for install and bootstrap GoBGP.

GoBGP Pojects: [GitHub](https://github.com/osrg/gobgp)

## Requirements
- Ansible: `2.7` or newer
- Host OS: 
  - `Ubuntu 16.04` or newer
  - `Debian 8 ` or newer
- Architecture(see also [Gobgp Supported list](https://github.com/osrg/gobgp/releases))
  - `amd64`
  - `386`
  - `arm64`
  - `armv6`




## Role Variables
```yml
GOBGP_VERSION: 2.11.0
CPU_ARCH: "amd64"

# Write gobgpd.conf in yaml format
GOBGP_CONF:
  global:
    config:
      as: 65000
      router-id: 192.0.2.1
      port: 179
  neighbors:
    - config:
        neighbor-address: 192.0.2.2
        peer-as: 65001
      transport:
        config:
          remote-port: "179"
      add-paths:
        config:
          send-max: "8"
          receive: false
      afi-safis:
        - config:
            afi-safi-name: ipv4-unicast
      route-reflector:
        config:
          route-reflector-client: true
          route-reflector-cluster-id: 1.1.1.1

```

`GOBGP_VERSIONS`: see also https://github.com/osrg/gobgp/releases/

See below for the format of gobgpd.conf
https://github.com/osrg/gobgp/blob/master/docs/sources/configuration.md

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