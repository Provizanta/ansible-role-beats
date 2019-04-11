Ansible role: beats
=========

Install and configure Elastic (ELK) Stack beats.

Requirements
------------

None

Role Variables
--------------

These defaults are set in defaults/main.yml:

    version: 6

Non defaulted variables that can be set:

    beats:
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
           version: 6
           beats:
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
