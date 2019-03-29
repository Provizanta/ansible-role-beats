ELK Beat
=========

Install Elastic Stack Beat.

Requirements
------------

None

Role Variables
--------------

version: <string or int of a version>

configuration: <the entire yaml configuration to be stored in the filebeat configuration file>

service:
  enabled: <bool, enable the service on startup> 
  state: <enum, state of the systemd service>

Dependencies
------------

None

Example Playbook
----------------

Information about local filebeat TCP output port, destination logstash host and port are necessary.

    - hosts: clients
      roles:
       - role: elk/beats/filebeat
         vars:
           version: 6
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

Tibor Csoka

