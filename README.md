Ansible role: beats
=========

![Build & Deploy](https://github.com/Provizanta/ansible-role-beats/workflows/molecule/badge.svg?branch=master)

Install and configure Elastic (ELK) Stack beats.

Requirements
------------

None

Role Variables
--------------

These variables are defined in [defaults/main.yml](./defaults/main.yml):

    elk_version: 6

Non defaulted variables that can be set:

    elk_beats:
      filebeat:
        configuration: <yaml dict, YAML configuration for filebeat>
        service:
          enabled: true
          state: started

Dependencies
------------

None

Example Playbook
----------------

Information about local filebeat TCP output port, destination logstash host and port are necessary.

    - hosts: clients
      roles:
       - role: beats
         vars:
           elk_version: 6
           elk_beats:
             filebeat:
               configuration:
                 filebeat:
                   inputs:
                     - host: localhost:11999
                       type: tcp
                   output:
                     logstash:
                       hosts: logstash:5959

License
-------

MIT

Author Information
------------------

Tibor Csóka
