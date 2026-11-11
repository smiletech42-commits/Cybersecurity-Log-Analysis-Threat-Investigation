# Cybersecurity Log Analysis & Threat Investigation

## Project Overview

This project focuses on analysing cybersecurity log records for Northstar Services, a fictional organisation experiencing increased failed login attempts, suspicious IP address activity and unresolved security alerts.

Using MySQL, the investigation explores employee login behaviour, IP address reputation, device usage and security alert patterns to identify potentially suspicious activities, uncover security weaknesses and provide actionable recommendations to management.

The objective is to transform raw security records into meaningful insights that support better access control, threat monitoring and cybersecurity decision-making.

## Business Problem

Northstar Services has observed unusual authentication activities across its systems, including:

- Increased failed login attempts.
- Login attempts originating from unfamiliar and high-risk IP addresses.
- Unusual employee account and device activity.
- Unresolved high-severity security alerts.

Management requires a data-driven investigation to understand these patterns, identify accounts and activities requiring attention, and recommend appropriate security improvements.

## Project Objectives

- Investigate login activity and authentication patterns.
- Identify employee accounts with repeated failed login attempts.
- Analyse IP addresses based on their reputation and associated login activities.
- Examine employee behaviour, device usage and departmental login patterns.
- Evaluate security alerts, severity levels and resolution times.
- Identify unusual activity and potential security risks.
- Develop actionable recommendations supported by SQL findings.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| MySQL | Data querying, transformation and investigation |
| SQL | Data cleaning, aggregation and analysis |
| GitHub | Project documentation and version control |

## Dataset Description

The project uses five interconnected CSV datasets containing fictional cybersecurity records.

| Dataset | Description | Records |
|---|---|---:|
| employees.csv | Employee information, departments, roles and employment status | 18 |
| devices.csv | Employee-associated devices and operating systems | 20 |
| login_logs.csv | Login timestamps, IP addresses and authentication outcomes | 238 |
| security_alerts.csv | Security alert types, severity and resolution status | 15 |
| ip_reputation.csv | IP address reputation, country and risk classification | 12 |

**Total records: 303**

## Data Quality Assessment

Before conducting the investigation, the datasets were examined for data quality issues that could affect analytical accuracy.

Key observations included:

- One missing IP address in the login records.
- Eight missing security alert resolution timestamps, requiring validation against alert status.
- An inactive employee account with 19 recorded login events, including 11 successful logins.
- Different column names between the supplied database structure and the actual CSV files.
- Repeated login timestamps requiring investigation to distinguish legitimate simultaneous events from duplicate records.
- Unknown country classifications in the IP reputation dataset.

Data quality checks included missing-value identification, duplicate primary key validation, data type inspection and relationship validation across tables.

## SQL Analysis & Investigation

The investigation was organised into five major analytical areas.

### 1. Login Activity Analysis

- Total login events and dataset coverage.
- Successful versus failed login proportions.
- Failed login patterns by day of the week and hour.
- Employee accounts with the highest failed login attempts.
- Identification of repeated failed logins followed by successful authentication.

### 2. IP Address Investigation

- IP addresses generating the highest login volumes.
- IP addresses associated with repeated failed login attempts.
- Analysis of successful logins from high-risk IP addresses.
- Country and IP reputation classification analysis.
- Development of rules for identifying potentially suspicious login activities.

### 3. Employee & Device Analysis

- Identification of employees accessing systems through multiple devices.
- Analysis of login activities outside assumed working hours.
- Devices associated with the highest failed login attempts.
- Departmental login failure rates.
- Identification of unusual employee and device activity.

### 4. Security Alert Analysis

- Security alerts grouped by severity.
- Identification of frequently occurring alert types.
- Resolved versus unresolved alert analysis.
- Identification of unresolved High and Critical alerts.
- Calculation of security alert resolution times.
- Daily and weekly failed-login trend analysis.

### 5. Advanced SQL Investigation

- Ranking employee accounts by failed login attempts.
- Comparing departmental failure rates against the company average.
- Period-over-period login activity comparison.
- Creation of reusable SQL views for management reporting.
- Prioritisation of areas requiring further security investigation.

## Key Findings & Business Insights

The analysis produced the following significant findings:

**1. Login Authentication Patterns**

Out of 238 recorded login events, 159 were successful (66.81%), while 79 failed (33.19%). This indicates a considerable level of unsuccessful authentication activity.

**2. Departmental Security Exposure**

The Finance department recorded the highest login failure rate at 48.94%, followed by HR at 40% and IT at 36.21%. These departments require closer examination.

**3. High-Risk IP Activity**

Two successful login events were associated with IP addresses classified as High Risk. These events require further investigation to establish whether the access was authorised.

**4. Inactive Employee Account Activity**

An inactive employee account recorded 19 login events, comprising 11 successful and 8 failed attempts. This highlights a potential weakness in account deactivation and access management.

**5. Unresolved Security Alerts**

The monitoring system generated 15 security alerts, of which 7 were resolved and 8 remained Open or under Investigation. Six unresolved alerts were classified as High or Critical.

**6. Increase in Failed Login Activity**

The week beginning 14 September 2026 recorded 28 failed login attempts, compared with 11 in the preceding week, representing an increase of approximately 154.55%.

## Recommendations

Based on the investigation, the following actions are recommended:

1. **Strengthen Account Access Management:** Investigate inactive employee accounts with recorded login activity and ensure that unauthorised accounts are promptly disabled.

2. **Enhance IP Address Monitoring:** Investigate successful authentication attempts originating from high-risk IP addresses and implement additional monitoring for suspicious network activity.

3. **Review Departmental Authentication Patterns:** Prioritise Finance, HR and IT because their login failure rates exceed the overall company failure rate of 33.19%.

4. **Improve Security Alert Resolution:** Establish escalation procedures for unresolved High and Critical alerts and improve response monitoring.

5. **Implement Continuous Login Monitoring:** Regularly monitor failed authentication patterns, unusual login times and sudden increases in suspicious activity.

## SQL Concepts Demonstrated

This project demonstrates practical application of:

- SELECT, WHERE and ORDER BY
- GROUP BY and aggregate functions
- INNER JOIN and LEFT JOIN
- Subqueries and Common Table Expressions (CTEs)
- CASE WHEN statements
- Window functions (RANK, DENSE_RANK and LAG)
- Date and time functions
- Conditional aggregation
- Percentage calculations and comparative analysis
- CREATE VIEW for reusable reporting

## Limitations

- The dataset covers only September 2026 and does not establish long-term trends.
- IP reputation classifications are indicators and do not independently confirm malicious activity.
- The dataset does not contain sufficient information to establish whether unusual employee login activities were authorised.
- The reason for individual failed login attempts is not available.
- The security alerts do not have a direct login event ID for tracing each alert to its originating login.
- Normal working hours were assumed to be 9 AM–5 PM because official company working hours were not supplied.

**Important:** This project identifies suspicious patterns requiring further investigation. It does not claim that a confirmed cyberattack or account compromise occurred.

## Conclusion

This project demonstrates how SQL can be applied to cybersecurity data to uncover authentication patterns, investigate potentially suspicious IP addresses, identify unusual employee account activities and evaluate security alert management.

The investigation highlights the importance of data quality, relational database analysis and evidence-based decision-making in cybersecurity operations.

Beyond identifying unusual activities, the project demonstrates the ability to translate raw operational data into actionable business intelligence and practical recommendations.

---

**Industry:** Cybersecurity / Information Technology  
**Database:** MySQL  
**Data:** Fictional training dataset  
**Project Group:** Group A  
**Organisation:** Tech Studio Academy
