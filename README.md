DNSSERVER
=========

This role configures the firewall on ubuntu server

Requirements
------------

- Should run on Ubuntu distribution

Role Variables
--------------

This role requires 1 variable to be set:
- firewall_rules: a list of objects specifying the firewall rules (by default this will allow tcp traffic on ports: 22, 80 and 443)

Dependencies
------------

No dependencies

Example Playbook
----------------
```yaml
- hosts: servers
  become: yes
  vars:
    firewall_rules:
      - rule: 'allow'
        port: 22
        proto: 'tcp'
      - rule: 'allow'
        port: 80
        proto: 'tcp'
  roles:
      - gara2000.firewall
```

License
-------

BSD