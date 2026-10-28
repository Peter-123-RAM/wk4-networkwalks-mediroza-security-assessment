# WK4 Networkwalks Project — Mediroza Web Application Security Assessment

> **Educational capstone:** Networkwalks B083 · Week 4  
> **Classification:** Sanitised project summary  
> **Important:** Do not publish patient records, staff personal data, passwords, raw database backups, or confidential screenshots.
 **Done By Eng. ADONGO PETER :** Networkwalks B083 · Week 4
## Overview

This project summarises a black-box web application security assessment documented in the supplied Week 4 project materials for the Mediroza General Hospital web application. The source report records seven findings spanning authentication, SQL injection, access to patient PDFs, weak document passwords, PDF metadata, directory listing, and exposure of a database backup.

The source report rates the overall risk as **Critical**. This README is a summary of the provided report and does not independently validate the target or confirm current remediation status.

## Findings at a glance

| # | Finding | Reported severity |
|---|---|---|
| 1 | Username enumeration through differing login errors | Medium |
| 2 | SQL injection login bypass | Critical |
| 3 | Patient PDFs accessible after authentication bypass | High |
| 4 | Weak PDF passwords reportedly recoverable using wordlists | High |
| 5 | Internal information exposed in PDF metadata | Medium |
| 6 | Directory listing exposed an old backup directory | Critical |
| 7 | SQL backup reportedly contained staff salary and shareholder information | Critical |

## Attack-chain summary

1. Reconnaissance reportedly revealed application paths.
2. Login error differences enabled username enumeration.
3. SQL injection reportedly bypassed patient-portal authentication.
4. Patient report PDFs were accessed.
5. Weak PDF passwords were reportedly recovered.
6. Document metadata disclosed a path to an old backup.
7. Directory listing exposed a SQL backup containing sensitive organisational records.

## Recommended remediation

- Use parameterised queries/prepared statements for all database operations.
- Return generic authentication failure messages and apply rate limiting.
- Enforce server-side authentication and per-record authorisation before serving patient documents.
- Store backups outside the public web root and restrict access.
- Disable directory listing across the web server.
- Remove unnecessary metadata and internal comments from documents before publication.
- Review logs for possible unauthorised access, rotate potentially exposed secrets, and conduct a documented retest.

## Tools listed in the source report

- `curl`
- Browser developer tools
- Networkwalks Hash Calculator
- Networkwalks Password Cracker
- `qpdf`
- `exiftool`
- `wget`
- ChatGPT for formatting raw SQL records into readable tables

## Learning outcomes

- Recognising how authentication weaknesses can combine with server misconfiguration.
- Understanding the confidentiality risks of public backups and document metadata.
- Prioritising remediation by severity and business impact.
- Producing a structured security report with findings, attack-chain analysis, and remediation guidance.
- Practising responsible handling of sensitive evidence.

## Responsible-use statement

Perform security testing only with explicit written permission and within the agreed scope. This repository should contain only sanitised documentation, safe diagrams, and redacted evidence. Never upload patient data, employee personal data, credentials, passwords, raw database dumps, or other confidential materials.



