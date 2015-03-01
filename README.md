django-lfs-deploy
=================

Deploys [Lighting Fast Shop](http://www.getlfs.com) (LFS) online shop to a single Linux (Ubuntu) node with [Ansible](http://www.ansible.com/home).

The LFS runs on the following components:

* Served with [nginx](http://nginx.org) and [uWSGI](http://uwsgi-docs.readthedocs.org/en/latest/)
* Backend database: [PostgreSQL](http://www.postgresql.org)
* Image support: JPG and PNG

The LFS version is [0.9.0a1](https://pypi.python.org/pypi/django-lfs/0.9.0a1).

Ansible
-------

Tested with Ansible version 1.8.2.

Create Ansible [inventory file](http://docs.ansible.com/intro_inventory.html) with one group `[lfsserver]`.

LFS is installed into `~/<ANSIBLE_SSH_USER>/lfs-installer/lfs_project`-directory.

LFS superuser initial password is set to a random string that one have to change after installation:

```bash
$ ~/lfs-installer/bin/django changepassword <LFS_SUPERUSER_USERNAME>
```

The following variables can/should be set:

Description | Location | Variable | Default Value
----------- | -------- | -------- | -------------
Server locale | roles/lfs-common/vars/main.yml | locale_lang | en_IE.utf8
Database name | roles/lfs-database/vars/main.yml | db_name | lfsdb
Database user | roles/lfs-database/vars/main.yml | db_username | lfs
Database password | roles/lfs-database/vars/main.yml | db_password | lfs
nginx domain name | roles/lfs/vars/main.yml | lfs_nginx_domain_name | {{ inventory_hostname }}
LFS superuser name | roles/lfs/vars/main.yml | lfs_superuser_username | lfsadmin

Run the `lfsserver.yml` playbook:

```Shell
$ ansible-playbook -i <INVENTORY_FILE> lfsserver.yml
```

License
-------

Copyright (C) 2014 Jani Hur <https://github.com/janihur/>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
