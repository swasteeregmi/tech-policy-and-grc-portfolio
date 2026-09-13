# Third Party Risk Evaluation Template

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
