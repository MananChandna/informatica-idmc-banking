# Axon Business Glossary – Banking PoC

## Domain
**Customer & Accounts**

---

## Business Term: Customer Account

**Definition:**  
A Customer Account represents a unique relationship between a customer and the organization, used to manage products, services, and financial interactions.

**Data Owner:**  
Head of Sales / Customer Operations

**Data Steward:**  
Enterprise Data Steward

**Related Technical Assets:**  
- Source Object: Account (Salesforce-style)
- Target Object: Account (Curated)

---

## Business Term: Account Number

**Definition:**  
A system-generated identifier used to uniquely identify a customer account.

**Classification:**  
PII / Sensitive Data

**Usage Purpose:**  
- Customer Identification  
- Internal Reporting  

**Restrictions:**  
- Must not be exposed in full to downstream analytical users  
- Masking required for non-privileged access

**Related Technical Field:**  
- ACCOUNTNUMBER (Source)
- o_account_masked (Target)

---

## Business Term: Customer Name

**Definition:**  
The legal or registered name of the customer associated with the account.

**Classification:**  
Confidential

**Related Technical Field:**  
- NAME (Source)
- o_name (Target)

---

## Business Term: Contact Phone Number

**Definition:**  
Primary contact phone number associated with the customer account.

**Classification:**  
PII

**Handling Rule:**  
Standardized format, no masking required for internal operations.

---

## Glossary Governance Notes

- Business terms are authored and maintained in Axon
- Technical metadata is linked from Enterprise Data Catalog (EDC)
- Stewardship ensures definitions and classifications remain consistent
