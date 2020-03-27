install-ros2-ubuntu
===================

[![Build Status](https://travis-ci.org/itnok/ansible-role-install-ros2-ubuntu.svg?branch=master)](https://travis-ci.org/itnok/ansible-role-install-ros2-ubuntu) [![GitHub tag](https://img.shields.io/github/v/tag/itnok/ansible-role-install-ros2-ubuntu?sort=semver)](https://github.com/itnok/ansible-role-install-ros2-ubuntu/tags/) [![Ansible Role](https://img.shields.io/ansible/role/47440)](https://galaxy.ansible.com/itnok/install_ros2_ubuntu)

Install ROS2 on an Ubuntu host.

Steps performed are:

  - Using role [itnok.manage_pkg_ubuntu](https://galaxy.ansible.com/itnok/manage_pkg_ubuntu):
    * Make sure build_essentials package is installed
    * Add ROS2 repository key
    * Install choosen ROS2 metapackage & basic tools
  - Check installed packages
  - Install RTI Connext DDS & middleware _(*Programmatically APPROVES license agreement!*)_


## :exclamation: Requirements
-----------------------------

None.


## :abcd: Role Variables
------------------------

| Variable                | Description                                             | Default Value       |
|-------------------------|---------------------------------------------------------|---------------------|
| `install_ros2_distro`   | Short name of the ROS distribution to install           | `dashing`           |
| `install_ros2`          | Name of the meta to install _(`ros-base`, `desktop`)_   | `ros-base`          |


## :link: Dependencies
----------------------

- [itnok.manage_pkg_ubuntu](https://galaxy.ansible.com/itnok/manage_pkg_ubuntu) _(:octocat: [ansible-role-manage-pkg-ubuntu](https://github.com/itnok/ansible-role-manage-pkg-ubuntu))_

To install dependencies use:
```
    $ ansible-galaxy install <dependecy.name>
```

Installation of the required Ansible Roles can also be simply addressed with:
```
    $ ansible-galaxy install -r requirements.yml
```


## :notebook: Example Playbook
------------------------------

Here an example of how to use this role in your playbooks:

```
---
- hosts: servers
  remote_user: ubuntu   # optional (your remote user)
  gather_facts: yes     # optional
  become: yes

  roles:
    - { role: itnok.install_ros2_ubuntu }

  vars:
    install_ros2_distro: "dashing"
    install_ros2_distro: "desktop"
```

## :guardsman: License
----------------------

MIT _([read more](LICENSE.md))_
