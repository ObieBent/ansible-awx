Ansible AWX
=========

This role install AWX

Requirements
------------

* **postgresql**

Role Variables
--------------

Variable | Default value |Description
---------|---------------|--------------
`awx_version` | 17.0.0 | Version to install
`awx_data_dir` | /var/lib/awx | Data dir of awx
`awx_port` | 3000 | awx http port
`awx_admin_pass` | changeme | User admin password
`awx_vhost_name` | awx | awx vhost

Dependencies
------------

* **apache-proxy**
* **docker**
* **ssl-certs**

Example Playbook
----------------

```yml
- hosts: all
  vars:
    awx_data_dir: /srv/awx
    awx_admin_pass: changeme
  roles:
    - role: postgresql
      postgresql_version: 13
      postgresql_data_dir: "{{ awx_data_dir | dirname }}/postgresql"
    - role: ansible-awx
```

You can acces with AWX with this http://host

License
-------

BSD

Author Information
------------------

* ASSOGBA Boris <borisassogba@live.fr>
