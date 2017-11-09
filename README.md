SLES bootstrap LXC
==================

This role is used to initialize a boot environment to start a container. 

Requirements
------------

The hosting node needs to be running SLES. Their zypper repositories are used to instal the base packages.

Role Variables
--------------

Two variables need to be defined:
* container.name
* container.ips.{interface,address,prefix,gateway}

Dependencies
------------

This role does not have any dependencies. By the way, it is part of a set of roles:
* ansible-ha-cluster
* ansible-sles-lxc-boostrap
* ansible-ha-lxc

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: my-host
      roles:
        - role: sles-lxc-bootstrap
      vars:
        container:
          name: my-container # Container's hostname
          ips:
            # Declare as many interfaces as you need
            - interface: public
              address: x.x.x.x
              prefix: xx
            - interface: save
              address: x.x.x.x
              prefix: xx
            - interface: admin
              address: x.x.x.x
              prefix: xx
              gateway: x.x.x.x

License
-------

GPL-3+

Author Information
------------------

Mathieu GRZYBEK

