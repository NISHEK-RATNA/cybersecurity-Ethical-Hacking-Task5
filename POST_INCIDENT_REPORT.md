# ApexPlanet Task 5 – Post-Incident Report

## 1. Incident Overview

A controlled incident response simulation was performed against the DVWA web application running on the local Kali Linux system. The purpose was to demonstrate how a suspicious web request can be detected, analyzed, contained, and recovered from in an authorized laboratory environment.

## 2. Incident Type

Simulated Web Application Security Incident

## 3. Detection

A controlled request containing the parameter `incident_response` was sent to the DVWA application.

The Apache access log was monitored using the Apache log file. The new request was identified as a suspicious test event.

Evidence:
- Incident_Detected_In_Log
- Apache access log output

## 4. Analysis

The Apache access log was searched for the `incident_response` request. The request was reviewed to identify the affected resource and confirm that the simulated event had been recorded.

Evidence:
- Incident_Analysis

## 5. Containment

A temporary firewall rule was applied using iptables to block the simulated source address:

127.0.0.1

This demonstrated how network-level controls can be used to contain suspicious traffic during an incident.

Evidence:
- Incident_Containment_Firewall

## 6. Eradication

The temporary firewall containment rule was removed after the simulation. No malicious software was deployed, and no real system compromise was performed.

The simulated threat was therefore considered eradicated from the test scenario.

## 7. Recovery

After removing the temporary firewall rule, the DVWA application was accessed again through the browser.

The DVWA Home page loaded successfully, confirming that the application was functioning normally after the incident-response simulation.

Evidence:
- Incident_Recovery_Verification

## 8. Lessons Learned

The simulation demonstrated the importance of:

- Continuous monitoring of web server logs.
- Detecting unusual requests quickly.
- Analyzing security events before taking action.
- Using firewall controls for temporary containment.
- Removing temporary containment rules after verification.
- Testing application availability after recovery.
- Maintaining proper evidence and documentation.

## 9. Recommended Improvements

For a real production environment, the following controls are recommended:

- Centralized security log collection.
- Automated alerting for suspicious requests.
- Web Application Firewall (WAF).
- Strong input validation.
- Prepared statements for database queries.
- Secure HTTP headers.
- Regular vulnerability assessments.
- Regular backups and recovery testing.
- Incident response procedures and documentation.

## 10. Conclusion

The incident response simulation successfully demonstrated the basic incident response lifecycle: detection, analysis, containment, eradication, and recovery. All activities were performed in a controlled and authorized DVWA laboratory environment for cybersecurity learning purposes.
