Thoth: PostgreSQL
=================

This role will deploy PostgreSQL into an OpenShift namespace.

Role Variables
--------------

This role requires a namespace in which the metrics exporter should be created together with few parameters for PostgreSQL instance. See the ``vars`` configuration section for more info.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters):

    - hosts: localhost
      connection: local
      gather_facts: False

      roles:
        - role: thoth-station.postgresql
          namespace: thoth-test-core

Variables of the playbook
-------------------------

The playbook accepts the following variables:


* `namespace` - OpenShift project where the PostgreSQL application should be deployed to (defaults to `thoth-test-core`)
* `postgresql_memory_limit` - memory limit for the provisioned PostgreSQL instance (defaults to `8Gi`)
* `postgresql_database_service_name` - name of the service (defaults to `postgresql`)
* `postgresql_user` - database user which will be created for accessing database content (defaults to `thoth`)
* `postgresql_password` - password which will be used for the database user - if not explictly provided, its autogenerated during provisioning
* `postgresql_database` - name of the PostgreSQL database (defaults to `postgres`)
* `postgresql_volume_capacity` - the default volume capacity used to persist data (defaults to `1Gi`)
* `postgresql_version` - version of PostgreSQL which should be used (defaults to `9.6`) - this version *has to* be available in OpenShift's service catalogue
* `storage_class_name` - the persistent volume to be claimed for postgresql
* `ceph_pv_secret_name` - ceph based persistent volume's required secret name
* `ceph_pv_secret` - ceph based persistent volume secret (value is present in thoth gopass)

License
-------

GPLv3

Author Information
------------------

The Thoth Station Team.
