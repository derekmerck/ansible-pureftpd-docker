Ansible Role for PureFTPd in Docker
===================================

[![Build Status](https://travis-ci.org/derekmerck/ansible-pureftpd-docker.svg?branch=master)](https://travis-ci.org/derekmerck/ansible-pureftpd-docker)

Derek Merck  
<derek_merck@brown.edu>  
Rhode Island Hospital and Brown University  
Providence, RI  

Configure and run a [Pure-FTPd](https://www.pureftpd.org/project/pure-ftpd) server in a Docker container.


Dependencies
------------

### Galaxy Roles

- [geerlingguy.docker](https://github.com/geerlingguy/ansible-role-docker) to setup the docker environment
- [geerlingguy.pip](https://github.com/geerlingguy/ansible-role-pip) to install Python reqs


### Remote Node

- [Docker][]
- [docker-py][]
- [pexpect][]

[Docker]: https://www.docker.com
[docker-py]: https://docker-py.readthedocs.io
[pexpect]: https://pexpect.readthedocs.io


Role Variables
--------------

### Docker Image and Tag

Always uses the hardened [stilliard/docker-pure-ftpd][] image.

[stilliard/docker-pure-ftpd]: https://github.com/stilliard/docker-pure-ftpd

### Docker Container Configuration

```yaml
pftp_container_name:   "pftp"
pftp_use_data_container: True
pftp_data_dir:         "/data/pftp"
pftp_port:             21
pftp_hostname:         localhost
```

### Service Configuration

```yaml
pftp_service_user:     "pftp"
pftp_service_password: "passw0rd!"
```


Example Playbook
----------------

```yaml
- hosts: ftp_server
  roles:
     - derekmerck.pureftpd_docker
```


License
-------

MIT

