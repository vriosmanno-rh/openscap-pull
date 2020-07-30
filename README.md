Role Name
=========

A simple role to download openscap OVAL definitions for RHEL 4+.

Requirements
------------

- Ansible >= 2.4

Role Variables
--------------
--------------

| Parameter | Type | Required |  Default Value | Comments |
| --------- | ---- | -------- | -------------- | -------- |
| **content_sync_path** | string | yes | *undefined* | The destination path for the openscap OVAL definitions |
| **openscap_urls** | list | yes | *rhsa.tar.bz2<br />com.redhat.rhsa-all.xml.bz2* | The URLs to download for the openscap OVAL definitions |

Examples
--------

### Running with defaults
```yaml
- name: openscap-pull example
  hosts: localhost
  roles:
    - role: openscap-pull
      tags:
        - openscap-db
```

### Running with different opencap_urls
```yaml
- name: openscap-pull example with different openscap_urls
  hosts: localhost
  roles:
    - role: openscap-pull
      tags:
        - openscap-db
      vars:
        openscap_urls:
          - https://www.redhat.com/security/data/oval/rhsa.tar.bz2 # This is the default
          - https://www.redhat.com/security/data/oval/com.redhat.rhsa-all.xml.bz2 # This is the default
```

License
-------

GPLv3
