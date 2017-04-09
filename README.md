[ ![Image](https://cloud.githubusercontent.com/assets/5514990/24834935/e0d1db04-1d1c-11e7-8ad0-53fd45ff13c3.png "Ansible") ](https://www.ansible.com/ "Ansible")

[![Build Status](https://travis-ci.org/ansyble/role-users.svg?branch=master)](https://travis-ci.org/ansyble/role-users)
[![Ansible Role](https://img.shields.io/ansible/role/16907.svg)](https://galaxy.ansible.com/ansyble/users/)

[Ansible](http://www.ansible.com) role to deploy users and groups.

### Install

```sh
ansible-galaxy install ansyble.users
```

### Usage

**Groups**

```yml
users_groups:
  - name: admin
    gid: 5000
    system: no
```

**Users**

```yml
users:
  - name: me
    sudoer: yes
    uid: 1008
    comment: hello world
    groups: ["admin"]
    append: no
    shell: /bin/zsh
    home: /home/me
    system: yes
    ssh_keys:
      - "ssh-rsa ..."
    zshenv: |
      export FOO=bar
```

**SSH config**

```yml
users_ssh_config_hosts:
  - user: me
    hosts:
      - name: github.com
        rsa_private: "{{rsa_github}}"
```
