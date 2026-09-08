# Policy Brief: Technical Feasibility and Regulatory Gaps in AI Policies

**Author**: Swastee Regmi

**Date**: 09/08/2026

**Target Audience**: Chief Information Security Officers (CISOs), Enterprise Risk Committees, Engineering Leadership

**Relevant Frameworks**: NIST AI Risk Management Framework (AI RMF 1.0), ISO/IEC 42001, SOC 2 Type II

---

## 1. Executive Summary

The rapid integration of Generative Artificial Intelligence and AI-powered coding assistants (GitHub Copilot, Cursor, VS Code extensions, etc.) has significantly accelerated software development velocity. However, ungoverned adoption introduces critical vulnerabilities across three major areas: proprietary source code exposure, third-party supply chain risks, and intellectual/copyright liabilities. This policy brief analyzes the threat vectors, mitigation methods, and actionable governmental controls under emerging AI frameworks.

---

## 2. Technical Threat Vector Analysis

### A. Automated injection of insecure code patterns

**Mechanism**: Large Language Models (LLMs) trained on public code repositories inevitably replicate insecure coding patterns, deprecated functions, and vulnerable dependencies. 

**Associated Risks**: Developers accepting auto-suggested code are subjecting themselves and their work to OWASP Top 10 vulnerabilities like hardcoded API keys, unvalidated input handling (SQL injection), and weak cryptographic primitives directly into primary code branches.

### B. Intellectual Property & License Contamination

**Mechanism**: LLMs may output verbatim code snippets from public code protected by restrictive open-source licenses like GPL-3.0 and AGPL.

**Associated Risks**: Merging such copyleft-licensed code into commercial, closed-source software products creates legal exposure to copyleft contamination, potential copyright infringement claims, and license compliance issues.

### C. Data Transmission & Retraining Leaks

**Mechanism**: AI assistants are able to serialize local codebase context, including API endpoints, variable names, internal database schemas, and surrounding code blocks. They then transmit this data to third-party vendor cloud endpoints through REST APIs.

**Associated Risks**: Standard consumer or API tiers usually reserve the right to log prompt payloads to retrain AI models. This risks exposing business logic, proprietary algorithms, and internal system architectures to third-party vendors. 

---

## 3. Threat & Mitigation Matrix

| Domain | Technical Vulnerability | Legal / Compliance Impact | Mandated Policy Control |
| :--- | :--- | :--- | :--- |
|**Data Privacy**| Transmission of consumer PII in prompt context | CCPA/HIPAA non-compliance | Enforce zero data retention (ZDR) agreements |
---

## 4. Policy Recommendations & Control Implementation

