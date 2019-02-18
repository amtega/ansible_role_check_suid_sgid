# role_name

This role search packages/files with suid or guid bit set and allows you to remove them.

## Requirements

[Ansible 2.7+](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

The role setups the following facts:

- check_suid_sgid_packages_found: list of installed packages that have suid/sgid files.
- check_suid_sgid_packages_found: list of suid/sgid files not installed by any know package.

## Dependencies

- [amtega.check_platform](https://galaxy.ansible.com/amtega/check_platform)
- [amtega.packages](https://galaxy.ansible.com/amtega/packages)

## Example Playbook

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.check_suid_sgid
      check_suid_sgid_packages_state: absent
      check_suid_sgid_files_state: absent
```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.check_suid_sgid/test
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Carlos Chedas Fernandez.
- Juan Antonio Valiño García.
