Plik Ansible Role
=================
[![CI](https://github.com/abarrak/plik-ansible-role/actions/workflows/ci.yml/badge.svg)](https://github.com/abarrak/plik-ansible-role/actions/workflows/ci.yml)
[![Release](https://github.com/abarrak/plik-ansible-role/actions/workflows/release.yml/badge.svg)](https://github.com/abarrak/plik-ansible-role/actions/workflows/release.yml)

This is an ansible role to install and configure Plik.

[Plik](https://github.com/root-gg/plik) is a scalable & friendly temporary file upload system (Wetransfer like) in golang.

Requirements
------------

Linux machine.

Role Variables
--------------

The role contains default varibles in `defaults/main.yml`, and should be overriden as convenient.

    
Dependencies
------------

None.

Example Playbook
----------------

Install the role:

    ansible-galaxy install abarrak.plik_ansible_role

Include it to run the setup tasks:

    - hosts: plik-server
      import_role:
        name: abarrak.plik_ansible_role
      vars:
        release_version: "1.3.6"

For plik configuration, the common parameters are available [in vars as well](https://github.com/abarrak/plik-ansible-role/blob/main/defaults/main.yml). 

For further customization _(e.g. add different backends)_, `plikd.cfg` can be pass as varible block:

    toml_config: |
      GoogleApiClientID   = ""
      GoogleApiSecret     = ""
      GoogleValidDomains  = []

      DataBackend = "gcs"
        [DataBackendConfig]
        Bucket = "MyAwesomeBucket"
        Folder = "plik"

License
-------

MIT.

Author Information
------------------

Abdullah Barrak [(@abarrak).](https://github.com/abarrak)
