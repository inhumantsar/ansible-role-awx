# awx

[![Build Status](https://travis-ci.org/inhumantsar/ansible-role-awx.svg?branch=master)](https://travis-ci.org/inhumantsar/ansible-role-awx)

Launches AWX on Docker Swarm

## Requirements

The target host must have Docker installed with Swarm initialized.

## Supported Platforms

* RHEL / CentOS: 6, 7      
* Fedora: 24-28      
* Debian:
    - jesse
    - sid
    - stretch
    - buster      
* Ubuntu
    - bionic
    - artful
    - zesty
    - yakkety
    - xenial
* Alpine

## Variables & Defaults

The defaults are fine if you're just trying things out. When moving into production though, there are some things you should change:

* `awx_secret_key`
* `awx_postgres_user` & `awx_postgres_pass`
* `awx_rabbitmq_user` & `awx_rabbitmq_pass`

If you're using an automatic proxy like [`jwilder/nginx-proxy`](https://github.com/jwilder/nginx-proxy) then you will also want to change `awx_web_deploy_labels`.

See [`defaults/main.yml`](defaults/main.yml) for more information.

## Usage

```
- hosts: localhost
  connection: local
  roles:
    - inhumantasr/awx
```

### Removing the stack

Set `awx_remove` to true and run the playbook. eg: `ansible-playbook ... -e awx_remove=true myplaybook.yml`

## Dependencies

None

## License
[BSD](LICENSE)

## Authors
[Shaun Martin](https://github.com/inhumantsar)