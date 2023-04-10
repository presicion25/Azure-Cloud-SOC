## Microsoft Azure SOC and HoneyNet


<p align="center">
<img src="https://imgur.com/cW8RYr1.png alt="Traffic Examination"/>  
</p>



## Summary

For this project, I built a HoneyNet and SOC in Microsoft Azure. To accomplish this, I provisioned all of the resources necessary for a cloud infrastructure including virtual machines, flow logs for each VM, a log analytics workspace to ingest the log data, a key vault, a storage account, vnets, network security groups and a SIEM (Azure Sentinel). After provisioning, I left the resources exposed to the internet in order to gather attack data for 24 hours. The environment was then hardened and left on for another 24 hours. Finally I gathered log data and created a spreadhseet to show the change in traffic patterns in the 24 hour period after the environment was hardened.
<br />
<br />


## Environments and Architecture Technologies Used

- Microsoft Azure (Cloud Platform)
  - Resource Groups
  - Azure Virtual Machines (2 Windows, 1 Linux)
  - Log Analytics Workspace
  - Azure Sentinel (SIEM)
  - Key Vault
  - Storage Account
  - Network Security Groups
  - Microsoft Defender for Cloud (Cloud-native Application Protection Platform (CNAPP))
  
 - Remote Desktop Protocol (Used for logging in to the VMs)
 - OSB Studio (For recording some my labs showcasing the procedures)
 
 ## Security Metrics Used for Queries in the Log Analytics Workspace
 
 - Syslog (For Linux Event Logs)
 - SecurityIncident (For Sentinel Created Incidents)
 - SecurityAlert (For Alerts Triggered in the Log Analytics Work Space)
 - AzureNetworkAnalytics_CL (For Malicious Events Triggered)
 - SecurityEvent (For Windows Event Logs)
 <br />
 <br />
 
 
  ## Architecture Before Hardening
  
  Before hardening, all resources were exposed to the internet with public endpoints with the Network Security Group firewalls wide open.
  <br />
  <br />
  ![Architecture Diagram](https://imgur.com/TcINeqM.png)
  <br />
  <br />
  
 ## Attack Maps Before Environment Hardening 
 These maps show malicious traffic attempting to penetrate the Azure environment before security controls were implemented. 
 
  ![Attack Map](https://imgur.com/JF0gqP9.png)
  <br />
  <br />
  ![Attack Map](https://imgur.com/86YhWnh.png)
  <br />
  <br />
  ![Attack Map](https://imgur.com/XJnrrgq.png)
  <br />
  <br />
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
