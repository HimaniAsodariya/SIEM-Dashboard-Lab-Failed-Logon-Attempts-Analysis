# SIEM-Dashboard-Lab-Failed-Logon-Attempts-Analysis
Developed a SIEM dashboard in Kibana to monitor failed login attempts (Event ID 4625) across Windows systems Applied KQL filters to detect suspicious authentication patterns and exclude system accounts Visualized user activity, host systems, and logon types to support SOC-level threat analysis

## Overview  
This project demonstrates the creation of a SIEM dashboard using Kibana as part of the HTB Academy Security Monitoring & SIEM Fundamentals module.  
The dashboard focuses on detecting and analyzing failed Windows logon attempts (Event ID 4625), helping identify suspicious authentication behavior and potential brute-force attacks.

## Objectives  
- Build a SIEM dashboard from scratch  
- Visualize failed logon attempts across systems  
- Apply filters and queries using KQL  
- Analyze user and host activity  
- Improve dashboard readability and usability  

## Tools & Technologies  
- Kibana (Visualization & Dashboard)  
- Elasticsearch (Data storage & indexing)  
- Windows Event Logs  
- KQL (Kibana Query Language)  

## Lab Implementation  

### 1. Dashboard Setup  
- Accessed Kibana interface  
- Removed default dashboard  
- Created a new dashboard and visualization  

### 2. Data Filtering  
- Index pattern: `windows*`  
- Time range: Last 15 years  
- Filter applied:
  
### 3. Visualization Configuration  
- Visualization type: Table  
- Fields used:
- `user.name.keyword` → Username  
- `host.hostname.keyword` → Event Source  
- `winlog.logon.type.keyword` → Logon Type  
- Metric:
- Count of records (# of logins)  

### 4. Refinement & Optimization  
- Renamed columns for clarity  
- Sorted results by login count (descending)  
- Excluded machine/system accounts  
- Applied advanced KQL filter:

## Results  
The dashboard provides visibility into:  
- Users with the highest failed login attempts  
- Systems generating authentication failures  
- Logon types used in failed attempts  

## Key Learnings  
- Practical SIEM dashboard creation  
- Log analysis using Windows event logs  
- Data aggregation using `.keyword` fields  
- KQL filtering for threat detection  
- Importance of visualization in SOC operations  
