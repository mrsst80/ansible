Role Name
=========

This role automates upgrade process of Red Hat Enterprise Linux from version 7 to version 8.

Requirements
------------

The role uses leap-upgrade tool and preconfigured internal satellite server. Satellite must have configured migration convent view, which includes RHEL7 and RHEL8 repositories as per Red Hat documentation. The target RHEL8 repositories must be version 8.6. 
The ansible_user configured to connect to satellite server, must have permission to use hammer tool without password. 

Role Variables
--------------

Mandatory variables
```
upgrade_contentview_name       - name of the upgrade content view
upgrade_contentview_rhel8_name - target content view to be configured after the upgrade
satellite_organization         - organization name configured in satellite
satellite_server               - hostname of the satellite server
```
Boolean variables, which control stages of Red Hat Linux Upgrade with their default values defined in default/main.yml:
```
leapp_install: true        - install leapp-upgrade package
leapp_data: true           - extract leapp-data file
kernel_versions: true      - remove kernel and kernel-devel package versions not in use
upgrade_content_view: true - upgrade host conntent view to upgrade one
leapp_preupgrade: true     - preupgrade tasks including leapp preupgrade 
leapp_upgrade: true        - actual upgrade and reboot in the end
leapp_postupgrade: true    - post upgrade tasks including change of the content view from upgrade to new rhel8 only based
oscap_hardening: false     - optional security hardening task, which require customzied oscap file

```
Dependencies
------------

N/A

Example Playbook
----------------

Usage:

    - hosts: servers
      become: true
      gather_facts: true
      vars:
        leapp_install: true
        leapp_data: true
        kernel_versions: true
        upgrade_content_view: true
        leapp_preupgrade: true
        leapp_upgrade: true
        leapp_postupgrade: true
        oscap_hardening: false
      roles:
         - role: linux_upgrade_rhel7_to_rhel8

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
