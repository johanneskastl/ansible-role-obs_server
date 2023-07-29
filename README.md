![Ansible Lint](https://github.com/johanneskastl/ansible-role-obs_server/workflows/Ansible%20Lint/badge.svg)

obs_server
=========

Install and configure a OpenBuildService server

**Attention**

This role is very much work in progress, nowhere near to feature-complete. It
only covers the OBS server to the point, where the UI loads successfully. No
workers are configured, no settings tweaked.

Requirements
------------

The OpenBuildService repository only supports a limited number of OS versions.
Currently the 2.10 versions supports 15.3 (both openSUSE Leap and SLES). Support
for 15.4 is in preparation, currently there are still lots of issues aka it is
broken...

TL;DR: Only use this role on SLES15SP3 or openSUSE Leap 15.3.

Role Variables
--------------

Required role variables:

- `mysql_root_password` (String): password for the MySQL/MariaDB root user
- `mysql_obs_username` (String):  name of the database user that OBS uses to
  connect
- `mysql_obs_password` (String): password of the OBS database user

Optional role variables:

- `obs_server_version` (String): OBS version to install, defaults to '2.10'
  currently
- `create_self_signed_tls_certificate` (Boolean): by default, this role creates
  a self-signed TLS certificate for OBS. If you provide the TLS certificate
  yourself, set this variable to `false` and follow the
  [documentation](https://openbuildservice.org/help/manuals/obs-admin-guide/obs.cha.installation_and_configuration.html#_apache_setup).
- `enable_recommended_services` (Boolean): whether recommended OBS services
  should be enabled and started (default: `true`)
- `enable_cloud_services` (Boolean): whether the optional cloud services should
  be started (default: `false`)

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
