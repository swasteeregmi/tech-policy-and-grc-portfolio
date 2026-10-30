# Enterprise Generative AI Acceptable Use Policy and Risk Assessment Framework

---

**Document Control:** Version 1.0 | **Author:** Swastee Regmi | **Date:** 10/30/2026

**Evaluation Scope:** Corporate-wide adoption of Commercial LLMs and AI Development Tools

**Target Standards:** NIST AI Risk Management Framework (AI RMF 1.0), ISO/IEC 42001:2023 (Artificial Intelligence Management System), OWASP Top 10 for LLMs

---

## 1. Executive Summary and Purpose

This framework sets governance boundaries for deploying and using Generative AI applications within an enterprise. It balances innovation with strict corporate protection mechanisms such as intellectual property leakage, shadow AI adoption, and data privacy violations. All prospective GenAI deployments must be scored against this framework before production release or onboarding for corporate access. 

---

## 2. Risk Profiling Model

AI tools are categorized into three tiers based on data exposure pathways and training modalities:

| **Risk Tier** | **Profile Characteristics** | **Operational Mandate**
| :--- | :--- | :--- |
| **Tier 1: High Risk** | Public/Consumer-grade AI models (e.g., free ChatGPT, Claude consumer tiers) where user prompts are harvested to retrain public models | Prohibited for any business context containing non-public organizational data |
| **Tier 2: Managed Risk** | Commercial enterprise AI deployments (e.g., ChatGPT Enterprise, Microsoft 365 Copilot) featuring opt-out data training clauses and data isolation boundaries | Permitted pending security validation and strict prompt data classification guardrails |
| **Tier 3: Low Risk** | Locally hosted, open-weight models (e.g., Llama 3 running on isolated corporate virtual private clouds) with zero external telemetry | Approved under standard internal security, software lifecycle, and infrastructure controls |

---

## 3. Generative AI Control Assessment Matrix

| **Risk Dimension** | **Control ID** | **Evaluation & Compliance Criteria** | **Target Metric / Guardrail** | **Implemented Mitigation Strategy** |
| :--- | :--- | :--- | :--- | :--- |
| **Data Privacy & Training Data** | AI.DP-01 | Verify vendor Data Processing Agreements (DPA) explicitly state that customer prompts and uploaded files are never used for base model retraining | Mandatory Pass | Implement a Zero Data Retention (ZDR) API proxy architecture between the corporate network and the AI provider | 
| **Intellectual Property Protection** | AI.IP-01 | Audit model code-generation outputs to ensure that tools do not surface copyrighted snippets without proper licensing | Source Tracking Enabled | Enforce the deployment of automated code scanning tools (e.g., SonarQube, GitHub Advanced Security) to flag licensed open-source snippets in AI-generated code blocks |
| **Input Sanitization (Data Leakage)** | AI.LLM-01 | Block corporate network transmission of highly sensitive data classes (PII, PHI, trade secrets) into public model API endpoints | Real-time DLP Blocking | Deploy inline Data Loss Prevention (DLP) filters at the network gateway to intercept and redact social security numbers, API tokens, and private cryptographic keys from AI prompts | 
| **Output Validation & Prompt Injection** | AI.LLM-02 | Defend against indirect prompt injection and systemic model hallucinations through programmatic validation before displaying outputs to end users | Structured Output Verification | Implement input-output sanitization loops and utilize retrieval-augmented generation (RAG) strictly anchored to verified internal vector knowledge bases |
| **Model Transparency & Lineage** | AI.GOV-01 | Document the specific model versions, system prompt definitions, and parameter choices (e.g., temperature) to guarantee auditability and reproducible results | Model Inventory Logged | Maintain a centralized corporate AI Model Registry tracking all enterprise API integrations, model lifecycles, and operational dependencies |

---

## 4. Employee Acceptable Use Directive

* **Human-in-the-Loop Requirement:** Employees are strictly prohibited from utilizing AI-generated text, source code, or analytical summaries in customer-facing products or critical business decisions without manual human review and sign-off.
* **Prohibited Activities:** Under no circumstances shall proprietary business logic, unreleased financial reports, or employee personal data be inputted into any consumer-facing AI tool lacking enterprise-grade privacy protection agreements. 

---
**Definitions:**

* **ISO:** International Organization for Standardization
* **IEC:** International Electrotechnical Commission
* **NIST:** National Institute of Standards and Technology
* **OWASP:** Open Web Application Security Project
* **Open-Weight Model:** An Open-Weight Model is an AI model whose core components are publicly released, allowing anyone to download it.
* **Zero Data Retention (ZDR) API proxy architecture:** A security design where an intermediary server (the proxy) processes, transforms, or routes API requests and responses without saving any sensitive data to persistent storage (like databases, logs, or hard drives).
* **Data Loss Prevention (DLP):** Data Loss Prevention (DLP) blocking is an automated security mechanism that stops sensitive or restricted information from leaving an organization's controlled environment or being shared improperly.



