
</head>

<body>

<h1>Informatica IDMC – End-to-End Data Integration & Governance PoC</h1>

<div class="section">
  <h2>Overview</h2>
  <p>
    This repository contains an end-to-end Proof of Concept (PoC) implemented using
    <strong>Informatica Intelligent Data Management Cloud (IDMC)</strong>.
  </p>
  <p>
    The objective of this PoC is to demonstrate how cloud-native data integration,
    metadata-driven transformations, and governance-ready pipelines are designed
    and executed in an enterprise environment.
  </p>

<div class="section">
  <h2>Tools & Services Used</h2>
  <ul>
    <li>Informatica Intelligent Data Management Cloud (IDMC)</li>
    <li>Cloud Data Integration (CDI)</li>
    <li>Informatica Cloud Hosted Secure Agent</li>
    <li>MockConnector (Salesforce-style source & target)</li>
    <li>Enterprise Data Catalog (conceptual integration)</li>
    <li>Axon Data Governance (conceptual integration)</li>
  </ul>
</div>

<div class="section">
  <h2>Source System</h2>
  <p>
    The source system represents a Salesforce-style <strong>Account</strong> object
    accessed via Informatica MockConnector.
  </p>
  <ul>
    <li>Customer identifiers</li>
    <li>Account names</li>
    <li>Phone numbers</li>
    <li>Account numbers (sensitive)</li>
  </ul>
</div>

<div class="section">
  <h2>Transformation Logic</h2>
  <p>
    An Expression transformation is used to apply business and data governance rules:
  </p>
  <ul>
    <li>Standardization of string attributes</li>
    <li>Null handling</li>
    <li>Masking of sensitive fields</li>
  </ul>

  <h3>Sample Masking Logic</h3>
  <pre>
'XXXXXX' || SUBSTR(ACCOUNTNUMBER, LENGTH(ACCOUNTNUMBER)-3, 4)
  </pre>
</div>

<div class="section">
  <h2>Target System</h2>
  <p>
    The transformed data is written back to a target Account object using MockConnector.
  </p>
  <ul>
    <li>Operation Type: Insert</li>
    <li>Manual field mapping</li>
  </ul>
</div>

<div class="section">
  <h2>Execution & Monitoring</h2>
  <p>
    The mapping was executed using the Informatica Cloud Hosted Agent.
  </p>
  <ul>
    <li>Mapping Task: <strong>mt_account_standardization</strong></li>
    <li>Rows Processed: 200</li>
    <li>Status: Success</li>
    <li>Execution Duration: ~8 seconds</li>
  </ul>
</div>

<div class="section">
  <h2>Enterprise Data Catalog (EDC) Integration</h2>
  <p>
    In an enterprise setup, IDMC mappings publish technical metadata to
    Enterprise Data Catalog.
  </p>
  <ul>
    <li>Source-to-target lineage</li>
    <li>Column-level impact analysis</li>
    <li>Transformation logic visibility</li>
  </ul>
</div>

<div class="section">
  <h2>Axon Data Governance Integration</h2>
  <p>
    Axon provides the business governance layer on top of cataloged metadata.
  </p>
  <ul>
    <li>Business glossary terms (Customer Account, Account Number)</li>
    <li>Data ownership and stewardship</li>
    <li>PII classification and policies</li>
    <li>Purpose-based data access</li>
  </ul>
</div>

<div class="section">
  <h2>Key Learnings</h2>
  <ul>
    <li>IDMC supports metadata-driven and governance-ready pipelines</li>
    <li>Transformation logic can directly enforce data protection rules</li>
    <li>The same architecture scales from PoC to enterprise production</li>
  </ul>
</div>

<div class="section">
  <h2>Disclaimer</h2>
  <p>
    This PoC was implemented using trial features and MockConnector.
    The same design principles apply to real enterprise data sources.
  </p>
</div>

</body>
</html>
