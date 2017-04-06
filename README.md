[ ![Image](https://cloud.githubusercontent.com/assets/5514990/21614528/5c56d772-d20c-11e6-8670-577f2dd7ca9b.png "Ansible") ](https://www.ansible.com/ "Ansible")

[Ansible](http://www.ansible.com) playbooks for deploying users and groups.

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
  - name: mongkok
    sudoer: yes
    uid: 1008
    comment: revolution will not be televised
    groups: ["admin"]
    append: no
    shell: /bin/zsh
    home: /home/mongkok
    system: yes
    ssh_keys:
      - "ssh-rsa ..."
    zshenv: |
      export FOO=bar
```

**Config ssh**

```yml
users_ssh_config_hosts:
  - user: mongkok
    hosts:
      - name: github.com
        rsa_private: "{{github_rsa_private}}"
    hosts:
      - name: me
        host: defocus.io
        rsa_private: "{{defocus_rsa_private}}"
```
