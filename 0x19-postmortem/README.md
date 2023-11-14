**Incident Postmortem: Critical Service Outage**

**Posted**: Tuesday, November 14, 2023

By Anthony Ndolo - ALX SE student

# Table of Contents
***

* [Issue Summary](#Issue-summary)

**Issue Summary**:

**Duration**: The outage occurred on November 13, 2023, from 02:00 AM to 06:00 AM (UTC).

**Impact**: During the incident, the authentication service was down, resulting in users experiencing login failures and a 503 error. Approximately 75% of users were affected.

**Root Cause**: The root cause of the outage was a misconfiguration in the load balancing system, causing a failure in distributing traffic to the authentication servers.

**Timeline (UTC)**:

* 02:00 AM: Issue detected through automated monitoring alerts indicating a spike in authentication errors.
* 02:10 AM: Initial investigation focused on the authentication service logs to identify any anomalies.
* 02:30 AM: Misleading assumption made that the issue might be related to a recent deployment; investigation into recent changes initiated.
* 03:00 AM: Load balancing misconfiguration identified as the root cause; corrective measures initiated.
* 03:30 AM: Incident escalated to the infrastructure team for further assistance and expertise.
* 04:00 AM: Load balancing misconfiguration rectified, and traffic distribution normalized.
* 06:00 AM: Service fully restored; monitoring in place to ensure stability.

**Root Cause and Resolution**:

**Root Cause**: The misconfiguration in the load balancing system resulted in an uneven distribution of traffic to the authentication servers. Specifically, an incorrect weight assignment led to a bottleneck in one of the servers, causing authentication failures.

**Resolution**: The issue was addressed by correcting the load balancing configuration. The weights were adjusted, ensuring a balanced distribution of incoming traffic among the authentication servers. This solution was promptly applied, restoring normal operation.

**Corrective and Preventative Measures**:

**Improvements/Fixes**:

Load Balancer Configuration Review: Conduct a comprehensive review of load balancer configurations to identify and rectify potential misconfigurations.
Automated Anomaly Detection: Enhance automated monitoring with anomaly detection to quickly identify and alert on irregularities in system behavior.

**Tasks**:

**Load Balancer Configuration Audit**: Schedule a regular audit of load balancer configurations to prevent similar misconfigurations.
**Automated Rollback Procedures**: Implement automated rollback procedures to swiftly revert to a stable configuration in the event of issues post-deployment.
