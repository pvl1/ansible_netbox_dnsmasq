Ansible DNSmasq
===============
adapted from https://gitlab.com/fwalk/ansible-dnsmasq

Requirements
------------

Tested with:

- Ansible 2.14

Role Variables
--------------

See example.

Dependencies
------------

netbox.netbox.nb_inventory

Example Playbook
----------------

*Inventory:*

```plain
[nameserver]
ns1 ansible_host=192.168.1.2 ansible_user=pi

[nameserver:vars]
domain=example.com
```

*Playbook:*

```plain
---
- hosts:
    - nameserver

  roles:
    - role: ansible-dnsmasq

Example Inventory
___
plugin: netbox.netbox.nb_inventory
api_endpoint: use_ssl_where_possible
token: blah
validate_certs: False
config_context: False
dns_names: true
interfaces: true
fetch_all: False
group_by:
  - tags
query_filters:
  - tag: no-dhcp
#https://github.com/p-rintz/netbox-dnsmasq
compose:
  ansible_host: display_name

License
-------

BSD

Author Information
------------------

fwalk___gitlab
