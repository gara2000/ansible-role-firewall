DNSSERVER
=========

This role configures the firewall on ubuntu server

Requirements
------------

- Should run on Ubuntu distribution

Role Variables
--------------

This role requires 2 variable to be set:
- open_ports: a list of the allowed ports (by default it allows ports: 22, 80, 443)
- policies: specify the incoming and outgoing policies

Dependencies
------------

No dependencies

Example Playbook
----------------
```yaml
- hosts: servers
  become: yes
  vars:
    open_ports: [22, 80]
    policies:
      - { direction: outgoing, policy: allow }
      - { direction: incoming, policy: deny}
  roles:
      - gara2000.firewall
```

License
-------

BSD