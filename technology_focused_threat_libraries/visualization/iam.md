# IAM and Identity Provider Threat Library

```mermaid
---
config:
  layout: elk
  flowchart:
    curve: step
---
flowchart LR
  T0("Take Over Workforce Accounts by Defeating<br/>Multi-Factor Authentication"):::threat
  T0M0["Capture live authentication sessions to<br/>obtain valid enterprise tokens and operate<br/>as the employee across every federated<br/>application"]:::motive
  T0 --> T0M0
  T0M0C0("Workforce Sign-In Portal"):::component
  T0M0 --> T0M0C0
  T0M0C0W0("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T0M0C0 --> T0M0C0W0
  T0M0C0W1("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T0M0C0 --> T0M0C0W1
  T0M0C1("Session and Token Issuance Service"):::component
  T0M0 --> T0M0C1
  T0M0C1W0("CWE-384: Session Fixation"):::cwe
  T0M0C1 --> T0M0C1W0
  T0M0C1W1("CWE-613: Insufficient Session Expiration"):::cwe
  T0M0C1 --> T0M0C1W1
  T0M0C1W2("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T0M0C1 --> T0M0C1W2
  T0M0C1W3("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T0M0C1 --> T0M0C1W3
  T0M1["Enroll an attacker-controlled authenticator<br/>on a targeted employee account to hold<br/>access independent of the original device"]:::motive
  T0 --> T0M1
  T0M1C0("Authenticator Enrollment and Delivery<br/>Channel"):::component
  T0M1 --> T0M1C0
  T0M1C0W0("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T0M1C0 --> T0M1C0W0
  T0M1C0W1("CWE-640: Weak Password Recovery<br/>Mechanism for Forgotten Password"):::cwe
  T0M1C0 --> T0M1C0W1
  T0M1C0W2("CWE-330: Use of Insufficiently Random<br/>Values"):::cwe
  T0M1C0 --> T0M1C0W2
  T0M1C0W3("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T0M1C0 --> T0M1C0W3
  T0M1C0W4("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T0M1C0 --> T0M1C0W4
  T1("Impersonate Any Enterprise User by Forging<br/>Federated Authentication Assertions"):::threat
  T1M0["Steal the federation signing key to mint<br/>assertions for any user of any connected<br/>application without touching a password"]:::motive
  T1 --> T1M0
  T1M0C0("Token Signing Key Custody"):::component
  T1M0 --> T1M0C0
  T1M0C0W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T1M0C0 --> T1M0C0W0
  T1M0C0W1("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T1M0C0 --> T1M0C0W1
  T1M0C0W2("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T1M0C0 --> T1M0C0W2
  T1M0C0W3("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T1M0C0 --> T1M0C0W3
  T1M0C1("Federation Service"):::component
  T1M0 --> T1M0C1
  T1M0C1W0("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T1M0C1 --> T1M0C1W0
  T1M0C1W1("CWE-15: External Control of System or<br/>Configuration Setting"):::cwe
  T1M0C1 --> T1M0C1W1
  T1M0C2("Relying Party Assertion Validation"):::component
  T1M0 --> T1M0C2
  T1M0C2W0("CWE-347: Improper Verification of<br/>Cryptographic Signature"):::cwe
  T1M0C2 --> T1M0C2W0
  T1M0C2W1("CWE-91: XML Injection (aka Blind XPath<br/>Injection)"):::cwe
  T1M0C2 --> T1M0C2W1
  T1M1["Register an attacker-controlled identity<br/>provider in the tenant so that account<br/>linking survives every password reset"]:::motive
  T1 --> T1M1
  T1M1C0("Identity Provider Trust Configuration"):::component
  T1M1 --> T1M1C0
  T1M1C0W0("CWE-285: Improper Authorization"):::cwe
  T1M1C0 --> T1M1C0W0
  T1M1C0W1("CWE-302: Authentication Bypass by<br/>Assumed-Immutable Data"):::cwe
  T1M1C0 --> T1M1C0W1
  T1M1C0W2("CWE-346: Origin Validation Error"):::cwe
  T1M1C0 --> T1M1C0W2
  T1M1C0W3("CWE-295: Improper Certificate Validation"):::cwe
  T1M1C0 --> T1M1C0W3
  T2("Seize Enterprise-Wide Administrative Control<br/>of the Identity Directory"):::threat
  T2M0["Convert a standard directory account into a<br/>domain administrator to reach every system<br/>the directory authenticates"]:::motive
  T2 --> T2M0
  T2M0C0("Domain Controller"):::component
  T2M0 --> T2M0C0
  T2M0C0W0("CWE-309: Use of Password System for<br/>Primary Authentication"):::cwe
  T2M0C0 --> T2M0C0W0
  T2M0C0W1("CWE-836: Use of Password Hash Instead of<br/>Password for Authentication"):::cwe
  T2M0C0 --> T2M0C0W1
  T2M0C0W2("CWE-285: Improper Authorization"):::cwe
  T2M0C0 --> T2M0C0W2
  T2M0C0W3("CWE-269: Improper Privilege Management"):::cwe
  T2M0C0 --> T2M0C0W3
  T2M0C1("Enterprise Certificate Authority"):::component
  T2M0 --> T2M0C1
  T2M0C1W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T2M0C1 --> T2M0C1W0
  T2M0C1W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T2M0C1 --> T2M0C1W1
  T2M1["Sell verified administrative access to the<br/>enterprise directory to ransomware and<br/>espionage operators"]:::motive
  T2 --> T2M1
  T2M1C0("Cloud Directory Tenant"):::component
  T2M1 --> T2M1C0
  T2M1C0W0("CWE-269: Improper Privilege Management"):::cwe
  T2M1C0 --> T2M1C0W0
  T2M1C0W1("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T2M1C0 --> T2M1C0W1
  T2M1C0W2("CWE-285: Improper Authorization"):::cwe
  T2M1C0 --> T2M1C0W2
  T2M1C1("Hybrid Directory Synchronization Connector"):::component
  T2M1 --> T2M1C1
  T2M1C1W0("CWE-250: Execution with Unnecessary<br/>Privileges"):::cwe
  T2M1C1 --> T2M1C1W0
  T2M1C1W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T2M1C1 --> T2M1C1W1
  T3("Encrypt Enterprise Operations for Ransom<br/>Through Directory Compromise"):::threat
  T3M0["Use directory-wide administrative control to<br/>encrypt every domain-joined system at once<br/>and extort payment for restoration"]:::motive
  T3 --> T3M0
  T3M0C0("Domain Controller"):::component
  T3M0 --> T3M0C0
  T3M0C0W0("CWE-285: Improper Authorization"):::cwe
  T3M0C0 --> T3M0C0W0
  T3M0C0W1("CWE-250: Execution with Unnecessary<br/>Privileges"):::cwe
  T3M0C0 --> T3M0C0W1
  T3M0C1("Privileged Access Tier"):::component
  T3M0 --> T3M0C1
  T3M0C1W0("CWE-923: Improper Restriction of<br/>Communication Channel to Intended<br/>Endpoints"):::cwe
  T3M0C1 --> T3M0C1W0
  T3M0C1W1("CWE-272: Least Privilege Violation"):::cwe
  T3M0C1 --> T3M0C1W1
  T3M0C2("Directory Backup and Forest Recovery Store"):::component
  T3M0 --> T3M0C2
  T3M0C2W0("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T3M0C2 --> T3M0C2W0
  T3M0C2W1("CWE-312: Cleartext Storage of Sensitive<br/>Information"):::cwe
  T3M0C2 --> T3M0C2W1
  T3M0C2W2("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T3M0C2 --> T3M0C2W2
  T4("Exfiltrate Directory and Customer Identity<br/>Records from Identity Platforms"):::threat
  T4M0["Extract the complete user directory with<br/>attributes and group memberships to enable<br/>targeted intrusion and resale"]:::motive
  T4 --> T4M0
  T4M0C0("Directory Data Store"):::component
  T4M0 --> T4M0C0
  T4M0C0W0("CWE-90: Improper Neutralization of<br/>Special Elements used in an LDAP Query<br/>('LDAP Injection')"):::cwe
  T4M0C0 --> T4M0C0W0
  T4M0C0W1("CWE-285: Improper Authorization"):::cwe
  T4M0C0 --> T4M0C0W1
  T4M0C1("Identity Management API"):::component
  T4M0 --> T4M0C1
  T4M0C1W0("CWE-302: Authentication Bypass by<br/>Assumed-Immutable Data"):::cwe
  T4M0C1 --> T4M0C1W0
  T4M0C1W1("CWE-770: Allocation of Resources Without<br/>Limits or Throttling"):::cwe
  T4M0C1 --> T4M0C1W1
  T4M1["Harvest stored credential material and<br/>recovery secrets from identity data stores<br/>for offline cracking and reuse"]:::motive
  T4 --> T4M1
  T4M1C0("Credential and Secret Storage"):::component
  T4M1 --> T4M1C0
  T4M1C0W0("CWE-312: Cleartext Storage of Sensitive<br/>Information"):::cwe
  T4M1C0 --> T4M1C0W0
  T4M1C0W1("CWE-916: Use of Password Hash With<br/>Insufficient Computational Effort"):::cwe
  T4M1C0 --> T4M1C0W1
  T4M1C0W2("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T4M1C0 --> T4M1C0W2
  T4M1C1("Identity Platform Diagnostic Export"):::component
  T4M1 --> T4M1C1
  T4M1C1W0("CWE-532: Insertion of Sensitive<br/>Information into Log File"):::cwe
  T4M1C1 --> T4M1C1W0
  T4M1C1W1("CWE-359: Exposure of Private Personal<br/>Information to an Unauthorized Actor"):::cwe
  T4M1C1 --> T4M1C1W1
  T5("Defraud Customers Through Mass Account<br/>Takeover of Consumer Identity Platforms"):::threat
  T5M0["Replay breached credential lists against<br/>consumer sign-in endpoints at scale to seize<br/>accounts holding stored value and payment<br/>methods"]:::motive
  T5 --> T5M0
  T5M0C0("Consumer Sign-In Endpoint"):::component
  T5M0 --> T5M0C0
  T5M0C0W0("CWE-307: Improper Restriction of<br/>Excessive Authentication Attempts"):::cwe
  T5M0C0 --> T5M0C0W0
  T5M0C0W1("CWE-521: Weak Password Requirements"):::cwe
  T5M0C0 --> T5M0C0W1
  T5M0C0W2("CWE-601: URL Redirection to Untrusted<br/>Site ('Open Redirect')"):::cwe
  T5M0C0 --> T5M0C0W2
  T5M0C0W3("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T5M0C0 --> T5M0C0W3
  T5M0C0W4("CWE-302: Authentication Bypass by<br/>Assumed-Immutable Data"):::cwe
  T5M0C0 --> T5M0C0W4
  T5M1["Take over consumer accounts through self-<br/>service recovery without ever holding the<br/>original credential"]:::motive
  T5 --> T5M1
  T5M1C0("Account Recovery Flow"):::component
  T5M1 --> T5M1C0
  T5M1C0W0("CWE-640: Weak Password Recovery<br/>Mechanism for Forgotten Password"):::cwe
  T5M1C0 --> T5M1C0W0
  T5M1C0W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T5M1C0 --> T5M1C0W1
  T5M1C1("Social Login and External Identity Broker"):::component
  T5M1 --> T5M1C1
  T5M1C1W0("CWE-346: Origin Validation Error"):::cwe
  T5M1C1 --> T5M1C1W0
  T5M1C1W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T5M1C1 --> T5M1C1W1
  T6("Extract Data From Connected Platforms by<br/>Abusing Delegated OAuth Authorization"):::threat
  T6M0["Obtain a durable consent grant from a user<br/>or administrator so that data access<br/>continues after every password and session<br/>reset"]:::motive
  T6 --> T6M0
  T6M0C0("OAuth Authorization Server"):::component
  T6M0 --> T6M0C0
  T6M0C0W0("CWE-285: Improper Authorization"):::cwe
  T6M0C0 --> T6M0C0W0
  T6M0C0W1("CWE-267: Privilege Defined With Unsafe<br/>Actions"):::cwe
  T6M0C0 --> T6M0C0W1
  T6M0C0W2("CWE-613: Insufficient Session Expiration"):::cwe
  T6M0C0 --> T6M0C0W2
  T6M0C1("Application Registration and Consent Catalog"):::component
  T6M0 --> T6M0C1
  T6M0C1W0("CWE-346: Origin Validation Error"):::cwe
  T6M0C1 --> T6M0C1W0
  T6M0C1W1("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T6M0C1 --> T6M0C1W1
  T6M1["Steal refresh tokens held by an integration<br/>vendor and query every tenant that<br/>authorized it"]:::motive
  T6 --> T6M1
  T6M1C0("Integration Vendor Token Store"):::component
  T6M1 --> T6M1C0
  T6M1C0W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T6M1C0 --> T6M1C0W0
  T6M1C0W1("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T6M1C0 --> T6M1C0W1
  T6M1C1("Connected Platform Integration API"):::component
  T6M1 --> T6M1C1
  T6M1C1W0("CWE-302: Authentication Bypass by<br/>Assumed-Immutable Data"):::cwe
  T6M1C1 --> T6M1C1W0
  T6M1C1W1("CWE-770: Allocation of Resources Without<br/>Limits or Throttling"):::cwe
  T6M1C1 --> T6M1C1W1
  T7("Compromise Identity Platform Suppliers to<br/>Reach Every Downstream Tenant"):::threat
  T7M0["Compromise an identity platform supplier to<br/>reach the authentication of every customer<br/>tenant through one trusted channel"]:::motive
  T7 --> T7M0
  T7M0C0("Identity Platform Vendor Software and Update<br/>Channel"):::component
  T7M0 --> T7M0C0
  T7M0C0W0("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T7M0C0 --> T7M0C0W0
  T7M0C0W1("CWE-347: Improper Verification of<br/>Cryptographic Signature"):::cwe
  T7M0C0 --> T7M0C0W1
  T7M0C0W2("CWE-829: Inclusion of Functionality from<br/>Untrusted Control Sphere"):::cwe
  T7M0C0 --> T7M0C0W2
  T7M0C0W3("CWE-506: Embedded Malicious Code"):::cwe
  T7M0C0 --> T7M0C0W3
  T7M0C1("Managed Service Provider Delegated<br/>Administration"):::component
  T7M0 --> T7M0C1
  T7M0C1W0("CWE-269: Improper Privilege Management"):::cwe
  T7M0C1 --> T7M0C1W0
  T7M0C1W1("CWE-285: Improper Authorization"):::cwe
  T7M0C1 --> T7M0C1W1
  T7M0C2("Vendor Support and Diagnostic Channel"):::component
  T7M0 --> T7M0C2
  T7M0C2W0("CWE-532: Insertion of Sensitive<br/>Information into Log File"):::cwe
  T7M0C2 --> T7M0C2W0
  T7M0C2W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T7M0C2 --> T7M0C2W1
  T8("Hijack Machine and Workload Identities to<br/>Reach Production Data and Compute"):::threat
  T8M0["Recover long-lived service credentials from<br/>code, pipelines and configuration to<br/>authenticate to production data as a trusted<br/>workload"]:::motive
  T8 --> T8M0
  T8M0C0("Secrets Manager and Credential Vault"):::component
  T8M0 --> T8M0C0
  T8M0C0W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T8M0C0 --> T8M0C0W0
  T8M0C0W1("CWE-285: Improper Authorization"):::cwe
  T8M0C0 --> T8M0C0W1
  T8M0C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T8M0C0 --> T8M0C0W2
  T8M0C0W3("CWE-613: Insufficient Session Expiration"):::cwe
  T8M0C0 --> T8M0C0W3
  T8M0C1("Build Pipeline and Source Repository<br/>Identity"):::component
  T8M0 --> T8M0C1
  T8M0C1W0("CWE-798: Use of Hard-coded Credentials"):::cwe
  T8M0C1 --> T8M0C1W0
  T8M0C1W1("CWE-250: Execution with Unnecessary<br/>Privileges"):::cwe
  T8M0C1 --> T8M0C1W1
  T8M0C1W2("CWE-312: Cleartext Storage of Sensitive<br/>Information"):::cwe
  T8M0C1 --> T8M0C1W2
  T8M1["Assume over-scoped workload roles to run<br/>attacker compute and reach data stores no<br/>human account could open"]:::motive
  T8 --> T8M1
  T8M1C0("Workload Identity Federation"):::component
  T8M1 --> T8M1C0
  T8M1C0W0("CWE-346: Origin Validation Error"):::cwe
  T8M1C0 --> T8M1C0W0
  T8M1C0W1("CWE-295: Improper Certificate Validation"):::cwe
  T8M1C0 --> T8M1C0W1
  T8M1C1("Container and Service Mesh Identity"):::component
  T8M1 --> T8M1C1
  T8M1C1W0("CWE-250: Execution with Unnecessary<br/>Privileges"):::cwe
  T8M1C1 --> T8M1C1W0
  T8M1C1W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T8M1C1 --> T8M1C1W1
  T8M1C1W2("CWE-295: Improper Certificate Validation"):::cwe
  T8M1C1 --> T8M1C1W2
  T9("Abuse Insider Identity Administration to<br/>Create Covert Standing Access"):::threat
  T9M0["Grant covert entitlements to attacker-<br/>controlled accounts and clear them through<br/>the reviewer's own authority"]:::motive
  T9 --> T9M0
  T9M0C0("Identity Governance and Access Certification"):::component
  T9M0 --> T9M0C0
  T9M0C0W0("CWE-269: Improper Privilege Management"):::cwe
  T9M0C0 --> T9M0C0W0
  T9M0C0W1("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T9M0C0 --> T9M0C0W1
  T9M0C0W2("CWE-285: Improper Authorization"):::cwe
  T9M0C0 --> T9M0C0W2
  T9M0C0W3("CWE-267: Privilege Defined With Unsafe<br/>Actions"):::cwe
  T9M0C0 --> T9M0C0W3
  T9M0C1("Privileged Role Assignment"):::component
  T9M0 --> T9M0C1
  T9M0C1W0("CWE-276: Incorrect Default Permissions"):::cwe
  T9M0C1 --> T9M0C1W0
  T9M0C1W1("CWE-613: Insufficient Session Expiration"):::cwe
  T9M0C1 --> T9M0C1W1
  T9M1["Retain access after departure through<br/>accounts and entitlements the leaver process<br/>never removes"]:::motive
  T9 --> T9M1
  T9M1C0("Joiner-Mover-Leaver Provisioning Workflow"):::component
  T9M1 --> T9M1C0
  T9M1C0W0("CWE-613: Insufficient Session Expiration"):::cwe
  T9M1C0 --> T9M1C0W0
  T9M1C0W1("CWE-309: Use of Password System for<br/>Primary Authentication"):::cwe
  T9M1C0 --> T9M1C0W1
  T9M1C1("Break-Glass Emergency Account"):::component
  T9M1 --> T9M1C1
  T9M1C1W0("CWE-798: Use of Hard-coded Credentials"):::cwe
  T9M1C1 --> T9M1C1W0
  T9M1C1W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T9M1C1 --> T9M1C1W1
  T10("Erase Identity Audit Evidence to Defeat<br/>Investigation and Compliance Attestation"):::threat
  T10M0["Destroy and forge identity audit records so<br/>that the intrusion cannot be reconstructed<br/>or attested to regulators"]:::motive
  T10 --> T10M0
  T10M0C0("Identity Audit Log Pipeline and Detection<br/>Configuration"):::component
  T10M0 --> T10M0C0
  T10M0C0W0("CWE-117: Improper Output Neutralization<br/>for Logs"):::cwe
  T10M0C0 --> T10M0C0W0
  T10M0C0W1("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T10M0C0 --> T10M0C0W1
  T10M0C0W2("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T10M0C0 --> T10M0C0W2
  T10M0C0W3("CWE-15: External Control of System or<br/>Configuration Setting"):::cwe
  T10M0C0 --> T10M0C0W3
  T10M0C1("Sign-In and Administrative Event Store"):::component
  T10M0 --> T10M0C1
  T10M0C1W0("CWE-269: Improper Privilege Management"):::cwe
  T10M0C1 --> T10M0C1W0
  T10M0C1W1("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T10M0C1 --> T10M0C1W1
  T11("Deny Authentication Services to Halt Every<br/>Dependent Business Application"):::threat
  T11M0["Exhaust authentication service capacity so<br/>that no user can sign in to any dependent<br/>application"]:::motive
  T11 --> T11M0
  T11M0C0("Authentication Endpoint and Lockout Policy"):::component
  T11M0 --> T11M0C0
  T11M0C0W0("CWE-770: Allocation of Resources Without<br/>Limits or Throttling"):::cwe
  T11M0C0 --> T11M0C0W0
  T11M0C0W1("CWE-307: Improper Restriction of<br/>Excessive Authentication Attempts"):::cwe
  T11M0C0 --> T11M0C0W1
  T11M0C0W2("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T11M0C0 --> T11M0C0W2
  T11M1["Destroy directory objects and federation<br/>configuration so that access cannot be<br/>restored from the platform itself"]:::motive
  T11 --> T11M1
  T11M1C0("Directory Object Lifecycle"):::component
  T11M1 --> T11M1C0
  T11M1C0W0("CWE-269: Improper Privilege Management"):::cwe
  T11M1C0 --> T11M1C0W0
  T11M1C0W1("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T11M1C0 --> T11M1C0W1
  T11M1C1("Federation Trust Configuration"):::component
  T11M1 --> T11M1C1
  T11M1C1W0("CWE-15: External Control of System or<br/>Configuration Setting"):::cwe
  T11M1C1 --> T11M1C1W0
  T11M1C1W1("CWE-353: Missing Support for Integrity<br/>Check"):::cwe
  T11M1C1 --> T11M1C1W1
  T12("Gain Unauthorized Physical Access by<br/>Subverting Converged Badge and Credential<br/>Issuance"):::threat
  T12M0["Obtain a working physical credential through<br/>the identity platform's own badge issuance<br/>path to enter restricted facilities"]:::motive
  T12 --> T12M0
  T12M0C0("Physical Access Control System"):::component
  T12M0 --> T12M0C0
  T12M0C0W0("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T12M0C0 --> T12M0C0W0
  T12M0C0W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T12M0C0 --> T12M0C0W1
  T12M0C0W2("CWE-285: Improper Authorization"):::cwe
  T12M0C0 --> T12M0C0W2
  T12M0C0W3("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T12M0C0 --> T12M0C0W3
  T12M0C0W4("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T12M0C0 --> T12M0C0W4
  T12M0C0W5("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T12M0C0 --> T12M0C0W5
  T12M0C1("Identity to Physical Access Provisioning<br/>Bridge"):::component
  T12M0 --> T12M0C1
  T12M0C1W0("CWE-353: Missing Support for Integrity<br/>Check"):::cwe
  T12M0C1 --> T12M0C1W0
  T13("Defeat Identity Proofing and Help Desk<br/>Verification With AI-Generated Personas"):::threat
  T13M0["Pass identity proofing and help desk<br/>verification with synthetic personas to<br/>obtain a legitimate credential for a<br/>fabricated identity"]:::motive
  T13 --> T13M0
  T13M0C0("Remote Identity Proofing and Biometric<br/>Capture"):::component
  T13M0 --> T13M0C0
  T13M0C0W0("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T13M0C0 --> T13M0C0W0
  T13M0C0W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T13M0C0 --> T13M0C0W1
  T13M0C0W2("CWE-346: Origin Validation Error"):::cwe
  T13M0C0 --> T13M0C0W2
  T13M0C0W3("CWE-353: Missing Support for Integrity<br/>Check"):::cwe
  T13M0C0 --> T13M0C0W3
  T13M0C1("Help Desk and IT Support"):::component
  T13M0 --> T13M0C1
  T13M0C1W0("CWE-287: Improper Authentication"):::cwe
  T13M0C1 --> T13M0C1W0
  T13M0C1W1("CWE-640: Weak Password Recovery<br/>Mechanism for Forgotten Password"):::cwe
  T13M0C1 --> T13M0C1W1
  T13M0C1W2("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T13M0C1 --> T13M0C1W2
  T14("Hijack AI Agent Delegated Authority to Act<br/>Across Enterprise Systems"):::threat
  T14M0["Redirect an autonomous agent's delegated<br/>authority through injected content to act<br/>against enterprise systems under a trusted<br/>identity"]:::motive
  T14 --> T14M0
  T14M0C0("AI Agent Identity and Delegation Chain"):::component
  T14M0 --> T14M0C0
  T14M0C0W0("CWE-441: Unintended Proxy or<br/>Intermediary ('Confused Deputy')"):::cwe
  T14M0C0 --> T14M0C0W0
  T14M0C0W1("CWE-269: Improper Privilege Management"):::cwe
  T14M0C0 --> T14M0C0W1
  T14M0C1("Agent Tool and Connector Authorization"):::component
  T14M0 --> T14M0C1
  T14M0C1W0("CWE-285: Improper Authorization"):::cwe
  T14M0C1 --> T14M0C1W0
  T14M0C1W1("CWE-267: Privilege Defined With Unsafe<br/>Actions"):::cwe
  T14M0C1 --> T14M0C1W1
  T14M0C1W2("CWE-1427: Improper Neutralization of<br/>Input Used for LLM Prompting"):::cwe
  T14M0C1 --> T14M0C1W2
  T14M0C2("Agent Credential and Context Store"):::component
  T14M0 --> T14M0C2
  T14M0C2W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T14M0C2 --> T14M0C2W0
  T14M0C2W1("CWE-312: Cleartext Storage of Sensitive<br/>Information"):::cwe
  T14M0C2 --> T14M0C2W1
  T14M0C2W2("CWE-798: Use of Hard-coded Credentials"):::cwe
  T14M0C2 --> T14M0C2W2
  T14M0C2W3("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T14M0C2 --> T14M0C2W3
  T15("Sell Customer Identity and Behavioral Data<br/>Beyond the Scope of Consent"):::threat
  T15M0["Monetize authentication telemetry and<br/>identity attributes beyond the consented<br/>purpose for advertising and data broker<br/>revenue"]:::motive
  T15 --> T15M0
  T15M0C0("Consent and Preference Store"):::component
  T15M0 --> T15M0C0
  T15M0C0W0("CWE-359: Exposure of Private Personal<br/>Information to an Unauthorized Actor"):::cwe
  T15M0C0 --> T15M0C0W0
  T15M0C0W1("CWE-285: Improper Authorization"):::cwe
  T15M0C0 --> T15M0C0W1
  T15M0C0W2("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T15M0C0 --> T15M0C0W2
  T15M0C1("Authentication Telemetry and Device<br/>Fingerprinting"):::component
  T15M0 --> T15M0C1
  T15M0C1W0("CWE-359: Exposure of Private Personal<br/>Information to an Unauthorized Actor"):::cwe
  T15M0C1 --> T15M0C1W0
  T15M0C2("Partner Data Sharing Interface"):::component
  T15M0 --> T15M0C2
  T15M0C2W0("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T15M0C2 --> T15M0C2W0
  T15M0C2W1("CWE-302: Authentication Bypass by<br/>Assumed-Immutable Data"):::cwe
  T15M0C2 --> T15M0C2W1
  T15M0C2W2("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T15M0C2 --> T15M0C2W2

  classDef threat fill:firebrick,color:white
  classDef motive fill:indianred,color:white
  classDef component fill:chocolate,color:white
  classDef cwe fill:steelblue,color:white
```

Flowchart generated from [`iam.json`](../iam.json)
