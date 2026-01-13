# Data Governance Policies – Banking PoC

---

## Policy: PII Data Protection

**Policy Type:**  
Data Privacy & Protection

**Description:**  
All personally identifiable information (PII) must be protected against unauthorized access.

**Scope:**  
Customer Account Data

**Enforcement Rules:**
- Mask sensitive attributes in integration layer
- Restrict full-value access to privileged roles only

**Enforced In:**  
- Informatica IDMC (Expression Transformation)
- Axon (Policy Definition)
- EDC (Policy-to-Asset Mapping)

---

## Policy: Data Quality Standardization

**Policy Type:**  
Data Quality

**Description:**  
Customer master data must conform to enterprise-wide formatting and completeness standards.

**Rules:**
- Trim leading/trailing spaces
- Enforce non-null constraints where applicable
- Standardize string fields

**Enforced In:**  
- Informatica IDMC Expression Transformation

---

## Policy: Data Lineage & Traceability

**Policy Type:**  
Data Transparency

**Description:**  
All critical data elements must have documented source-to-target lineage.

**Implementation:**
- Lineage captured automatically by IDMC
- Harvested into Enterprise Data Catalog
- Consumed by Axon for governance oversight
