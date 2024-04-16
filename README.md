# ansible roles:
*linux_upgrade_rhel7_to_rhel8* - upgrade Red Hat Enterprise Linux from version RHEL7 to RHEL8, using leapp-upgrade tool and inernal satellite server <br /><br />
*linux_upgrade_rhel7_to_rhel8* - upgrade Red Hat Enterprise Linux from version RHEL8 to RHEL9, using leapp-upgrade tool and inernal satellite server <br />
 The role requires satellite ansible connection (can be install from git - meta/requirements.yml or ansible collection hub) and preconfigured content view on the satellite server. 
 Following variables must be set:
   upgrade_contentview_name: <upgrade content view>
   rhel9_contentview_name: <post upgrade rhel9 content view>
   satellite_organization: <satellite organization>
   satellite_server: <satellite url>
   satellite_username: <satellite username>
   satellite_password: <satellite password> 
 Upgrade process is split into stages. Execution of each stage is controled by variable defined in default/main.yml.
 For open scan security hardedning, definition file must be uploaded in files/.
<br />
*ms_devops_setup* - setup Linux server for Azure selfhosted agent. The script uses standard and custom repositories defined on local satellite server. Supports RHEL8 and RHEL9. For customization change variable values in default/main.yml file. <br /> <br />
*linux_rear* - kick off preconfigured rear backup.

# ansible playbooks
*setup_azure_devops_agent.yml* - install/uninstall chosen number of Azure devops selfhosted agents
