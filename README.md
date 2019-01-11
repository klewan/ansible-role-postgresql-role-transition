Ansible Role: postgresql-role-transition
========================================

This role is used for PostgreSQL Role Transitions (Switchover and Failover) management.

Supported OS:
-------------
* RedHat
* CentOS
* OracleLinux

Requirements
------------

None

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    postgresql_role_transition_switchover_trigger_file: "{{ postgresql_switchover_trigger_file |  default('switchover.trigger.file',true) }}"

    # display debug info
    postgresql_role_transition_debug_info: true


Dependencies
------------

This role uses `postgresql` role.

Example Playbook
----------------

    - name: Perform PostgreSQL server role transition (switchover/failover)
      hosts: pg-servers
      become: true
      become_user: '{{ postgresql_user }}'
      roles:
        - { role: postgresql-role-transition, tags: postgresql-role-transition }

Inside `vars/main.yml` or `group_vars/..` or `host_vars/..`:

    #------------------------------------------------------
    # overrides role 'postgresql-role-transition' variables
    #------------------------------------------------------

    # ... etc ...


License
-------

GPLv3 - GNU General Public License v3.0

Author Information
------------------

This role was created in 2018 by [Krzysztof Lewandowski](mailto:Krzysztof.Lewandowski@fastmail.fm).


