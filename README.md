# Secure Azure Containerized Web App with WAF & Monitoring

## Overview
This project demonstrates the design and deployment of a secure, enterprise-style Azure environment hosting a containerized web application. The focus is on cloud networking, application security, monitoring, and incident detection-core responsibilities in IT Support and Cloud Operations roles.

## Architecture
- Hub–spoke virtual network design
- Azure Web App for Containers (Linux)
- Azure Application Gateway (WAF v2) as a secure front door
- Centralized logging with Azure Monitor and Log Analytics

## Key Features
- Secure traffic routing through Application Gateway (WAF v2)
- Container-based application hosting using Microsoft Container Registry
- Centralized diagnostics and log collection
- KQL-based log analysis for HTTP status codes
- Alerting for application failures

## Implementation Highlights
- Designed VNets, subnets, and VNet peering for secure segmentation
- Deployed a Linux-based Web App for Containers using a public container image
- Configured Application Gateway backend pools using FQDN routing
- Enabled diagnostic logging for App Service and Application Gateway
- Queried logs using KQL to validate application health
- Configured Azure Monitor alerts for HTTP 5xx errors


## Screenshots

### Web App Running
The containerized web application successfully deployed and running on Azure Web App for Containers.
![Web App Running](webapp-running.png)

### Application Gateway Backend Health
Backend pool health showing successful routing through Azure Application Gateway (WAF v2).
![Application Gateway Backend Health](application-gateway-backend-health.png)

### Log Analytics KQL Results
KQL query results from Azure Log Analytics analyzing HTTP status codes for application traffic.
![Log Analytics KQL Results](log-analytics.png)

### Aleert rules
Alert rule configured to detect HTTP server errors and notify support teams.
![Alert Rules](alert-rules.png)


## Monitoring & Troubleshooting
Logs are collected in a Log Analytics workspace and queried using KQL to analyze traffic patterns and application health.

Example query:
```kusto
AppServiceHTTPLogs
| summarize Count = count() by ScStatus
| order by ScStatus desc

