Role Name
=========

This role automates upgrade process of Red Hat Enterprise Linux from version 7 to version 8.

Requirements
------------

The role uses leap upgrade tool and preconfigured internal satellite server. Satellite must have configured migration convent view, which includes RHEL7 and RHEL8 repositories as per Red Hat documentation. The target RHEL8 repositories must be 8.6. 
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
Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: linux_upgrade_rhel7_to_rhel8

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
