Wireguard
=========

Install and configure wireguard

Requirements
------------

None.

Role Variables
--------------

There are a lot of configuration variables that can be set to configure a client. This is only a list of the common options. To find all variables see the templates.

| Variable            | Required | Description                                         |
| ------------------- | -------- | --------------------------------------------------- |
| wireguard_conf_dir  | No       | The wireguard config directory                      |
| wireguard_interface | No       | Name of the wireguard interface                     |
| wireguard_template  | No       | Template to use for interface config                |
| wireguard_port      | No       | Wireguard listening port                            |
| wireguand_enabled   | No       | Specifies if wg-quick@interface should be enabled   |
| wireguard_state     | No       | Specifies the state of a wg-quick@interface service |


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
