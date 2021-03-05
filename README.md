Wildfly / JBoss EAP - Installer
=========
[![Open Source Love png1](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/ellerbrock/open-source-badges/) <img alt="Ansible" src="https://img.shields.io/badge/ansible%20-%231A1918.svg?&style=for-the-badge&logo=ansible&logoColor=white"/>

This role allows you to install either Wildfly or JBoss EAP in domain mode.

Tasks
------------

- Install java OpenJDK
- Install Wildfly/JBoss EAP.
- Configure Master - Slaves connection,  you can add as many slaves as you want.
- Configure firewall ports
- Add Postgres/Microsoft/IBM/Oracle JDBC modules. 

Notice
------

- This role will NOT configure server groups nor JVM for you. once the roll finished, you will have to create them.
- This role does not contemplate the creation of two masters (Active/Passive)

Role Variables
--------------

This role rely on variable heavily so check the following path to assure the proper variable are set, variables are defined in `defaults/main.yml` for global variables and `vars/*.yml` for specific variables, and any variables that can/should be set via parameters to the role.
The most important variable are set in `install.yml`, since is here where you define your hosts.

Example Playbook
----------------

Define your hosts Master/Slaves/Lb as follows:

      - hosts: all
        vars:
           install: jboss
           server_mode: domain
           master_server: master
           slave_server:
           - slave01
           - slave02
           lb_server:
           - lb01
        roles:
          - role: wildfly_jboss

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
