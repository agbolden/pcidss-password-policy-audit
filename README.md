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






