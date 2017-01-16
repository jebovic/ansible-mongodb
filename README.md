MongoDB
=========

[![Build Status](https://travis-ci.org/jebovic/ansible-mongodb.svg?branch=master)](https://travis-ci.org/jebovic/ansible-mongodb) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.mongodb-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/mongodb)

Install and configure MongoDB

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Compatibility
-------------

Tested and approved on :

* Debian jessie (8+)
* Ubuntu Trusty (14.04 LTS)
* Ubuntu Xenial (16.04 LTS)

Role Variables
--------------

```yaml
# MonogoDB install configuration
mongodb_apt_key_url: https://www.mongodb.org/static/pgp/server-3.2.asc
mongodb_apt_repositories:
  - "deb http://repo.mongodb.org/apt/{{ ansible_distribution | lower }} {{ ansible_distribution_release | lower }}/mongodb-org/3.2 {% if ansible_distribution == 'Debian' %}main{% else %}multiverse{% endif %}"
mongodb_packages:
  - mongodb-org
  - python-pymongo
mongodb_daemon: mongod

# MongoDB basic configuration
mongodb_dbpath: /var/lib/mongodb
mongodb_log_file: /var/log/mongodb/mongodb.log
mongodb_bind_ip: 127.0.0.1
mongodb_port: 27017
mongodb_journal: "true"
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.mongodb }
```

Example : config
----------------

```yaml
# MongoDB listen on server ip, not only localhost
mongodb_bind_ip: "{{ ansible_host }}"
```

Tags
----

* mongodb_config : only update config and restart service

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
