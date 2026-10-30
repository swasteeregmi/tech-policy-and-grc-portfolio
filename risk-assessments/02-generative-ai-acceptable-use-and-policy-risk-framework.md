# Enterprise Generative AI Acceptable Use Policy and Risk Assessment Framework

---

**Document Control:** Version 1.0 | **Author:** Swastee Regmi | **Date:** 10/30/2026

**Evaluation Scope:** Corporate-wide adoption of Commercial LLMs and AI Development Tools

**Target Standards:** NIST AI Risk Management Framework (AI RMF 1.0), ISO/IEC 42001:2023 (Artificial Intelligence Management System), OWASP Top 10 for LLMs

---

## 1. Executive Summary and Purpose

This framework establishes governance boundaries for the deployment and usage of Generative AI applications within an enterprise. It balances innovation with strict corporate protection mechanisms such as intellectual property leakage, shadow AI adoption, and data privacy violations. All prospective GenAI deployments must be scored against this framework prior to production release or corporate access onboarding. 

---

## 2. Risk Profiling Model

AI tools are categorized into three tiers based on data exposure pathways and training modalities:

| **Risk Tier** | **Profile Characteristics** | **Operational Mandate**
| :--- | :--- | :--- |
| **Tier 1: High Risk** | Public/Consumer-grade AI models (e.g., free ChatGPT, Claude consumer tiers) where user prompts are harvested to retrain public models | Prohibited for any business context containing non-public organizational data |
| **Tier 2: Managed Risk** | Commercial enterprise AI deployments (e.g., ChatGPT Enterprise, Microsoft 365 Copilot) featuring opt-out data training clauses and data isolation boundaries | Permitted pending security validation and strict prompt data classification guardrails |
| **Tier 3: Low Risk** | Locally hosted, open-weight models (e.g., Llama 3 running on isolated corporate virtual private clouds) with zero external telemetry | Approved under standard internal security, software lifecycle, and infrastructure controls |

---



---
**Definitions:**

* **ISO:** International Organization for Standardization
* **IEC:** International Electrotechnical Commission
* **NIST:** National Institute of Standards and Technology
* **OWASP:** Open Web Application Security Project
* **Open-Weight Model:** An Open-Weight Model is an AI model whose core components are publicly released, allowing anyone to download it. 







