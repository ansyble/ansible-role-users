[ ![Image](https://cloud.githubusercontent.com/assets/5514990/21614528/5c56d772-d20c-11e6-8670-577f2dd7ca9b.png "Ansible") ](https://www.ansible.com/ "Ansible")

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

**Config ssh**

```yml
users_ssh_config_hosts:
  - user: me
    hosts:
      - name: github.com
        rsa_private: "{{rsa_github}}"
```
