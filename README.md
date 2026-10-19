# Runes SOC Lab — Linux Authentication Monitoring

A hands-on SOC investigation lab focused on detecting automated credential-guessing activity through Linux system and application logs.

The project demonstrates a practical workflow for monitoring authentication attempts, investigating suspicious login activity, and correlating web-server telemetry with application-level authentication events.

## Objectives

- Identify repeated login attempts against a web application.
- Analyze successful and failed authentication events.
- Correlate Apache access logs with application authentication logs.
- Document findings and distinguish confirmed evidence from assumptions.

## Lab Environment

| Component | Technology |
|---|---|
| Operating system | Kali Linux |
| Web server | Apache2 |
| Application | PHP |
| Database | MariaDB |
| Traffic analysis | Burp Suite Community Edition |
| Log analysis | Linux CLI, `grep`, `awk` |

## Investigation Workflow

1. Establish normal application and authentication behavior.
2. Generate controlled credential-guessing traffic using Burp Suite Intruder.
3. Review repeated HTTP requests and response patterns in Apache `access.log`.
4. Analyze `LOGIN_FAILURE` and `LOGIN_SUCCESS` events in `runes_auth.log`.
5. Correlate evidence across both log sources and document the findings.

## Key Findings

- Repeated login submissions consistent with automated credential guessing were observed.
- Six successful authentication events were identified in the captured investigation output.
- Corresponding HTTP 302 responses were observed in Apache access logs.
- The evidence confirms successful authentication events in the lab, but does not establish post-authentication impact or account compromise beyond the observed test scenario.

## Evidence and Report

The full investigation report includes the lab setup, screenshots, log evidence, event correlation, assessment of findings, and example detection logic.
[Read the full investigation report (PDF)](./Runes_Linux_Detection_Lab.pdf)

## Scope

All tests were conducted in a controlled lab environment against a test application. The results demonstrate a practical security-monitoring workflow and should not be interpreted as evidence of a real-world compromise.

