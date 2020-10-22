# ansible-skeleton

Ansible role skeleton for Ansible Galaxy init function

![ansible-version](https://img.shields.io/badge/ansible-v2.9+-green.svg)
![last-commit](https://img.shields.io/github/last-commit/eagleusb/ansible-skeleton)
![license](https://img.shields.io/github/license/eagleusb/ansible-skeleton)

## Requirements

None

## Quickstart

```sh
ansible-galaxy install eagleusb.skeleton
ansible-galaxy init --role-skeleton ~/.ansible/roles/eagleusb.skeleton ansible-therole
...
- Role ansible-therole was created successfully
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

[GNU GENERAL PUBLIC LICENSE Version 3](./LICENSE)
