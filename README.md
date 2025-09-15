# azure-soc-homelab
Azure SOC home lab using Microsoft Sentinel, Log Analytics, and KQL to monitor security events with custom dashboards and visualizations.

# Azure SOC Home Lab

This project is a home lab built in Microsoft Azure to simulate a Security Operations Center (SOC).  
It demonstrates how to collect, analyze, and visualize security events using Azure services.

## Project Overview
- **Resource Group**: Central hub for Azure resources.  
- **Virtual Network & Virtual Machine**: Deployed a VM inside a VNet.  
- **Network Security Configuration**: Disabled RDP (Remote Desktop Protocol) to reduce attack surface.  
- **Log Analytics Workspace**: Centralized log collection.  
- **Microsoft Sentinel**: Security Information and Event Management (SIEM).  
- **Workbooks**: Created custom dashboards, including a virtual map (JSON template included).  
- **KQL Queries**: Used Kusto Query Language to filter logs by Event IDs, track failed and successful logins, and visualize activity.  

## Technologies Used
- Microsoft Azure  
- Microsoft Sentinel  
- Log Analytics  
- KQL (Kusto Query Language)  
- JSON  

## Example Queries
- **Failed logins**  
  ```kql
  SecurityEvent
  | where EventID == 4625
  | summarize Count = count() by Account, Computer

  - **Successful logins**  
  ```kql
  SecurityEvent
  | where EventID == 4624
  | summarize Count = count() by Account, Computer
