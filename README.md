# ansible-bault

Ansible role to deploy and initialize Hashicorp Vault machine or cluster.
It's a fork of [ansible-vault](https://github.com/ansible-community/ansible-vault) in order to refactor it, use Raft integrated storage as default
and support initialization.

![ansible-version](https://img.shields.io/badge/ansible-v2.9+-green.svg)
![last-commit](https://img.shields.io/github/last-commit/eagleusb/ansible-vault)
![license](https://img.shields.io/github/license/eagleusb/ansible-vault)

## Requirements

None

## Quickstart

```sh
ansible-galaxy install eagleusb.vault
```

## Variables

| Name         | Required | Default Value | Description                                          |
|--------------|----------|---------------|------------------------------------------------------|
| skeleton_foo | no       | *5.0*         | flush input data to foobar every seconds.nanoseconds |

## Playbook Example

```yml
- hosts: all
  roles:
    - role: ansible-skeleton
      vars:
        skeleton_foo: "1.0"
```

## License

[BSD](./LICENSE.txt)
