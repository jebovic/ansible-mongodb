MongoDB
=========

[![Build Status](https://travis-ci.org/jebovic/ansible-mongodb.svg?branch=master)](https://travis-ci.org/jebovic/ansible-mongodb) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.mongodb-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/mongodb)

Install and configure MongoDB

Role Variables
--------------

```
# MongoDB basic ocnfiguration
mongodb_dbpath: /var/lib/mongodb
mongodb_log_file: /var/log/mongodb/mongodb.log
mongodb_bind_ip: 127.0.0.1
mongodb_port: 27017
mongodb_journal: "true"
mongodb_verbose: "false"
```

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: mongodb }
```

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
