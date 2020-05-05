[![Build Status](https://travis-ci.org/open-io/ansible-role-openio-loki.svg?branch=master)](https://travis-ci.org/open-io/ansible-role-openio-loki)
# Ansible role `loki`

An Ansible role for install loki. Specifically, the responsibilities of this role are to:

- install and configure loki

## Requirements

- Ansible 2.9+

## Role Variables

| Variable   | Default | Comments (type)  |
| :---       | :---    | :---             |
| `openio_loki_namespace` | `"{{ namespace \| d('OPENIO') }}"` | OpenIO Namespace |
| `openio_loki_maintenance_mode` | `"{{ openio_maintenance_mode \| d(false) }}"` | Maintenance mode |
| `openio_loki_bind_address` | `"{{ openio_mgmt_bind_address \| d(ansible_default_ipv4.address) }}"` | Binding IP address |
| `openio_loki_bind_port` | `6900` | Binding port |
| `openio_loki_grpc_bind_address` | `"{{ openio_loki_bind_address) }}"` | GRPC binding IP address |
| `openio_loki_grpc_bind_port` | `0` | GRPC binding port |

## Dependencies
- https://github.com/open-io/ansible-role-openio-service

## Example Playbook

```yaml
- hosts: all
  gather_facts: true
  become: true

  tasks:
    - include_role:
        name: loki
```

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.

Pull requests are also very welcome.
The best way to submit a PR is by first creating a fork of this Github project, then creating a topic branch for the suggested change and pushing that branch to your own fork.
Github can then easily create a PR based on that branch.

## License
Copyright (C) 2015-2020 OpenIO SAS
