# Ansible Role: web100clt

[![Build Status](https://travis-ci.org/mtlynch/ansible-role-web100clt.svg?branch=master)](https://travis-ci.org/mtlynch/ansible-role-web100clt)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-web100clt-blue.svg?style=flat-square)](https://galaxy.ansible.com/mtlynch/web100clt)
[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](LICENSE)

Installs the NDT C client, with support for a variety of Linux servers.

The NDT client is a tool for measuring network bandwidth. To use the client, you
will need to direct it to a compatible NDT server. For publicly available NDT
servers, consult [mlab-ns](https://mlab-ns.appspot.com/ndt).

## Role Variables

Available variables are listed below, along with default values (see [defaults/main.yml](defaults/main.yml)):

```yaml
web100clt_ndt_version: HEAD
```

The git version of NDT to use to build the NDT C client. This can be any commit
ID or tag from the [mainline NDT repo](https://github.com/ndt-project/ndt).


```yaml
web100clt_install_dir: /opt
```

The directory in which to place the built NDT C client binary.


```yaml
web100clt_temp_dir: /tmp
```

The temporary directory to use for building files.


```yaml
web100clt_jansson_version: 2.9
```

The version of the [Jansson JSON library](http://www.digip.org/jansson/) to use.

```yaml
web100clt_jansson_build_dir: "{{ web100clt_temp_dir }}/jansson-{{ web100clt_jansson_version }}"
```

The directory in which to build Jansson from source.

## Dependencies

None

## Example Playbook

### `example.yml`

```yaml
- hosts: all
  roles:
    - { role: mtlynch.web100clt }
```

### Running Example Playbook

To run the example playbook, `example.yml` (above), run the following commands:

```shell
ansible-galaxy install mtlynch.web100clt
ansible-playbook example.yml
```

When the playbook completes, the compiled NDT C client (`web100clt`) will be
available on the node at `/opt/ndt/src/web100clt`.

## License

Apache2

## Author Information

This role was created in 2016 by [Michael Lynch](http://mtlynch.io).
