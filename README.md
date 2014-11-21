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
