`unix_installer.properties`

```yaml
INSTALLER_UI=SILENT
ACCEPT_EULA=ACCEPT
#Make sure ACCEPT_EULA is set to ACCEPT
USER_INSTALL_DIR=/opt/CA/WA_Agent
AGENTPARM_CONVERT_2=No
AGENT_INFO_1=hkgabdlapp02a
AGENT_INFO_2=7520
NUM_MANAGER_1=2
# Add manager1
MANAGER_1_INFO_1=HKD
MANAGER_1_INFO_2=10.115.101.180
MANAGER_1_INFO_3=7507
# Add manager2
MANAGER_2_INFO_1=HPI
MANAGER_2_INFO_2=10.115.186.45
MANAGER_2_INFO_3=7507
# plugin functions
ENABLE_AE_FIPS_140_2_COMPLIANCE=false #  Disable FIPS 140-2 Compliancy
LOCAL_SECURITY=off
SNMP_MGMT_CONN=0	#  Disable SNMP Management Connector Option
JMX_PLUGIN=0	# Disable JMX Connector 
FTP_PLUGIN=1	# Enable FTP plug-in
FTP_SSL_CLIENT_ENABLED=false # Enables regular encryption,FTP Plug-in Information - Client
FTP_NO_SERVER=false # Sets whether the agent can act as an FTP server.
SNMP_PLUGIN=0 # Disable SNMP Job Type
CA_SOCKET=0 # Disable SSA
# service 
SERVICE_AUTO_START=true
AUTOSYS_MODE=true
USER_INSTALL_MODE=auto


```

