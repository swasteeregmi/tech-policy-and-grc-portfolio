# Third-Party Risk Evaluation Template

**Document control:** Version 1.0 | **Author:** Swastee Regmi
**Evaluation scope:** Cloud SaaS & Infrastructure vendors
**Target Standards:** NIST CSF 2.0, SOC 2 Trust Services Criteria

---

## 1. Executive Summary & Objective

This document provides a standardized vendor security assessment framework designed to evaluate third-party cloud applications prior to enterprise system integration. It establishes a repeatable and understandable scoring method for evaluating data protection, access control mechanisms, incident response capabilities, and alignment with NIST CSF controls.

---

## 2. Risk Scoring & Quantification Model

Risk Exposure can be evaluated using a 4x4 matrix balancing Probability and Business Impact:

$$ \text{Risk Score} = \text{Likelihood(1--4)} \times \text{Impact(1--4)} $$

| Score Range | Severity Level | Action Required |
| :--- | :--- | :--- |
| **12-16** | **Critical** | Any onboarding is blocked; requires Chief Information Security Officer (CISO) waiver and regulatory plans. |
| **8-11** | **High** | Conditional onboarding; vendor remediation must be done within 30 days. |
| **4-7** | **Medium** | Acceptable risk; standard annual security review. |
| **1-3** | **Low** | Approved; minimal risk exposure. |

---

## 3. Control Assessment & Governance Matrix
---
| Domain | Control ID | Evaluation Criteria | Vendor Compliance Status | Risk Score | Mitigation |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Identity & Access Management** | PR.AA-01 | Enforce SAML 2.0/ OpenID Connect SSO integration and mandatory MFA for all administrative roles | **Pass** | Low (2) | Require hardware-backed FIDO2 MFA keys for tenant admin accounts |
| **Data protection at rest** | PR.DS-01 | AES-256 encryption across all storage tiers and database instances; support for customer-managed keys (KMS) | **Pass** | Low (1) | Ensure key rotation schedules are configured annually via AWS KMS |
| **Data Protection in Transit** | PR.DS-02 | Mandatory TLS 1.3 encryption across all public APIs and client connections | **Partial** | Medium (6) | Contractually require vendor to deprecate legacy TLS endpoints on internal worker nodes within 60 days |
| **Incident Response** | IR.RA-01 | Contractually binding breach notification window within 72 hours of initial discovery | **Fail** | High (9) | Amend Master Services Agreement (MSA) to replace vague "reasonable time" language with explicit 72-hour notification rule | 
| **Business Continuity & Disaster Relief** | PR.IR-01 | Verified Recovery Time Objective (RTO) $< 4$ hours and Recovery Point Objective (RPO) $< 1$ hour | **Pass** | Low (2) | Request annual SOC 2 Type II report to verify third-party disaster recovery testing execution |


---

## 4. Final Recommendation 
**Overall Assessment Rating:** Conditional Approval
**Mandated Action Items:** Onboarding approved pending execution of the updated Data Processing Addendum (DPA) incorporating the mandatory 72-hour breach notification requirement and TLS remediation timeline. 

**Keywords:**
- Amazon Web Services Key Management Service (AWS KMS)
- Data Processing Addendum (DPA) is a legally binding contract that defines how a third-party vendor handles, uses, and protects personal data on a company's behalf.

---

**All control IDs are subframeworks of NIST CSF**
