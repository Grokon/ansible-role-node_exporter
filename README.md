# ansible-role-node_exporter

[![Mocelule Test Status](https://github.com/Grokon/ansible-role-node_exporter/actions/workflows/molecule.yaml/badge.svg?branch=master)](https://github.com/Grokon/ansible-role-node_exporter/actions/workflows/molecule.yaml)
[![GitHub release](https://img.shields.io/github/release/Grokon/ansible-role-node_exporter.svg)](https://github.com/Grokon/ansible-role-node_exporter/release)
[![GitHub license](https://img.shields.io/github/license/Grokon/ansible-role-node_exporter.svg)](https://github.com/Grokon/ansible-role-node_exporter/blob/master/LICENSE)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-grokon.node_exporter-blue.svg)](https://galaxy.ansible.com/grokon/node_exporter/)

## Example Playbook

```yaml
- hosts: all
  roles:
    - grokon.node_exporter
```

An Ansible Role that installs node_exporter on Debian

## Table of content

- [Default Variables](#default-variables)
  - [node_exporter__basic_auth_users](#node_exporter__basic_auth_users)
  - [node_exporter__config_dir](#node_exporter__config_dir)
  - [node_exporter__disabled_collectors](#node_exporter__disabled_collectors)
  - [node_exporter__enabled_collectors](#node_exporter__enabled_collectors)
  - [node_exporter__http_server_config](#node_exporter__http_server_config)
  - [node_exporter__install](#node_exporter__install)
  - [node_exporter__log_level](#node_exporter__log_level)
  - [node_exporter__path](#node_exporter__path)
  - [node_exporter__system_group](#node_exporter__system_group)
  - [node_exporter__system_user](#node_exporter__system_user)
  - [node_exporter__textfile_dir](#node_exporter__textfile_dir)
  - [node_exporter__tls_server_config](#node_exporter__tls_server_config)
  - [node_exporter__tmp_dir](#node_exporter__tmp_dir)
  - [node_exporter__version](#node_exporter__version)
  - [node_exporter__web_listen_address](#node_exporter__web_listen_address)
- [Discovered Tags](#discovered-tags)
- [Open Tasks](#open-tasks)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### node_exporter__basic_auth_users

Basic auth configuration for node_exporter

#### Default value

```YAML
node_exporter__basic_auth_users: {}
```

### node_exporter__config_dir

node_exporter configuration directory

#### Default value

```YAML
node_exporter__config_dir: /etc/node_exporter
```

### node_exporter__disabled_collectors

List of disabled collectors for node_exporter

#### Default value

```YAML
node_exporter__disabled_collectors: []
```

### node_exporter__enabled_collectors

List of enabled collectors for node_exporter

#### Default value

```YAML
node_exporter__enabled_collectors:
  - systemd
  - textfile:
      directory: '{{ node_exporter__textfile_dir }}'
  - filesystem:
      ignored-mount-points: ^/(sys|proc|dev)($|/)
      ignored-fs-types: ^(sys|proc|auto|tmp)fs$
```

### node_exporter__http_server_config

HTTP configuration for node_exporter

#### Default value

```YAML
node_exporter__http_server_config: {}
```

### node_exporter__install

Weather of not to install node_exporter Set to false if it's already installed and wanted to remove it

#### Default value

```YAML
node_exporter__install: true
```

### node_exporter__log_level

node_exporter log level, One of: debug, info, warn, error

#### Default value

```YAML
node_exporter__log_level: info
```

### node_exporter__path

Default path for node_exporter

#### Default value

```YAML
node_exporter__path: /usr/local/bin/node_exporter
```

### node_exporter__system_group

Group for node_exporter

#### Default value

```YAML
node_exporter__system_group: '{{ node_exporter__system_user }}'
```

### node_exporter__system_user

User for node_exporter

#### Default value

```YAML
node_exporter__system_user: node-exporter
```

### node_exporter__textfile_dir

Directory for node_exporter textfile collectors

#### Default value

```YAML
node_exporter__textfile_dir: /var/lib/node_exporter
```

### node_exporter__tls_server_config

TLS configuration for node_exporter

#### Default value

```YAML
node_exporter__tls_server_config: {}
```

### node_exporter__tmp_dir

Default tmp directory for node_exporter

#### Default value

```YAML
node_exporter__tmp_dir: /tmp
```

### node_exporter__version

Default to latest version, pin version example: 'v1.1.0'

#### Default value

```YAML
node_exporter__version: latest
```

### node_exporter__web_listen_address

Address on which to expose metrics and web interface.

#### Default value

```YAML
node_exporter__web_listen_address: 0.0.0.0:9100
```

## Discovered Tags

**_node_exporter_configure_**

**_node_exporter_install_**

**_node_exporter_run_**

## Open Tasks


## Dependencies

None.

## License

MIT

## Author

grokon
