# ansible-vault

Ansible role to deploy and initialize Hashicorp Vault machine or cluster.
It's a fork of [ansible-vault](https://github.com/ansible-community/ansible-vault) in order to refactor it, use Raft integrated storage as default
and support initialization with SNI.

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

Only most common ones are listed here, to see all variables go to [defaults/main.yml](./defaults/main.yml)

| Name                     | Required | Default Value       | Description                                                      |
|--------------------------|----------|---------------------|------------------------------------------------------------------|
| vault_version            | no       | *1.5.5*             | Binary version                                                   |
| vault_install_remotely   | no       | *false*             | Install process only on remote target(s)                         |
| vault_upgrade_inplace    | no       | *false*             | Update binary when version do not match                          |
| vault_group_name         | no       | *vault_instances*   | Inventory group name containing vault instances                  |
| vault_api_addr           | no       | *IP:8200*           | Announced listening address for Vault API                        |
| vault_cluster_disable    | no       | *false*             | Disable Vault clustering                                         |
| vault_tls_enable         | no       | *true*              | Enable or disable TLS transport for API and supported backends   |
| vault_backend            | no       | *raft*              | Selected Vault backend                                           |

## Playbook Example

```yml
- hosts: all
  roles:
    - role: ansible-vault
      vars:
        vault_group_name: "vault_server"
        vault_init: true
        vault_init_key_shares: 5
        vault_init_key_threshold: 2
        vault_log_level: "debug"
        vault_tls_enable: true
        vault_tls_files:
          ca_file: "ca.crt"
          cert_file: "vault.crt"
          key_file: "vault.key"
          copy: true
```

## License

[BSD](./LICENSE.txt)
