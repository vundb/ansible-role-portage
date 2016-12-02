Ansible Role Portage
======================================

Ansible role handle portage configuration and package installation on gentoo
instances.

Supported Distributions
-----------------------

- Gentoo

Role Variables
--------------

- `portage_configuration`:
Array with gentoo's portage configuration. See
[default vars file](defaults/main.yml)

- `portage_packages`:
Array with packages to be installed. See
[default vars file](defaults/main.yml)

Dependencies
------------

None.

Example Playbook
----------------
```
- hosts: all
  roles:
    - role: vundb-portage
      portage_configuration:
        - section: 'package.use'
          file: 'dev-lang-php'
          entries:
            - 'dev-lang-php gd'
        - section: 'package.accept_keywords'
          file: 'dev-lang-php'
          entries:
            - '>=dev-lang/php-7.0 ~amd64'
      portage_packages:
        - package: "dev-lang/php"
```

License
-------

MIT

Author Information
------------------

- You can find more roles in my GitHub channel [vundb](https://github.com/vundb)
- Follow me on Twitter [@vundb](https://twitter.com/vundb)
