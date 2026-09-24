# GDPR vs CCPA Technical Data Architecture Mapping

**Author:** Swastee Regmi

**Date:** 09/24/2026

**Focus Area**: Data Privacy Compliance, Database Systems Design, Data Lifecycle Management

---

## 1. Overview and Architectural Challenge

Translating high-level legal frameworks, such as the European Union's **General Data Protection Regulation (GDPR)** and the **California Consumer Privacy Act (CCPA/CPRA)**, into system architecture requires shifting from abstract compliance statements to explicit database schema design, retention rules, and security boundaries. This is a quick reference guide that aims to bridge some legal requirements under the EU and US laws with some retention and deletion suggestions.
--- 

## 2. Regulatory Technical Mapping Matrix

| Legal Right/Mandate | GDPR Provision | CCPA/CCRA Provision | Backend System Architecture Implementation |
| :--- | :--- | :--- | :--- |
| **Right to Erasure/Deletion** | Article 17 ("Right to be Forgotten") | Cal. Civ. Code § 1798.105 | Implement cascading delete logic across primary SQl/No SQL stores; issue asynchronous worker jobs to purge user logs from analytical pipelines |
| **Right to Opt-out/Object** | Article 21 ("Right to Object") | Cal. Civ. Code § 1798.120 | Maintain an indexed 'opt_out' boolean flag in user preference; filter outboud telemetry before sending it to third-party endpoints |
| **Security of Processing ** | Article 32 (Security Controls) | Cal. Civ. Code § 1798.100 (e) | AES-256 level encryption for sensitive columns (e.g., SSN, Financial Information); TLS transport security; Key management by KMS |
| **Data Minimization & Storage Limitation** | Article 5(1)(c) & (e) | Cal. Civ. Code § 1798.100(a)(3) | Automate object lifecycle expiration policies on cloud storage (e.g., AWS lifecycle rules) to purge logs after 90 days |

---

## 3. Engineering Implementation Patterns

### Pattern A: Handling "Right to Erasure" in Relational DBs & Analytics 

When a user submits a valid deletion request, directly deleting transactional history can corrupt relational integrity and accounting audits.

* **Direct Identifiers (PII):** Execute a hard deletion on tables containing explicit personal information (e.g., `names`, `addresses`, `billing details`).
* **Transactional Logs & Analytics:** Retain transactional history by converting explicit foreign key references to an unlinkable hash string, as given below

  ```sql
  --Pseudocode SQL pattern for anonymization
  UPDATE transcations_and_orders
  SET user_id = SHA256(CONCAT(user_id, 'SYSTEM SALT')),
              shipping_address = 'DELETED PER GDPR REQUEST',
              customer_name = 'ANONYMOUS'
  WHERE user_id = 'target_user_id';
