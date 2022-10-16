Plik Ansible Role
=================

This is an ansible role to install and configure Plik.

[Plik](https://github.com/root-gg/plik) is a scalable & friendly temporary file upload system (Wetransfer like) in golang.

Requirements
------------

Linux machine.

Role Variables
--------------

The role contains default varibles in `defaults/main.yml`, and should be overriden as convenient.

For plik configuration, the common parameters are available [in vars as well](https://github.com/abarrak/plik-ansible-role/blob/main/defaults/main.yml). 

In case further customization is needed (e.g. add different backends), the config file `plik.toml` can be pass as block to the play:

    toml_config: |
      GoogleApiClientID   = ""
      GoogleApiSecret     = ""
      GoogleValidDomains  = []

      DataBackend = "gcs"
        [DataBackendConfig]
        Bucket = "MyAwesomeBucket"
        Folder = "plik"

    
Dependencies
------------

None.

Example Playbook
----------------

Install the role:

    ansible-galaxy install abarrak.plik_role

Include it to run the setup tasks:

    - hosts: plik-server
      import_role:
        name: abarrak.plik_role
      vars:
        release_version: "1.3.6"

License
-------

MIT.

Author Information
------------------

Abdullah Barrak [(@abarrak).](https://github.com/abarrak)
