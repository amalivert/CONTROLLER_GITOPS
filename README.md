Controller Git Ops playbook
============================

Role to install and do basic configuration of Red Hat Satellite 6.X.

INFORMATION
-----------

This playbook will take a while to run depending the number of repositories to
sync.

Requirements
------------
Collections:
 - ansible.controller
 - redhat_cop.controller_configuration

 Python module:
 - awxkit


How to run the playbook
------------------------

* Install awxkit 
```
pip<pythonversion> install awxkit:
```

* Install needed collections:
```
ansible-galaxy collection install redhat_cop.controller_configuration
```

The ansible-playbook controller_set_assets_vars.yml and controller_set_assets_vars.yml are used to extract assets from one Tower/Controller and use that asset to create the variable files that are needed to import to another tower/controller.

* Run the playbooks to generate var files for sepecific assets that exists on Tower/Controller:
```
ansible-playbook controller_set_assets_vars.yml 
```

* Check the var files to ensure that they got populated with the correct data and format:
i.e
```
cat vars/controller_projects.json
```
* Run playbook to create Controller assets
```
 ansible-playbook add_controller_projects
```

License
-------

MIT

Author Information
------------------

Abnerson Malivert

