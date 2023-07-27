![Ansible Lint](https://github.com/johanneskastl/ansible-role-obs_server/workflows/Ansible%20Lint/badge.svg)

obs_server
=========

Install and configure a OpenBuildService server

Requirements
------------

The OpenBuildService repository only supports a limited number of OS versions.
Currently the 2.10 versions supports 15.3 (both openSUSE Leap and SLES). Support
for 15.4 is in preparation, currently there are still lots of issues aka it is
broken...

TL;DR: Only use this role on SLES15SP3 or openSUSE Leap 15.3.

Role Variables
--------------

None.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: 'johanneskastl.obs_server'

License
-------

BSD-3-Clause

Author Information
------------------

I am Johannes Kastl, reachable via kastl@b1-systems.de.
