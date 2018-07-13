ara
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-ara.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-ara)

Provides ara (Ansible Runtime Analysis) for your system.

Context
-------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/ara.png "Dependency")

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

To tell Ansible to use ara, these variables can be modified:
- ara_configuration_file can be set and defaults to /etc/ansible/ansible.cfg.
- ara_callback_plugins should point to where ara is installed.

All other (ara) options can be defined by overwriting ara_configuration:
- ara_configuration:
  - option: port
    value: 9191

You can configure ara using this structure:
```
ara_configuration:
  - option: port
    value: 9191
```

These are the settings you can use.

- dir
- database
- host
- port
- logconfig
- logfile
- loglevel
- logformat
- sqldebug
- ignore_parameters
- ignore_empty_generation
- ignore_mimetype_warnings
- playbook_override
- playbook_per_page
- result_per_page

Dependencies
------------

This role can be used to prepare your system:

- [robertdebock.bootstrap](https://travis-ci.org/robertdebock/ansible-role-bootstrap)
- [robertdebock.buildtools](https://travis-ci.org/robertdebock/ansible-role-buildtools)
- [robertdebock.epel](https://travis-ci.org/robertdebock/ansible-role-epel)
- [robertdebock.scl](https://travis-ci.org/robertdebock/ansible-role-scl)
- [robertdebock.python_pip](https://travis-ci.org/robertdebock/ansible-role-python_pip)

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|
|------------|-----------|-----------|-----------|
|alpine-edge|yes|yes|yes|
|alpine-latest|yes|yes|yes|
|archlinux|yes|yes|yes|
|centos-6|no|no|no|
|centos-latest|yes|yes|yes|
|debian-latest|yes|yes|yes|
|debian-stable|yes|yes|yes|
|fedora-latest|yes|yes|yes|
|fedora-rawhide|yes|yes|yes|
|opensuse-leap|yes|yes|yes|
|opensuse-tumbleweed|yes|yes|yes|
|ubuntu-artful|yes|yes|yes|
|ubuntu-latest|yes|yes|yes|

Example Playbook
----------------

The simplest way possible:
```
- hosts: servers
  become: true

  roles:
    - robertdebock.bootstrap
    - robertdebock.epel
    - robertdebock.buildtools
    - robertdebock.scl
    - robertdebock.python_pip
    - robertdebock.ara
```

You can also call this role without having `become: true`, because the tasks that require elevated privileges have `become: true` added.

Install this role using `galaxy install robertdebock.ara`.

License
-------

Apache License, Version 2.0

Author Information
------------------

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
