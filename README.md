Wireguard
=========

Install and configure wireguard

Requirements
------------

None.

Role Variables
--------------

### wireguard_conf_dir

The directory where wireguard stores the configurations


### wireguard_interface

Wireguard interface name.

### wireguard_template

Template to use when applying the interface config.

### wireguard_port

The wireguard listening port

### wireguard_enabled

If wireguard should be enabled by systemd (wg-quick)

### wireguard_state

What state the service should have. (wg-quick)

Dependencies
------------

None.

Example Playbook
----------------

    - name: Setup tunnel between multiple host groups
      hosts:
        - group-one
        - group-two
      roles:
        - tuggan.wireguard
      tags:
        - wireguard
      become: true
      vars:
        wireguard_endpoints: "{{ groups['group-one'] + groups['group-two'] }}"

License
-------

BSD
