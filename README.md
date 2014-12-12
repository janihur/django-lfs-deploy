django-lfs-deploy
=================

DRAFT

How to deploy [Lighting Fast Shop](http://www.getlfs.com) (LFS) online shop to a single Linux (Ubuntu) node with [Ansible](http://www.ansible.com/home).

* Backend database: [PostgreSQL](http://www.postgresql.org)
* Image support: JPG and PNG
* Configurable locale
* Served with [nginx](http://nginx.org) and [uWSGI](http://uwsgi-docs.readthedocs.org/en/latest/)

Ansible
-------

```Shell
$ ansible-playbook -i inventory lfsserver.yml
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
