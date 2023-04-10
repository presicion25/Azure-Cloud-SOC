## Microsoft Azure SOC and HoneyNet


<p align="center">
<img src="https://imgur.com/cW8RYr1.png alt="Traffic Examination"/>  
</p>



## Summary

For this project, I built a HoneyNet and SOC in Microsoft Azure. To accomplish this, I provisioned all of the resources necessary for a cloud infrastructure including virtual machines, flow logs for each VM, a log analytics workspace to ingest the log data, a key vault, a storage account, vnets, network security groups and a SIEM (Azure Sentinel). After provisioning, I left the resources exposed to the internet in order to gather attack data for 24 hours. The environment was then hardened and left on for another 24 hours. Finally, I gathered log data and created a spreadhseet to show the change in traffic patterns in the 24 hour period after the environment was hardened.
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
  
  Before hardening, all resources were exposed to the internet with public endpoints and the Network Security Group firewalls were wide open.
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
  
  ## Metrics Before Implementing Security Controls
  
  The below table displays the metrics that were measured while the environment was insecure for 24 hours:
  
  ![Before Table](https://imgur.com/7TtL0tn.png)
  
  <br />
  <br />
  
  
  ## Architecture After Hardening
 
  
  After hardening, the VMs had their exposed ports (RDP/SSH) closed, the resources were all secured behind firewalls and a v-net with it's own network security group. Firewall rules were then set to only allow my workstation PC to access any of the resources in the environment for purposes of gathering log traffic data.
  <br />
  
  ![Architecture Diagram](https://imgur.com/ZBGHKPC.png)
  <br />
  <br />
  
   ## Metrics After Implementing Security Controls 
   
   The below table displays the metrics that were measured after the environment was hardened with security controls for 24 hours.
  
  ![After Table](https://imgur.com/u8PKIIQ.png)
  <br />
  <br />
  
 ## Rate of Change
 
 ![Rate of Change Table](https://imgur.com/cQHeXFV.png)
 <br />
 <br />
 
 
  ## Conclusion
  
  In this project I constructed a honeynet in Microsoft Azure with log sources that were integrated into a log analytics workspace. I also deployed Azure Sentinel in order to trigger alerts and incidents based on the log data from the log analytics workspace. There were metrics measured 24 hours after the creation all insecure resources and then 24 hours after implementing security controls. As seen in the metric data tables there was a dramatic drop in incidents because security controls were put in place which illustrates their effectiveness.
  
 Please note: This project was done in a controlled environment so results will vary based on applied situation.
  
   
  <h1>Thank Your for looking! For more content like this, visit <a href="https://exemplarysecurity.com">my website</a>☺</h1>
  
