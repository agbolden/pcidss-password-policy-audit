# 🔐 PCI DSS Password Policy Audit Lab (Windows 10 VM)

This lab simulates a real-world internal audit of **PCI DSS v4.0.1 Requirement 8** – focused on password policy enforcement and remediation on a standalone Windows 10 virtual machine.

As the Internal Security Assessor (ISA), I conducted interviews, gathered screenshot evidence, documented findings, and validated remediations per PCI controls.

---

## 👤 Role Details

| Role            | Name                                |
|-----------------|-------------------------------------|
| Auditor         | Alex Bolden – Internal Security Assessor (ISA) |
| System Owner    | Stone Cold Steve Austin – IT Lead   |
| Target System   | Windows 10 Standalone VM (non-domain) |
| Audit Date      | June 8, 2025                           |

---

## 🔍 Assessor Walkthrough – Mock Interview Table (Pre-Remediation)

| PCI Req | Interview Question | Screenshot |
|---------|--------------------|------------|
| 8.3.6 | *Can you show me the current minimum password length setting in secpol.msc?* | ![before_min_password_length.png](screenshots_pre/before_min_password_length.png) |
| 8.3.6 | *Can you show me where password complexity is enabled on this machine?* | ![before_complexity_disabled.png](screenshots_pre/before_complexity_disabled.png) |
| 8.3.9 | *Can you show me when passwords are set to expire?* | ![before_password_age_180_days.png](screenshots_pre/before_password_age_180_days.png) |
| 8.3.7 | *Can you show me the system setting that prevents users from reusing previous passwords?* | ![before_password_history_1.png](screenshots_pre/before_password_history_1.png) |
| 8.3.4 | *How many failed login attempts trigger account lockout?* | ![before_lockout_threshold_20_attempts.png](screenshots_pre/before_lockout_threshold_20_attempts.png) |
| 8.3.4 | *How long does the lockout last after threshold is reached?* | ![before_lockout_duration_5min.png](screenshots_pre/before_lockout_duration_5min.png) |
| 8.6.3 | *Can you show the CLI output of password policy enforcement?* | ![before_net_accounts_output.png](screenshots_pre/before_net_accounts_output.png) |

---

## 📋 Internal PCI DSS Password Policy Audit Report

### Executive Summary

This audit reviewed password policy controls on a Windows 10 virtual machine used for PCI-sensitive administrative functions. Several misconfigurations were discovered that deviate from PCI DSS v4.0.1 Requirement 8. Each issue is documented below with supporting evidence and mapped to the relevant requirement.

---

### Audit Findings Table (Pre-Remediation Evidence)

| Finding # | Description | PCI Req | Risk | Recommendation | Screenshot |
|-----------|-------------|---------|------|----------------|------------|
| 8.01 | Password minimum length is set to 8 characters | 8.3.6 | Susceptible to brute-force attacks | Set to minimum 12 characters | ![before_min_password_length.png](screenshots_pre/before_min_password_length.png) |
| 8.02 | Password complexity is disabled | 8.3.6 | Weak, guessable passwords allowed | Enable complexity: upper/lower/number/symbol | ![before_complexity_disabled.png](screenshots_pre/before_complexity_disabled.png) |
| 8.03 | Passwords expire after 180 days | 8.3.9 | Long exposure window if stolen | Reduce to 90-day expiration | ![before_password_age_180_days.png](screenshots_pre/before_password_age_180_days.png) |
| 8.04 | Only 1 password remembered | 8.3.7 | Allows reuse and cycling | Store at least last 4 passwords | ![before_password_history_1.png](screenshots_pre/before_password_history_1.png) |
| 8.05 | Lockout threshold is 20 attempts | 8.3.4 | Higher risk of brute-force login | Reduce to max 10 attempts | ![before_lockout_threshold_20_attempts.png](screenshots_pre/before_lockout_threshold_20_attempts.png) |
| 8.06 | Lockout duration is 5 minutes | 8.3.4 | Too short – attacker can retry quickly | Set to 30 minutes or manual reset | ![before_lockout_duration_5min.png](screenshots_pre/before_lockout_duration_5min.png) |
| 8.07 | CLI output shows weak overall configuration | 8.6.3 | No strong complexity or enforcement baseline | Remediate via security policy & enforcement tools | ![before_net_accounts_output.png](screenshots_pre/before_net_accounts_output.png) |

---

### Remediation Plan

All remediations were assigned to the IT Lead, Stone Cold Steve Austin.  
Configuration changes were made using `secpol.msc` and validated with screenshots.

---

## ✅ Post-Remediation Screenshot Evidence

| Setting | Screenshot |
|---------|------------|
| Min Password Length (12) | ![after_min_password_length_12.png](screenshots_post/after_min_password_length_12.png) |
| Password Complexity Enabled | ![after_complexity_enabled.png](screenshots_post/after_complexity_enabled.png) |
| Password Expiration 90 Days | ![after_password_age_90_days.png](screenshots_post/after_password_age_90_days.png) |
| Password History = 4 | ![after_password_history_4.png](screenshots_post/after_password_history_4.png) |
| Lockout Threshold = 10 | ![after_lockout_threshold_10.png](screenshots_post/after_lockout_threshold_10.png) |
| Lockout Duration = 30 mins | ![after_lockout_duration_30min.png](screenshots_post/after_lockout_duration_30min.png) |
| Net Accounts Config | ![after_net_accounts_output.png](screenshots_post/after_net_accounts_output.png) |

---

## ✅ Final Compliance Summary

The system is now aligned with **PCI DSS v4.0.1 – Requirement 8** password policies.  
All issues identified in the initial audit have been fully remediated and evidenced.  
This repo now serves as a full audit + remediation walkthrough for future internal assessments or hiring manager review.

---
