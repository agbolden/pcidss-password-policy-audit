# PCI DSS Password Policy Audit (v4.0) – Internal Lab

Simulated internal audit of local Windows password policies based on **PCI DSS v4.0 Requirement 8**.  
This lab mimics a real-world compliance review scenario where separation of duties is enforced.

---

## 🎯 Objective

- Identify and document weak password settings.
- Validate gaps against PCI DSS v4.0 controls.
- Remediate findings and collect post-fix evidence.
- Demonstrate process-driven audit readiness.

---

## 🧑‍💼 Roles

- **Auditor:** Internal Security Auditor (You)
- **IT Lead (Remediator):** *Stone Cold Steve Austin*  
  _“Fixes applied by authorized personnel. Auditor did not perform changes due to SoD (Separation of Duties).”_

---

## 📂 Folder Structure

---

## 🔍 Lab Steps (Audit Flow)

1. Logged into Windows 10 VM as auditor
2. Collected password policy via:
   - GUI: `secpol.msc`
   - CLI: `net accounts`, `Get-LocalUser | Select Name, PasswordLastSet`
3. Captured screenshots of current settings
4. Interviewed IT Lead for clarification (see below)
5. Compared results to PCI DSS v4.0 Req 8
6. IT Lead remediated settings
7. Captured post-remediation screenshots
8. Finalized report and evidence file

---

## 🎙️ Mock Interview with IT Lead

> **Date:** [Insert Date]  
> **Auditor:** You  
> **Interviewee:** Stone Cold Steve Austin

| PCI Req | Interview Question                                                           | Auditor Validation               |
|---------|-------------------------------------------------------------------------------|----------------------------------|
| 8.3.1   | Are passwords at least 12 characters?                                         | Screenshot confirmed ✅          |
| 8.3.5   | Is password history enforced?                                                 | Screenshot confirmed ✅          |
| 8.3.6   | Is complexity enforced (upper/lower/num/symbol)?                              | Screenshot confirmed ✅          |
| 8.3.7   | What is the max password age configured?                                      | Screenshot confirmed ✅          |
| 8.3.9   | What happens after multiple failed login attempts?                            | Screenshot confirmed ✅          |
| Other   | Where are these settings documented?                                          | "Stored in SharePoint IT Docs"  |

---

## 📄 Files Included

| File Name                                      | Description                                      |
|------------------------------------------------|--------------------------------------------------|
| `Internal_PCI_Password_Audit_Report.docx`      | Main findings report with executive summary      |
| `Password_Policy_Audit_Evidence_File.docx`     | Before screenshots with captions                 |
| `Password_Policy_Audit_Evidence_File_Updated.docx` | Post-remediation proof and verification      |
| `screenshots_pre/`                             | All pre-remediation evidence                     |
| `screenshots_post/`                            | All post-remediation evidence                    |

---

## 🧩 Notes

- Lab built to simulate a **real internal audit workflow**
- No perfect configuration at start — issues were intentionally staged
- Screenshots labeled clearly for GitHub review and report traceability

---

## 🏁 Outcome

✔ PCI DSS v4.0 Requirement 8 compliance was verified  
✔ Separation of duties observed  
✔ Ready for GitHub upload or stakeholder submission



