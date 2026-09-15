# ApexPlanet Task 5 – Findings and Mitigations

## 1. Finding: SQL Injection

### Description
A controlled SQL Injection test was performed against the DVWA application with the security level set to Low. The test demonstrated that user input can be interpreted as part of a database query when proper input validation and query protection are not implemented.

### Evidence
The SQL Injection test was captured as a screenshot and included in the project evidence.

### Risk
SQL Injection can potentially allow unauthorized access to database information, modification of data, authentication bypass, or other unintended database operations.

### Severity
High

### Mitigation
- Use prepared statements and parameterized SQL queries.
- Validate and sanitize user input.
- Avoid directly concatenating user input into SQL queries.
- Apply the principle of least privilege to database accounts.
- Use secure error handling so database details are not exposed.
- Perform regular application security testing.

## 2. Finding: Missing/Weak Security Controls in the Test Application

### Description
The DVWA application was intentionally configured at Low security for controlled security testing. This configuration allows vulnerabilities to be demonstrated in the laboratory environment.

### Risk
Weak security controls can make a web application more susceptible to common attacks.

### Mitigation
- Use secure application configurations in production.
- Implement strong input validation.
- Apply secure coding practices.
- Use appropriate security headers.
- Keep Apache, PHP, and application components updated.
- Conduct regular vulnerability assessments and penetration testing.

## 3. Finding: Suspicious Request Detection Through Apache Logs

### Description
A controlled test request containing the parameter `incident_response` was generated against the DVWA application. The request was detected in the Apache access log and then analyzed.

### Evidence
The incident detection and analysis screenshots show the request in the Apache access log.

### Mitigation
- Monitor web server access logs regularly.
- Configure centralized log collection where possible.
- Create alerts for suspicious or unusual requests.
- Maintain appropriate log retention.
- Investigate abnormal requests promptly.

## 4. Incident Containment

### Description
During the incident response simulation, a temporary firewall rule was applied using iptables to block the simulated source address.

### Evidence
The firewall rule and its verification were captured in the Incident Containment screenshot.

### Mitigation
- Use firewall rules to isolate suspicious traffic when appropriate.
- Restrict unnecessary network access.
- Maintain documented firewall policies.
- Review temporary containment rules after the incident.

## 5. Recovery

### Description
After the temporary containment rule was removed, DVWA access was tested again to verify that the service was functioning normally.

### Evidence
The Incident Recovery Verification screenshot demonstrates successful recovery.

### Overall Security Recommendation

The DVWA environment is intentionally vulnerable and should only be used in an isolated and authorized laboratory. For real applications, secure coding, input validation, parameterized queries, strong authentication, security headers, logging, monitoring, patch management, and regular security testing should be implemented.
