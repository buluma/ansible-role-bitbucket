# [Ansible role bitbucket](#ansible-role-bitbucket)

Ansible Role for Atlassian Bitbucket Installation

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-bitbucket/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bitbucket/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-bitbucket/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bitbucket)|[![downloads](https://img.shields.io/ansible/role/d/buluma/bitbucket)](https://galaxy.ansible.com/buluma/bitbucket)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bitbucket.svg)](https://github.com/buluma/ansible-role-bitbucket/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-bitbucket/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- become: true
  gather_facts: true
  hosts: all
  name: Converge
  roles:
  - role: buluma.bitbucket
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-bitbucket/blob/master/molecule/default/prepare.yml):

```yaml
---
- become: true
  gather_facts: false
  hosts: all
  name: Prepare
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
bitbucket_autologin_cookie_age: "10080"
bitbucket_catalina: /opt/atlassian/bitbucket
bitbucket_catalina_connector_port: "7990"
bitbucket_catalina_connector_proxyname:
bitbucket_catalina_connector_proxyport:
bitbucket_catalina_connector_scheme:
bitbucket_catalina_connector_secure:
bitbucket_catalina_context_path:
bitbucket_group: bitbucket
bitbucket_home: /var/atlassian/application-data/bitbucket
bitbucket_jvm_maximum_memory: 2048m
bitbucket_jvm_minimum_memory: 2048m
bitbucket_jvm_reserved_code_cache_size: 512m
bitbucket_jvm_support_recommended_args: -Datlassian.plugins.enable.wait=300
  -XX:+IgnoreUnrecognizedVMOptions -XX:+UnlockExperimentalVMOptions
bitbucket_owner: bitbucket
bitbucket_release: "8.19"
bitbucket_session_timeout: "120"
bitbucket_version: "{{ _bitbucket_version[bitbucket_release] }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-bitbucket/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.git](https://galaxy.ansible.com/buluma/git)|[![Build Status GitHub](https://github.com/buluma/ansible-role-git/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-git/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-git/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-git)|
|[buluma.openjdk](https://galaxy.ansible.com/buluma/openjdk)|[![Build Status GitHub](https://github.com/buluma/ansible-role-openjdk/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-openjdk/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-openjdk/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-openjdk)|
|[buluma.java](https://galaxy.ansible.com/buluma/java)|[![Build Status GitHub](https://github.com/buluma/ansible-role-java/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-java/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-java/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-java)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

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

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-bitbucket/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-bitbucket/blob/master/LICENSE).

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)
