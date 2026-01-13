# PII Classification – Banking PoC

## Classification Levels

### Public
- Non-sensitive business metadata

### Confidential
- Customer Name
- Account Type

### PII (Personally Identifiable Information)
- Phone Number
- Email Address

### Sensitive PII
- Account Number
- Government Identifiers (if applicable)

---

## Field-Level Classification Mapping

| Field Name          | Classification |
|--------------------|----------------|
| NAME               | Confidential   |
| PHONE              | PII            |
| ACCOUNTNUMBER      | Sensitive PII  |
| o_account_masked   | Protected View |

---

## Enforcement Mechanism

- Sensitive PII is masked during ingestion
- Only masked versions propagate to downstream systems
- Full values remain restricted at source

---

## Audit & Compliance

- Classification maintained in Axon
- Technical enforcement verified via IDMC mappings
- Lineage ensures traceability for audits
