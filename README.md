# 🔐 PCI DSS Password Policy Audit (v4.0.1)

This project simulates an internal PCI DSS audit targeting password policies on a Windows 10 system.  
It includes pre- and post-remediation screenshots, mock interviews, findings, and compliance validation logs.

**Performed by:** Alex Bolden – Internal Security Assessor (ISA)

---

## 🔍 Password Policy Validation – Interview & Evidence Log

This section simulates a real-world PCI DSS v4.0 password policy audit, structured from the perspective of an Internal Security Assessor (ISA). The ISA does not apply system changes but instead requests that the IT Lead (Stone Cold Steve Austin) demonstrate compliance settings, which are then captured as evidence.

### 🧑‍💼 Interview Questions and Evidence Collection

As the ISA, I requested evidence for each PCI DSS v4.0 Requirement 8 password control. Screenshots were taken during the session to verify what the IT Lead showed.

### ✅ Pre-Remediation Questions and Screenshots

| PCI Req | Assessor Question | Screenshot |
|---------|-------------------|------------|
| 8.3.1   | Can you pull up the minimum password length setting? | ![Before](images/pre/password-length.png) |
| 8.3.5   | Can you show me how many previous passwords are remembered? | ![Before](images/pre/password-history.png) |
| 8.3.6   | Where can I verify that password complexity is enabled? | ![Before](images/pre/complexity.png) |
| 8.3.7   | Please show me the password expiration setting (in days). | ![Before](images/pre/expiration.png) |
| 8.3.9   | Can you show me your account lockout threshold? | ![Before](images/pre/lockout-threshold.png) |
| 8.3.9   | Can you show me lockout duration and reset time settings? | ![Before](images/pre/lockout-duration.png) |
| CLI     | Show me 'net accounts' CLI output for global policy confirmation. | ![Before](images/pre/net-accounts.png) |
| CLI     | Can you show me PasswordLastSet date from CLI? | ![Before](images/pre/password-last-set.png) |

> **Note:** The documented password configuration standard was requested but not available during this audit. This was noted as a soft gap under Requirement 12.

---

## 📝 Internal PCI DSS Password Policy Audit Report

**Confidential – For Internal Use Only**

**Organization:** Google.com  
**System Owner:** Stone Cold Steve Austin – IT Lead  
**Audit Performed By:** Alex Bolden – Internal PCI Auditor (ISA)  
**Audit Date:** June 2025  
**Target System:** Windows 10 Standalone VM  

📎 [Click here: For Evidence File](#)

### 📋 Executive Summary

This audit report presents the results of an internal assessment of the password authentication policies configured on a Windows 10 virtual machine used for PCI-related administrative functions.

The goal was to validate compliance with PCI DSS v4.0.1 – Requirement 8. The assessment revealed multiple deficiencies in system configuration — most notably in password length, complexity, expiration, lockout thresholds, and temporary password handling.

This report maps each finding to its associated risk, PCI DSS v4.0.1 requirement, and a clear remediation recommendation. All issues must be addressed before the system can be considered compliant.

### 🖥️ System Design Description

The target system is a Windows 10 standalone VM simulating access to cardholder data. It is configured using local security policy (`secpol.msc`) and does not rely on domain-joined Group Policies. Local user accounts are used to validate enforcement of password and account lockout policies.

System changes are applied manually and validated using PowerShell and command-line tools.

### 👁️‍🗨️ Observations

- Password length set below PCI minimum
- Complexity settings disabled
- Expiration and reuse policies misaligned with standards
- Lockout thresholds too lenient
- No enforcement for temp password reset
- No documented configuration standard or user password guidance provided

### 📊 Audit Findings

| Finding # | Description | PCI DSS Requirement | Risk | Recommendation | Due Date |
|-----------|-------------|----------------------|------|----------------|----------|
| 8.01 | Password minimum length is set to 8 characters | 8.3.6 | Susceptible to brute-force attacks | Set password length to 12 characters | 2025-06-20 |
| 8.02 | Password complexity is disabled | 8.3.7 | Allows weak passwords with low entropy | Enable complexity requirements | 2025-06-20 |
| 8.03 | Password expiration set to 180 days | 8.3.8 | Longer exposure for compromised credentials | Set expiration to 90 days | 2025-06-20 |
| 8.04 | Only 1 password remembered | 8.3.9 | Allows frequent reuse of previous passwords | Increase history to remember last 4 | 2025-06-20 |
| 8.05 | Lockout threshold is 20 attempts | 8.3.11 | Enables brute-force attempts | Set threshold to 10 or fewer | 2025-06-20 |
| 8.06 | Lockout duration is only 5 minutes | 8.3.12 | Enables repeated attacks | Set to 30 minutes or until reset | 2025-06-20 |
| 8.07 | Temp passwords don't expire or enforce reset | 8.3.13 | Persistent access via temp credentials | Force reset and 24-hr expiry | 2025-06-20 |

---

## 🛠️ Remediation Plan

The System Owner is responsible for applying the above recommendations by June 20, 2025. Changes should be made via `secpol.msc` or Group Policy tools.

A follow-up validation audit will be performed after the deadline. All changes must be accompanied by timestamped screenshots and confirmation from the IT Lead.

---

## ✅ Post-Remediation Validation and Follow-Up

| PCI Req | Follow-Up Question | Screenshot |
|---------|--------------------|------------|
| 8.3.1   | Please show updated password length setting. | ![After](images/post/password-length.png) |
| 8.3.5   | Please show updated password history setting. | ![After](images/post/password-history.png) |
| 8.3.6   | Can you show complexity settings again for confirmation? | ![After](images/post/complexity.png) |
| 8.3.7   | Show password expiration setting after remediation. | ![After](images/post/expiration.png) |
| 8.3.9   | Can you show lockout threshold and duration again? | ![After](images/post/lockout.png) |
| CLI     | Show updated 'net accounts' CLI output. | ![After](images/post/net-accounts.png) |

---

## 📝 Notes

- All settings were demonstrated by the IT Lead and validated visually.
- Screenshots were captured during both pre- and post-remediation audits.
- IT Lead confirmed changes via Jira ticket #4569.






