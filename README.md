# InfluxDB

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/ansiblebit/influxdb/master/LICENSE)
[![Build Status](https://travis-ci.org/ansiblebit/influxdb.svg?branch=master)](https://travis-ci.org/ansiblebit/influxdb)

[![Platform](http://img.shields.io/badge/platform-debian-a80030.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/ansiblebit-influxdb/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansiblebit-influxdb/)

[Ansible][ansible] role to setup [InfluxDB][influxdb].

## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian  | Jessie  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Debian  | Wheezy  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Xenial  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Trusty  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Precise | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Vivid   | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |

## Requirements

- ansible >= 1.9.6

## Role Variables

- **influxdb_apt_dependencies**: packages needed to be able to run this playbook or install [InfluxDB][influxdb].
- **influxdb_configuration**: the contents of the [InfluxDB][influxdb] configuration file.
- **influxdb_conf_file**: the location where the [InfluxDB][influxdb] is located.
- **influxdb_group**: the [InfluxDB][influxdb] group.
- **influxdb_http_port**: the port where the [InfluxDB][influxdb] HTTP API will be running.
- **influxdb_ifql_port**: the port where the [InfluxDB][influxdb] ifql RPC service will be running.
- **influxdb_rpc_port**: the port where the [InfluxDB][influxdb] RPC service will be running.
- **influxdb_udp_port**: the port where the [InfluxDB][influxdb] UDP listener will be running.
- **influxdb_user**: the [InfluxDB][influxdb] user.
- **influxdb_version**: the [InfluxDB][influxdb] version to be installed.

Unless stated otherwise a default value is provided for each of the variables mentioned above in the `defaults` directory.

## Dependencies

None.

## Playbooks

    - hosts: servers
      roles:
         - role: ansiblebit.influxdb

## Tags

- **configuration**: configuration tasks.
- **debug**: task to debug role variables.
- **installation**: installation tasks.
- **validation**: task to validate role variables.

## Test

To run the tests you will need to install:

- [tox](https://tox.readthedocs.org/)
- [vagrant](https://www.vagrantup.com/)

To run all tests against all pre-defined OS/distributions * ansible versions:

```bash
tox
```

To run tests for `trusty64`:

```bash
$ cd tests
$ bash test_idempotence.sh --box trusty64.vagrant.dev
# log file will be stores under tests/log
```

To perform debugging on a specific environment:

```bash
$ cd tests
$ vagrant up trusty64.vagrant.dev

# to provision using the test.yml playbook (as many time as you need)
$ vagrant provision trusty64.vagrant.dev

# to access the Vagrant box
$ vagrant ssh trusty64.vagrant.dev
```

## Links

- [[InfluxDB][influxdb] : Introduction > Installation](https://docs.influxdata.com/influxdb/v0.13/introduction/installation/)

[ansible]:      https://www.ansible.com         "Ansible"
[license]:      https://github.com/ansiblebit/influxdb/blob/master/LICENSE  "BSD license"
[influxdb]:     https://influxdata.com          "InfluxDB"
[steenzout]:    https://github.com/steenzout/   "Pedro Salgado"
