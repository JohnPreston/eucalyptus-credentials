eucalyptus-credentials
======================

Role to download the credentials for a given account

Requirements
------------

This role can only be ran from the CLC host

Role Variables
--------------

| Parameter | Required | Default | Description
|--- |--- |--- |---
| user | Yes | admin | Name of the user getting the credentials. Let as default if it is used in Eucalyptus setup playbook
| account | Yes | eucalyptus | Name of the account in which the user is. Again, let as-is if use in Eucalyuptus Setup playbook
| euca_admin_zip_path | Yes | /var/tmp/ | Folder in which the .zip file will be stored
| euca_admin_zip_file | Yes | admin.zip | Name of the .zip file containing credentials
| euca_admin_creds_path | Yes | /var/tmp/creds/ | Folder in which will the credentials be expanded
| euca_admin_creds_file | Yes | eucarc | Name of the file which sets the environment values and contains API keys


Dependencies
------------

None. This role can be used anytime by the CLC host, and also be used as a dependency for other roles

Example Playbook
----------------

```

- hosts: clc
  roles:
  - JohnPreston.eucalyptus-credentials

```

```

- hosts: clc
  roles:
  - JohnPreston.eucalyptus-credentials
  vars:
  - euca_admin_zip_path: /root/
  - user: john
  - account: ews

```


License
-------

BSD

Author Information
------------------

John Preston [John Mille]

