🔍 Password Policy Validation – Interview & Evidence Log

This document simulates a real-world PCI DSS v4.0 password policy audit, structured from the perspective of an Internal Security Assessor (ISA). The ISA does not apply system changes but instead requests that the IT Lead (Stone Cold Steve Austin) demonstrate compliance settings, which are then captured as evidence.

---

## 🧑‍💼 Interview Questions and Evidence Collection

As the ISA, I requested evidence for each PCI DSS v4.0 Requirement 8 password control. Screenshots were taken during the session to verify what the IT Lead showed.

### ✅ Pre-Remediation Questions and Screenshots

| PCI Req | Assessor Question | Screenshot |
|---------|-------------------|------------|
| 8.2.6   | Can you show me your password configuration standard? | *(Refer to SharePoint entry – not available)* |
| 8.3.1   | Can you pull up the minimum password length setting? | ![](screenshots_pre/before_min_password_length.png) |
| 8.3.5   | Can you show me how many previous passwords are remembered? | ![](screenshots_pre/before_password_history_1.png) |
| 8.3.6   | Where can I verify that password complexity is enabled? | ![](screenshots_pre/before_complexity_disabled.png) |
| 8.3.7   | Please show me the password expiration setting (in days). | ![](screenshots_pre/before_password_age_180_days.png) |
| 8.3.9   | Can you show me your account lockout threshold? | ![](screenshots_pre/before_lockout_threshold_20_attempts.png) |
| 8.3.9   | Can you show me lockout duration and reset time settings? | ![](screenshots_pre/before_lockout_duration_5min.png) |
| -       | Show me 'net accounts' CLI output for global policy confirmation. | ![](screenshots_pre/before_net_accounts_output.png) |
| -       | Can you show me PasswordLastSet date from CLI? | ![](screenshots_pre/before_passwordlastset_output.png) |

## 📝 Internal PCI DSS Password Policy Audit Report

**Confidential – For Internal Use Only**

- **Organization:** Google.com  
- **System Owner:** Stone Cold Steve Austin – IT Lead  
- **Audit Performed By:** Alex Bolden – Internal PCI Auditor (ISA)  
- **Audit Date:** June 2025  
- **Target System:** Windows 10 Standalone VM  
- **Click here:** *For Evidence File*

---

### 📋 Executive Summary

This audit report presents the results of an internal assessment of the password authentication policies configured on a Windows 10 virtual machine used for PCI-related administrative functions.

The goal was to validate compliance with **PCI DSS v4.0.1 – Requirement 8**. The assessment revealed multiple deficiencies in system configuration — most notably in password length, complexity, expiration, lockout thresholds, and temporary password handling.

This report outlines each finding, its associated risk, the relevant PCI DSS requirement, and a recommended remediation path. All issues must be addressed before the system can be considered compliant.

---

### 🖥️ System Design Description

The target system is a **Windows 10 standalone VM** simulating access to cardholder data. It is configured using local security policy (`secpol.msc`) and does not rely on domain-joined Group Policies. Local user accounts are used to validate enforcement of password and account lockout policies.

System changes are applied manually and validated using PowerShell and command-line tools.

---

### 👁️‍🗨️ Observations

During the audit, it was noted that several password-related controls were misconfigured. Key observations include:

- Password length set below PCI minimum  
- Complexity settings disabled  
- Expiration and reuse policies misaligned with standards  
- Lockout thresholds too lenient  
- No enforcement for temp password reset  
- No documented configuration standard or user password guidance provided

---

### 📊 Audit Findings

| Finding # | Description | PCI DSS Requirement | Risk | Recommendation | Due Date |
|-----------|-------------|---------------------|------|----------------|----------|
| 8.01 | Password minimum length is set to 8 characters | 8.3.6 | Susceptible to brute-force attacks | Set password length to 12 characters | 2025-06-20 |
| 8.02 | Password complexity is disabled | 8.3.7 | Allows weak passwords with low entropy | Enable complexity: uppercase, lowercase, number, special character | 2025-06-20 |
| 8.03 | Password expiration set to 180 days | 8.3.8 | Extended expiration increases exposure | Reduce to 90-day expiration | 2025-06-20 |
| 8.04 | Only 1 password remembered | 8.3.9 | Allows users to cycle reused passwords | Remember last 4 passwords | 2025-06-20 |
| 8.05 | Lockout threshold is set to 20 attempts | 8.3.11 | Higher risk of brute-force | Lower to 10 or fewer attempts | 2025-06-20 |
| 8.06 | Lockout duration only 5 minutes | 8.3.12 | Enables repeated attack attempts | Set to 30 minutes or manual reset | 2025-06-20 |
| 8.07 | Temporary passwords don’t expire or force change | 8.3.13 | Long-lived temp credentials pose risk | Enforce 24-hour expiry and reset at login | 2025-06-20 |

---

### 🛠️ Remediation Plan

The **System Owner** is responsible for applying the above recommendations by **June 20, 2025**.  
Changes should be made via `secpol.msc` or Group Policy tools.

A follow-up validation audit will be performed after the deadline. All changes must be accompanied by timestamped screenshots and confirmation from the IT Lead.

---

### ✅ Conclusion

This internal audit has identified multiple deviations from PCI DSS Requirement 8.  
A formal remediation effort is required to address the gaps before the system can be considered compliant.

Once updates are made, a **compliance walkthrough and screenshot validation** will confirm each finding has been closed.

---



### 🛠️ Post-Remediation Validation and Follow-Up

| PCI Req | Follow-Up Question | Screenshot |
|---------|--------------------|------------|
| 8.2.6   | Was the configuration standard updated after changes? | *(Pending update to SharePoint)* |
| 8.3.1   | Please show me updated password length setting. | ![](screenshots_post/after_min_password_length_12.png) |
| 8.3.5   | Please show me updated password history setting. | ![](screenshots_post/after_password_history_4.png) |
| 8.3.6   | Can you show complexity settings again for confirmation? | ![](screenshots_post/after_complexity_enabled.png) |
| 8.3.7   | Show password expiration setting after remediation. | ![](screenshots_post/after_password_age_90_days.png) |
| 8.3.9   | Can you show lockout threshold and duration again? | ![](screenshots_post/after_lockout_threshold_10.png)<br>![](screenshots_post/after_lockout_duration_30min.png) |
| -       | Show me updated 'net accounts' CLI output. | ![](screenshots_post/after_net_accounts_output.png) |

---

## 📝 Notes

- All settings were demonstrated by the IT Lead and validated visually.
- Screenshots were captured as part of the audit session.
- IT Lead confirmed remediation changes were submitted via Jira ticket #4569.






