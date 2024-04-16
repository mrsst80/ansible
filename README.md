# ansible roles:
*linux_upgrade_rhel7_to_rhel8* - upgrade Red Hat Enterprise Linux from version RHEL7 to RHEL8, using leapp-upgrade tool and inernal satellite server <br /><br />
*linux_upgrade_rhel7_to_rhel8* - upgrade Red Hat Enterprise Linux from version RHEL8 to RHEL9, using leapp-upgrade tool and inernal satellite server <br />
 The role requires satellite ansible connection (can be installed from git - meta/requirements.yml or ansible collection hub) as well as preconfigured content view on the satellite server. <br />
 Following variables must be set: <br /><br />
   upgrade_contentview_name: upgrade_content_view <br />
   rhel9_contentview_name: post_upgrade_rhel9_content_view <br />
   satellite_organization: satellite_organization <br />
   satellite_server: satellite_url> <br />
   satellite_username: satellite_username <br />
   satellite_password: satellite_password <br /><br />
 Upgrade process is split into stages. Execution of each stage is controled by variable defined in default/main.yml. <br />
 For open scan security hardedning, definition file must be uploaded in files/. <br />
<br />
*ms_devops_setup* - setup Linux server for Azure selfhosted agent. The script uses standard and custom repositories defined on local satellite server. Supports RHEL8 and RHEL9. For customization change variable values in default/main.yml file. <br /> <br />
*linux_rear* - kick off preconfigured rear backup.

# ansible playbooks
*setup_azure_devops_agent.yml* - install/uninstall chosen number of Azure devops selfhosted agents
