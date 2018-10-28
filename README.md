ara
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-ara.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-ara)

Installs ara (ARA Reports Ansible) for your system and configures Ansible to use ARA.


Example Playbook
----------------

This example is taken from `molecule/default/playbook.yml`:
```
---
- name: Converge
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.python_pip
    - role: ansible-role-ara

```

Role Variables
--------------

These variables are set in `defaults/main.yml`:
```
---
# defaults file for ara

# If you would like to update the packages that this role installs, set `ara_packages_state` to `latest`, otherwise use `default`.
ara_package_state: present

# The ansible.cfg to modify.
ara_configuration_file: /etc/ansible/ansible.cfg

# Extra options can be set using this structure.
# ara_configuration:
#   - option: port
#     value: 9191
#   - option: host
#     value: 0.0.0.0
#   - option: playbook_per_page
#     value: 10
#   - option: result_per_page
#     value: 25

```

Requirements
------------

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the last 3 release of Ansible.)

These roles can be installed to ensure all requirements are met:

- none

To install all requirements at once: `ansible-galaxy install -r requirements.yml`.

Context
-------

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/ara.png "Dependency")


Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|ansible 2.7|ansible devel|
|------------|-----------|-----------|-----------|-----------|-------------|
|alpine-edge*|yes|yes|yes|yes|yes*|
|alpine-latest|yes|yes|yes|yes|yes*|
|archlinux|yes|yes|yes|yes|yes*|
|centos-6|no|no|no|no|no*|
|centos-latest|yes|yes|yes|yes|yes*|
|debian-latest|yes|yes|yes|yes|yes*|
|debian-stable|yes|yes|yes|yes|yes*|
|debian-unstable*|yes|yes|yes|yes|yes*|
|fedora-latest|yes|yes|yes|yes|yes*|
|fedora-rawhide*|yes|yes|yes|yes|yes*|
|opensuse-leap|yes|yes|yes|yes|yes*|
|opensuse-tumbleweed|yes|yes|yes|yes|yes*|
|ubuntu-artful|yes|yes|yes|yes|yes*|
|ubuntu-devel*|yes|yes|yes|yes|yes*|
|ubuntu-latest|yes|yes|yes|yes|yes*|

A single star means the build may fail, it's marked as an experimental build.

Testing
-------

[Unit tests](https://travis-ci.org/robertdebock/ansible-role-ara) are done on every commit and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-ara/issues)

To test this role locally please use [Molecule](https://github.com/metacloud/molecule):
```
pip install molecule
molecule test
```
There are many specific scenarios available, please have a look in the `molecule/` directory.


License
-------

Apache-2.0


Author Information
------------------

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
