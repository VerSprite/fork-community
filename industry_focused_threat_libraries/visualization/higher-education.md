# Higher Education Threat Library

```mermaid
---
config:
  layout: elk
  flowchart:
    curve: step
---
flowchart LR
  T0("Compromise Faculty and Student Accounts to<br/>Commit Academic Fraud"):::threat
  T0M0["Gain authenticated access to faculty<br/>accounts to manipulate grades, steal course<br/>materials, and access student personal data"]:::motive
  T0 --> T0M0
  T0M0C0("Faculty Identity and Learning Platform<br/>Access"):::component
  T0M0 --> T0M0C0
  T0M0C0W0("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T0M0C0 --> T0M0C0W0
  T0M0C0W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T0M0C0 --> T0M0C0W1
  T0M0C0W2("CWE-798: Use of Hard-coded Credentials"):::cwe
  T0M0C0 --> T0M0C0W2
  T0M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T0M0C0 --> T0M0C0W3
  T0M0C0W4("CWE-285: Improper Authorization"):::cwe
  T0M0C0 --> T0M0C0W4
  T0M0C1("Faculty Productivity and Remote Access<br/>Infrastructure"):::component
  T0M0 --> T0M0C1
  T0M0C1W0("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T0M0C1 --> T0M0C1W0
  T0M0C1W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T0M0C1 --> T0M0C1W1
  T0M0C1W2("CWE-798: Use of Hard-coded Credentials"):::cwe
  T0M0C1 --> T0M0C1W2
  T0M1["Compromise student accounts to manipulate<br/>academic records, access financial aid<br/>systems, and commit identity fraud"]:::motive
  T0 --> T0M1
  T0M1C0("Student Account Management Systems"):::component
  T0M1 --> T0M1C0
  T0M1C0W0("CWE-521: Weak Password Requirements"):::cwe
  T0M1C0 --> T0M1C0W0
  T0M1C0W1("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T0M1C0 --> T0M1C0W1
  T0M1C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T0M1C0 --> T0M1C0W2
  T0M1C0W3("CWE-285: Improper Authorization"):::cwe
  T0M1C0 --> T0M1C0W3
  T1("Exfiltrate Student and Faculty Records from<br/>University Systems"):::threat
  T1M0["Extract bulk student and faculty personal<br/>records for identity theft, financial fraud,<br/>and dark web resale"]:::motive
  T1 --> T1M0
  T1M0C0("Student Information System Platform Access"):::component
  T1M0 --> T1M0C0
  T1M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T1M0C0 --> T1M0C0W0
  T1M0C0W1("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T1M0C0 --> T1M0C0W1
  T1M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T1M0C0 --> T1M0C0W2
  T1M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T1M0C0 --> T1M0C0W3
  T1M0C0W4("CWE-285: Improper Authorization"):::cwe
  T1M0C0 --> T1M0C0W4
  T1M0C1("Student and Faculty Data Repositories"):::component
  T1M0 --> T1M0C1
  T1M0C1W0("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T1M0C1 --> T1M0C1W0
  T1M0C1W1("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T1M0C1 --> T1M0C1W1
  T1M0C1W2("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T1M0C1 --> T1M0C1W2
  T1M0C1W3("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T1M0C1 --> T1M0C1W3
  T1M0C1W4("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T1M0C1 --> T1M0C1W4
  T1M0C1W5("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T1M0C1 --> T1M0C1W5
  T1M0C1W6("CWE-434: Unrestricted Upload of File<br/>with Dangerous Type"):::cwe
  T1M0C1 --> T1M0C1W6
  T2("Falsify Student Academic Records for<br/>Fraudulent Advancement"):::threat
  T2M0["Manipulate student grade and transcript<br/>records to obtain fraudulent academic<br/>credentials or financial aid"]:::motive
  T2 --> T2M0
  T2M0C0("Ellucian Banner (SIS)"):::component
  T2M0 --> T2M0C0
  T2M0C0W0("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T2M0C0 --> T2M0C0W0
  T2M0C0W1("CWE-285: Improper Authorization"):::cwe
  T2M0C0 --> T2M0C0W1
  T2M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T2M0C0 --> T2M0C0W2
  T2M0C1("Oracle PeopleSoft Campus Solutions"):::component
  T2M0 --> T2M0C1
  T2M0C1W0("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T2M0C1 --> T2M0C1W0
  T2M0C1W1("CWE-285: Improper Authorization"):::cwe
  T2M0C1 --> T2M0C1W1
  T2M0C1W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T2M0C1 --> T2M0C1W2
  T2M0C2("University Registrar Portal"):::component
  T2M0 --> T2M0C2
  T2M0C2W0("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T2M0C2 --> T2M0C2W0
  T2M0C2W1("CWE-285: Improper Authorization"):::cwe
  T2M0C2 --> T2M0C2W1
  T2M0C2W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T2M0C2 --> T2M0C2W2
  T2M0C3("Financial Aid Database"):::component
  T2M0 --> T2M0C3
  T2M0C3W0("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T2M0C3 --> T2M0C3W0
  T2M0C3W1("CWE-285: Improper Authorization"):::cwe
  T2M0C3 --> T2M0C3W1
  T2M0C3W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T2M0C3 --> T2M0C3W2
  T3("Steal University Research Data and<br/>Intellectual Property"):::threat
  T3M0["Exfiltrate government-funded research data<br/>and pre-publication findings for competitive<br/>or national intelligence advantage"]:::motive
  T3 --> T3M0
  T3M0C0("Amazon Web Services (AWS) Research<br/>Environment"):::component
  T3M0 --> T3M0C0
  T3M0C0W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T3M0C0 --> T3M0C0W0
  T3M0C0W1("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T3M0C0 --> T3M0C0W1
  T3M0C0W2("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T3M0C0 --> T3M0C0W2
  T3M0C1("University Research Lab Server"):::component
  T3M0 --> T3M0C1
  T3M0C1W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T3M0C1 --> T3M0C1W0
  T3M0C1W1("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T3M0C1 --> T3M0C1W1
  T3M0C1W2("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T3M0C1 --> T3M0C1W2
  T3M0C2("High-Performance Computing (HPC) Cluster"):::component
  T3M0 --> T3M0C2
  T3M0C2W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T3M0C2 --> T3M0C2W0
  T3M0C2W1("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T3M0C2 --> T3M0C2W1
  T3M0C2W2("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T3M0C2 --> T3M0C2W2
  T3M0C3("Intellectual Property Repository"):::component
  T3M0 --> T3M0C3
  T3M0C3W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T3M0C3 --> T3M0C3W0
  T3M0C3W1("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T3M0C3 --> T3M0C3W1
  T3M0C3W2("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T3M0C3 --> T3M0C3W2
  T4("Encrypt University Systems for Ransom"):::threat
  T4M0["Encrypt university operational data to halt<br/>academic and administrative functions and<br/>extort ransom payment"]:::motive
  T4 --> T4M0
  T4M0C0("University File Server"):::component
  T4M0 --> T4M0C0
  T4M0C0W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T4M0C0 --> T4M0C0W0
  T4M0C0W1("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T4M0C0 --> T4M0C0W1
  T4M0C1("University Backup System"):::component
  T4M0 --> T4M0C1
  T4M0C1W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T4M0C1 --> T4M0C1W0
  T4M0C1W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T4M0C1 --> T4M0C1W1
  T4M0C2("Faculty Workstations"):::component
  T4M0 --> T4M0C2
  T4M0C2W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T4M0C2 --> T4M0C2W0
  T4M0C2W1("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T4M0C2 --> T4M0C2W1
  T4M0C3("On-Premise Email and Student Network Storage"):::component
  T4M0 --> T4M0C3
  T4M0C3W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T4M0C3 --> T4M0C3W0
  T4M0C3W1("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T4M0C3 --> T4M0C3W1
  T5("Defraud Students Through Tuition and Fee<br/>Payment System Manipulation"):::threat
  T5M0["Intercept, redirect, or falsify tuition and<br/>fee payments for direct financial gain"]:::motive
  T5 --> T5M0
  T5M0C0("Flywire (Payment Gateway)"):::component
  T5M0 --> T5M0C0
  T5M0C0W0("CWE-352: Cross-Site Request Forgery<br/>(CSRF)"):::cwe
  T5M0C0 --> T5M0C0W0
  T5M0C0W1("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T5M0C0 --> T5M0C0W1
  T5M0C0W2("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T5M0C0 --> T5M0C0W2
  T5M0C1("TransferMate (Payment Processor)"):::component
  T5M0 --> T5M0C1
  T5M0C1W0("CWE-352: Cross-Site Request Forgery<br/>(CSRF)"):::cwe
  T5M0C1 --> T5M0C1W0
  T5M0C1W1("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T5M0C1 --> T5M0C1W1
  T5M0C1W2("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T5M0C1 --> T5M0C1W2
  T5M0C2("University Financial Database"):::component
  T5M0 --> T5M0C2
  T5M0C2W0("CWE-352: Cross-Site Request Forgery<br/>(CSRF)"):::cwe
  T5M0C2 --> T5M0C2W0
  T5M0C2W1("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T5M0C2 --> T5M0C2W1
  T5M0C2W2("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T5M0C2 --> T5M0C2W2
  T5M0C3("University Billing Portal"):::component
  T5M0 --> T5M0C3
  T5M0C3W0("CWE-352: Cross-Site Request Forgery<br/>(CSRF)"):::cwe
  T5M0C3 --> T5M0C3W0
  T5M0C3W1("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T5M0C3 --> T5M0C3W1
  T5M0C3W2("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T5M0C3 --> T5M0C3W2
  T6("Distribute Malware Across University<br/>Networks to Harvest Credentials"):::threat
  T6M0["Deploy credential-harvesting malware across<br/>campus networks to enable account takeover<br/>and sustained institutional access"]:::motive
  T6 --> T6M0
  T6M0C0("Campus Authentication and Endpoint<br/>Infrastructure"):::component
  T6M0 --> T6M0C0
  T6M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T6M0C0 --> T6M0C0W0
  T6M0C0W1("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T6M0C0 --> T6M0C0W1
  T6M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T6M0C0 --> T6M0C0W2
  T6M0C0W3("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T6M0C0 --> T6M0C0W3
  T6M0C0W4("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T6M0C0 --> T6M0C0W4
  T6M0C1("University Web Applications and Network<br/>Services"):::component
  T6M0 --> T6M0C1
  T6M0C1W0("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T6M0C1 --> T6M0C1W0
  T6M0C1W1("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T6M0C1 --> T6M0C1W1
  T6M0C1W2("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T6M0C1 --> T6M0C1W2
  T6M0C1W3("CWE-434: Unrestricted Upload of File<br/>with Dangerous Type"):::cwe
  T6M0C1 --> T6M0C1W3
  T6M0C1W4("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T6M0C1 --> T6M0C1W4
  T7("Gain Unauthorized Physical Access to Campus<br/>Facilities"):::threat
  T7M0["Bypass electronic access controls to enter<br/>restricted campus facilities for theft,<br/>espionage, or sabotage"]:::motive
  T7 --> T7M0
  T7M0C0("Access Control Management Platform"):::component
  T7M0 --> T7M0C0
  T7M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T7M0C0 --> T7M0C0W0
  T7M0C0W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T7M0C0 --> T7M0C0W1
  T7M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T7M0C0 --> T7M0C0W2
  T7M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T7M0C0 --> T7M0C0W3
  T7M0C0W4("CWE-285: Improper Authorization"):::cwe
  T7M0C0 --> T7M0C0W4
  T7M0C0W5("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T7M0C0 --> T7M0C0W5
  T7M0C0W6("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T7M0C0 --> T7M0C0W6
  T7M0C1("Physical Access Control Hardware and<br/>Interfaces"):::component
  T7M0 --> T7M0C1
  T7M0C1W0("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T7M0C1 --> T7M0C1W0
  T7M0C1W1("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T7M0C1 --> T7M0C1W1
  T7M0C1W2("CWE-434: Unrestricted Upload of File<br/>with Dangerous Type"):::cwe
  T7M0C1 --> T7M0C1W2
  T7M0C1W3("CWE-20: Improper Input Validation"):::cwe
  T7M0C1 --> T7M0C1W3
  T8("Deny Students and Faculty Access to Digital<br/>Campus Services"):::threat
  T8M0["Exhaust digital service resources to deny<br/>students and faculty access during critical<br/>academic periods"]:::motive
  T8 --> T8M0
  T8M0C0("University Authentication and Session<br/>Management"):::component
  T8M0 --> T8M0C0
  T8M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T8M0C0 --> T8M0C0W0
  T8M0C0W1("CWE-307: Improper Restriction of<br/>Excessive Authentication Attempts"):::cwe
  T8M0C0 --> T8M0C0W1
  T8M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T8M0C0 --> T8M0C0W2
  T8M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T8M0C0 --> T8M0C0W3
  T8M0C0W4("CWE-285: Improper Authorization"):::cwe
  T8M0C0 --> T8M0C0W4
  T8M0C1("Campus Digital Service Applications"):::component
  T8M0 --> T8M0C1
  T8M0C1W0("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T8M0C1 --> T8M0C1W0
  T8M0C1W1("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T8M0C1 --> T8M0C1W1
  T8M0C1W2("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T8M0C1 --> T8M0C1W2
  T8M0C1W3("CWE-434: Unrestricted Upload of File<br/>with Dangerous Type"):::cwe
  T8M0C1 --> T8M0C1W3
  T8M0C1W4("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T8M0C1 --> T8M0C1W4
  T9("Hijack University Computing Resources for<br/>Cryptomining and Illicit Operations"):::threat
  T9M0["Gain unauthorized access to university<br/>computing infrastructure to conduct<br/>cryptomining and illicit compute operations<br/>at institutional expense"]:::motive
  T9 --> T9M0
  T9M0C0("Research Computing Access and Authorization"):::component
  T9M0 --> T9M0C0
  T9M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T9M0C0 --> T9M0C0W0
  T9M0C0W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T9M0C0 --> T9M0C0W1
  T9M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T9M0C0 --> T9M0C0W2
  T9M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T9M0C0 --> T9M0C0W3
  T9M0C0W4("CWE-285: Improper Authorization"):::cwe
  T9M0C0 --> T9M0C0W4
  T9M0C1("University Computing Management and Job<br/>Submission Infrastructure"):::component
  T9M0 --> T9M0C1
  T9M0C1W0("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T9M0C1 --> T9M0C1W0
  T9M0C1W1("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T9M0C1 --> T9M0C1W1
  T9M0C1W2("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T9M0C1 --> T9M0C1W2
  T9M0C1W3("CWE-434: Unrestricted Upload of File<br/>with Dangerous Type"):::cwe
  T9M0C1 --> T9M0C1W3
  T9M0C1W4("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T9M0C1 --> T9M0C1W4
  T10("Compromise Campus Building Systems to Create<br/>Physical Safety Hazards"):::threat
  T10M0["Manipulate campus building automation to<br/>create physical hazards for students and<br/>staff or render facilities unusable"]:::motive
  T10 --> T10M0
  T10M0C0("Building Management System Platform"):::component
  T10M0 --> T10M0C0
  T10M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T10M0C0 --> T10M0C0W0
  T10M0C0W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T10M0C0 --> T10M0C0W1
  T10M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T10M0C0 --> T10M0C0W2
  T10M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T10M0C0 --> T10M0C0W3
  T10M0C0W4("CWE-285: Improper Authorization"):::cwe
  T10M0C0 --> T10M0C0W4
  T10M0C1("Building Automation Control and OT Network"):::component
  T10M0 --> T10M0C1
  T10M0C1W0("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T10M0C1 --> T10M0C1W0
  T10M0C1W1("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T10M0C1 --> T10M0C1W1
  T10M0C1W2("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T10M0C1 --> T10M0C1W2
  T10M0C1W3("CWE-434: Unrestricted Upload of File<br/>with Dangerous Type"):::cwe
  T10M0C1 --> T10M0C1W3
  T10M0C1W4("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T10M0C1 --> T10M0C1W4
  T11("Defraud Federal Financial Aid Programs Using<br/>AI-Generated Ghost Student Identities"):::threat
  T11M0["Enroll AI-generated synthetic identities as<br/>students to fraudulently obtain and divert<br/>federal financial aid disbursements"]:::motive
  T11 --> T11M0
  T11M0C0("University Admissions and Enrollment System"):::component
  T11M0 --> T11M0C0
  T11M0C0W0("CWE-287: Improper Authentication"):::cwe
  T11M0C0 --> T11M0C0W0
  T11M0C0W1("CWE-20: Improper Input Validation"):::cwe
  T11M0C0 --> T11M0C0W1
  T11M0C0W2("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T11M0C0 --> T11M0C0W2
  T11M0C0W3("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T11M0C0 --> T11M0C0W3
  T11M0C1("Financial Aid Disbursement System"):::component
  T11M0 --> T11M0C1
  T11M0C1W0("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T11M0C1 --> T11M0C1W0
  T11M0C1W1("CWE-285: Improper Authorization"):::cwe
  T11M0C1 --> T11M0C1W1
  T11M0C1W2("CWE-287: Improper Authentication"):::cwe
  T11M0C1 --> T11M0C1W2
  T11M0C1W3("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T11M0C1 --> T11M0C1W3
  T12("Conduct State-Sponsored Espionage Against<br/>University Research Programs"):::threat
  T12M0["Exfiltrate government-funded defense and<br/>technology research through sustained long-<br/>dwell intrusion campaigns"]:::motive
  T12 --> T12M0
  T12M0C0("University Research Collaboration<br/>Infrastructure"):::component
  T12M0 --> T12M0C0
  T12M0C0W0("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T12M0C0 --> T12M0C0W0
  T12M0C0W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T12M0C0 --> T12M0C0W1
  T12M0C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T12M0C0 --> T12M0C0W2
  T12M0C0W3("CWE-346: Origin Validation Error"):::cwe
  T12M0C0 --> T12M0C0W3
  T12M0C1("Secure Research Computing Environment"):::component
  T12M0 --> T12M0C1
  T12M0C1W0("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T12M0C1 --> T12M0C1W0
  T12M0C1W1("CWE-521: Weak Password Requirements"):::cwe
  T12M0C1 --> T12M0C1W1
  T12M0C1W2("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T12M0C1 --> T12M0C1W2
  T13("Deceive University Staff Through AI-<br/>Generated Impersonation to Commit Payroll<br/>Fraud"):::threat
  T13M0["Deceive HR and payroll staff into disclosing<br/>credentials or authorizing fraudulent<br/>payroll changes through AI-generated<br/>impersonation"]:::motive
  T13 --> T13M0
  T13M0C0("University HR and Payroll Systems"):::component
  T13M0 --> T13M0C0
  T13M0C0W0("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T13M0C0 --> T13M0C0W0
  T13M0C0W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T13M0C0 --> T13M0C0W1
  T13M0C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T13M0C0 --> T13M0C0W2
  T13M0C0W3("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T13M0C0 --> T13M0C0W3
  T13M0C1("University Staff Email and Communication<br/>Systems"):::component
  T13M0 --> T13M0C1
  T13M0C1W0("CWE-346: Origin Validation Error"):::cwe
  T13M0C1 --> T13M0C1W0
  T13M0C1W1("CWE-287: Improper Authentication"):::cwe
  T13M0C1 --> T13M0C1W1

  classDef threat fill:firebrick,color:white
  classDef motive fill:indianred,color:white
  classDef component fill:chocolate,color:white
  classDef cwe fill:steelblue,color:white
```

Flowchart generated from [`higher-education.json`](../higher-education.json)
