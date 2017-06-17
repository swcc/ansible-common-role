Common
=========

[![Build Status](https://travis-ci.org/swcc/ansible-common-role.svg?branch=master)](https://travis-ci.org/swcc/ansible-common-role)

Common configurations and initial setups useful for a Debian server


Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

| Variable name | type | default | description |
|---------------|------|---------|-------------|
| common_generate_dh_params | boolean | Whether to generate DH parameters or not. Useful for TLS webservers |
| common_apt_packages | array |   - `htop`<br>  - `vim`<br>  - `less`<br>  - `ntp`<br>  - `ca-certificates`<br>  - `apt-transport-https`<br>  - `sudo`<br>  - `unattended-upgrades`<br>  - `apt-listchanges`<br> | List of apt packages to install |
| common_apt_extra_packages | array | [] | List of extra apt packages to install |


Example Playbook
----------------

    - hosts: servers
      roles:
        - role: swcc.common
          common_generate_dh_params: true
          common_apt_extra_packages: [ iotop, iftop ]

License
-------

GPLv3
