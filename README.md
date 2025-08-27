# Cloud SIEM Lab

## Overview
This project demonstrates a cloud security monitoring lab using AWS CloudTrail, Splunk, and MITRE ATT&CK. I uploaded JSON CloudTrail events from a test user account to Splunk, built dashboards to visualize login activity and access attempts, and applied detection use cases mapped to MITRE ATT&CK. I plan to continue refining this lab to expand detection capabilities (see the [future improvements](#future-improvements) section)

## Features
- Ingested CloudTrail JSON logs into Splunk  
- Built dashboards with multiple panels for login activity and access attempts  
- Implemented SPL queries for failed logins, successful logins, denied access, and geographic mapping  
- Used MITRE ATT&CK techniques T1110 (Brute Force) and T1078 (Valid Accounts) as detection references  

## Dashboard Panels
1. **Total Failed Logins**: Counts failed AWS ConsoleLogin attempts  
2. **Total Successful Logins**: Tracks valid console logins  
3.  **Denied Access Attempts**: Timechart of `AccessDenied` API events  
4. **Activity by Country**: Map visualization of login activity by country  

---

## Sample Log
This repo includes an example CloudTrail log of a failed IAM user sign-in (`aws/sample_log.json`). This sample is from AWS documentation and contains no real credentials or sensitive data. It is included only to demonstrate log structure and for testing queries.

Reference: [AWS CloudTrail Console Sign-In Events Example](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-aws-console-sign-in-events.html#cloudtrail-aws-console-sign-in-events-iam-user-failure)

---

## SPL Queries
All queries used in the dashboard are saved in `splunk/searches.txt`.  

---

## Future Improvements
- **Continuous CloudTrail Ingestion**: Integrate directly with an S3 bucket for real-time log collection and monitoring.  
- **Behavioural and Anomaly Detection**: Identify unusual login patterns, failed login spikes, or suspicious activity trends.  
- **Automated Alerting & Notifications**: Configure alerts for repeated failed logins, denied access, or other high-risk events.  

