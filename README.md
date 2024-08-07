# Ansible role [bitbucket](https://galaxy.ansible.com/ui/standalone/roles/buluma/bitbucket/documentation)

Ansible Role for Atlassian Bitbucket Installation

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-bitbucket/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bitbucket/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bitbucket.svg)](https://github.com/buluma/ansible-role-bitbucket/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-bitbucket.svg)](https://github.com/buluma/ansible-role-bitbucket/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-bitbucket.svg)](https://github.com/buluma/ansible-role-bitbucket/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/bitbucket)](https://galaxy.ansible.com/ui/standalone/roles/buluma/bitbucket/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-bitbucket/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.bitbucket
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-bitbucket/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: false
  become: true

  roles:
    - name: buluma.bootstrap
    - name: buluma.git
    - name: buluma.java
    - name: buluma.openjdk
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-bitbucket/blob/master/defaults/main.yml):

```yaml
---
# https://github.com/alvistack/ansible-role-bitbucket/tree/master/defaults
# Bitbucket release.
bitbucket_release: "8.19"

# Bitbucket version.
bitbucket_version: "{{ _bitbucket_version[bitbucket_release] }}"

# Owner and group for Bitbucket.
bitbucket_owner: bitbucket
bitbucket_group: bitbucket

# Bitbucket home directory.
bitbucket_home: /var/atlassian/application-data/bitbucket

# Bitbucket installation directory.
bitbucket_catalina: /opt/atlassian/bitbucket

# JVM minimal and maximum memory usage.
bitbucket_jvm_minimum_memory: 2048m
bitbucket_jvm_maximum_memory: 2048m
bitbucket_jvm_reserved_code_cache_size: 512m

# Proxy and context path setup.
bitbucket_catalina_connector_port: "7990"
bitbucket_catalina_connector_scheme:
bitbucket_catalina_connector_secure:
bitbucket_catalina_connector_proxyname:
bitbucket_catalina_connector_proxyport:
bitbucket_catalina_context_path:
# Atlassian Support recommended JVM arguments.
bitbucket_jvm_support_recommended_args: >-
  -Datlassian.plugins.enable.wait=300
  -XX:+IgnoreUnrecognizedVMOptions
  -XX:+UnlockExperimentalVMOptions

# Session timeout (120 minutes = 2 hours).
bitbucket_session_timeout: "120"

# Remember Me timeout (10080 minutes = 168 hours = 7 days).
bitbucket_autologin_cookie_age: "10080"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-bitbucket/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.git](https://galaxy.ansible.com/buluma/git)|[![Ansible Molecule](https://github.com/buluma/ansible-role-git/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-git/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-git.svg)](https://github.com/shadowwalker/ansible-role-git)|
|[buluma.openjdk](https://galaxy.ansible.com/buluma/openjdk)|[![Ansible Molecule](https://github.com/buluma/ansible-role-openjdk/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-openjdk/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-openjdk.svg)](https://github.com/shadowwalker/ansible-role-openjdk)|
|[buluma.java](https://galaxy.ansible.com/buluma/java)|[![Ansible Molecule](https://github.com/buluma/ansible-role-java/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-java/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-java.svg)](https://github.com/shadowwalker/ansible-role-java)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-bitbucket/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-bitbucket/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-bitbucket/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-bitbucket/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
