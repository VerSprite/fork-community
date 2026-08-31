# Automotive Threat Library

```mermaid
---
config:
  layout: elk
---
flowchart LR
  T0("Steal Automotive Intellectual Property from<br/>Design and R&amp;D Systems"):::threat
  T0M0["Acquire proprietary vehicle design data and<br/>engineering specifications to replicate OEM<br/>technology without R&amp;D investment"]:::motive
  T0 --> T0M0
  T0M0C0[["Design and Engineering Systems"]]:::component
  T0M0 --> T0M0C0
  T0M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T0M0C0 --> T0M0C0W0
  T0M0C0W1("CWE-285: Improper Authorization"):::cwe
  T0M0C0 --> T0M0C0W1
  T0M0C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T0M0C0 --> T0M0C0W2
  T0M0C1[["Research and Development Networks"]]:::component
  T0M0 --> T0M0C1
  T0M0C1W0("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T0M0C1 --> T0M0C1W0
  T0M0C1W1("CWE-221: Information Loss or Omission"):::cwe
  T0M0C1 --> T0M0C1W1
  T0M0C1W2("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T0M0C1 --> T0M0C1W2
  T0M0C1W3("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T0M0C1 --> T0M0C1W3
  T0M1["Destroy or corrupt automotive design data to<br/>sabotage a competitor's vehicle development<br/>program"]:::motive
  T0 --> T0M1
  T0M1C0[["Design and Engineering Systems"]]:::component
  T0M1 --> T0M1C0
  T0M1C0W0("CWE-20: Improper Input Validation"):::cwe
  T0M1C0 --> T0M1C0W0
  T0M1C0W1("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T0M1C0 --> T0M1C0W1
  T1("Corrupt Automotive Manufacturing to Produce<br/>Defective Vehicles"):::threat
  T1M0["Introduce manufacturing defects into vehicle<br/>production to trigger costly recalls and<br/>damage brand reputation"]:::motive
  T1 --> T1M0
  T1M0C0[["Automated Manufacturing and Production<br/>Control Systems"]]:::component
  T1M0 --> T1M0C0
  T1M0C0W0("CWE-15: External Control of System or<br/>Configuration Setting"):::cwe
  T1M0C0 --> T1M0C0W0
  T1M0C0W1("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T1M0C0 --> T1M0C0W1
  T1M0C0W2("CWE-285: Improper Authorization"):::cwe
  T1M0C0 --> T1M0C0W2
  T1M0C1[["Industrial Control Systems (ICS) and Smart<br/>Manufacturing Platforms"]]:::component
  T1M0 --> T1M0C1
  T1M0C1W0("CWE-521: Weak Password Requirements"):::cwe
  T1M0C1 --> T1M0C1W0
  T1M0C1W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T1M0C1 --> T1M0C1W1
  T1M0C1W2("CWE-94: Improper Control of Generation<br/>of Code ('Code Injection')"):::cwe
  T1M0C1 --> T1M0C1W2
  T2("Lock Down Automotive Operations for Ransom"):::threat
  T2M0["Encrypt OEM production systems to halt<br/>vehicle manufacturing and extort ransom<br/>payment under sustained operational pressure"]:::motive
  T2 --> T2M0
  T2M0C0[["OEM Enterprise IT and Production Systems"]]:::component
  T2M0 --> T2M0C0
  T2M0C0W0("CWE-521: Weak Password Requirements"):::cwe
  T2M0C0 --> T2M0C0W0
  T2M0C0W1("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T2M0C0 --> T2M0C0W1
  T2M0C0W2("CWE-221: Information Loss or Omission"):::cwe
  T2M0C0 --> T2M0C0W2
  T2M0C1[["Dealer Management SaaS Provider Platform"]]:::component
  T2M0 --> T2M0C1
  T2M0C1W0("CWE-285: Improper Authorization"):::cwe
  T2M0C1 --> T2M0C1W0
  T2M0C1W1("CWE-829: Inclusion of Functionality from<br/>Untrusted Control Sphere"):::cwe
  T2M0C1 --> T2M0C1W1
  T2M1["Compromise a supplier to propagate<br/>ransomware into connected OEM networks and<br/>amplify disruption across the supply chain"]:::motive
  T2 --> T2M1
  T2M1C0[["Automotive Supplier Network Integration"]]:::component
  T2M1 --> T2M1C0
  T2M1C0W0("CWE-287: Improper Authentication"):::cwe
  T2M1C0 --> T2M1C0W0
  T2M1C0W1("CWE-285: Improper Authorization"):::cwe
  T2M1C0 --> T2M1C0W1
  T3("Compromise Vehicle Firmware and Safety-<br/>Critical Software"):::threat
  T3M0["Inject malicious firmware into vehicle ECUs<br/>to enable remote control or disable safety<br/>systems across a vehicle fleet"]:::motive
  T3 --> T3M0
  T3M0C0[["Vehicle Software and Embedded Firmware<br/>Systems"]]:::component
  T3M0 --> T3M0C0
  T3M0C0W0("CWE-798: Use of Hard-coded Credentials"):::cwe
  T3M0C0 --> T3M0C0W0
  T3M0C0W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T3M0C0 --> T3M0C0W1
  T3M0C0W2("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T3M0C0 --> T3M0C0W2
  T3M0C0W3("CWE-319: Cleartext Transmission of<br/>Sensitive Information"):::cwe
  T3M0C0 --> T3M0C0W3
  T3M0C1[["Remote Vehicle Maintenance and OTA Update<br/>Systems"]]:::component
  T3M0 --> T3M0C1
  T3M0C1W0("CWE-285: Improper Authorization"):::cwe
  T3M0C1 --> T3M0C1W0
  T3M1["Compromise supplier-embedded firmware before<br/>vehicles are manufactured to introduce<br/>safety vulnerabilities at scale"]:::motive
  T3 --> T3M1
  T3M1C0[["Supplier-Embedded Software and Firmware<br/>Systems"]]:::component
  T3M1 --> T3M1C0
  T3M1C0W0("CWE-506: Embedded Malicious Code"):::cwe
  T3M1C0 --> T3M1C0W0
  T3M1C0W1("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T3M1C0 --> T3M1C0W1
  T3M1C0W2("CWE-521: Weak Password Requirements"):::cwe
  T3M1C0 --> T3M1C0W2
  T4("Manipulate Vehicle Software to Defeat<br/>Emissions and Safety Standards"):::threat
  T4M0["Modify vehicle ECU calibrations to defeat<br/>emissions controls and generate fraudulent<br/>regulatory compliance"]:::motive
  T4 --> T4M0
  T4M0C0[["Vehicle ECU Calibration and Engine Control<br/>Systems"]]:::component
  T4M0 --> T4M0C0
  T4M0C0W0("CWE-285: Improper Authorization"):::cwe
  T4M0C0 --> T4M0C0W0
  T4M0C0W1("CWE-15: External Control of System or<br/>Configuration Setting"):::cwe
  T4M0C0 --> T4M0C0W1
  T4M0C1[["Vehicle Diagnostic and Tuning Systems"]]:::component
  T4M0 --> T4M0C1
  T4M0C1W0("CWE-285: Improper Authorization"):::cwe
  T4M0C1 --> T4M0C1W0
  T5("Harvest Driver Location and Telemetry Data<br/>from Connected Vehicle Platforms"):::threat
  T5M0["Extract continuous driver location histories<br/>and behavioral profiles for surveillance,<br/>stalking, or targeted exploitation"]:::motive
  T5 --> T5M0
  T5M0C0[["Vehicle Telematics Platform"]]:::component
  T5M0 --> T5M0C0
  T5M0C0W0("CWE-285: Improper Authorization"):::cwe
  T5M0C0 --> T5M0C0W0
  T5M0C0W1("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T5M0C0 --> T5M0C0W1
  T5M0C1[["EV Charging Network Platform"]]:::component
  T5M0 --> T5M0C1
  T5M0C1W0("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T5M0C1 --> T5M0C1W0
  T5M0C1W1("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T5M0C1 --> T5M0C1W1
  T6("Gain Unauthorized Remote Control of<br/>Connected Vehicles"):::threat
  T6M0["Take control of connected-vehicle command<br/>APIs to unlock, start and locate vehicles<br/>for theft and resale"]:::motive
  T6 --> T6M0
  T6M0C0[["Connected Vehicle API Gateway"]]:::component
  T6M0 --> T6M0C0
  T6M0C0W0("CWE-285: Improper Authorization"):::cwe
  T6M0C0 --> T6M0C0W0
  T6M0C0W1("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T6M0C0 --> T6M0C0W1
  T6M0C0W2("CWE-307: Improper Restriction of<br/>Excessive Authentication Attempts"):::cwe
  T6M0C0 --> T6M0C0W2
  T6M1["Establish persistent covert access to an<br/>individual's vehicle through a compromised<br/>aftermarket accessory for stalking or<br/>targeted extortion"]:::motive
  T6 --> T6M1
  T6M1C0[["Aftermarket Vehicle Accessories and OBD<br/>Interface"]]:::component
  T6M1 --> T6M1C0
  T6M1C0W0("CWE-798: Use of Hard-coded Credentials"):::cwe
  T6M1C0 --> T6M1C0W0
  T6M1C0W1("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T6M1C0 --> T6M1C0W1
  T6M1C0W2("CWE-285: Improper Authorization"):::cwe
  T6M1C0 --> T6M1C0W2
  T7("Compromise Autonomous Vehicle Perception and<br/>Driving Decision Systems"):::threat
  T7M0["Introduce perception failures into<br/>autonomous driving AI to create unsafe<br/>vehicle behavior at scale"]:::motive
  T7 --> T7M0
  T7M0C0[["Autonomous Driving AI System"]]:::component
  T7M0 --> T7M0C0
  T7M0C0W0("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T7M0C0 --> T7M0C0W0
  T7M0C0W1("CWE-506: Embedded Malicious Code"):::cwe
  T7M0C0 --> T7M0C0W1
  T7M0C0W2("CWE-285: Improper Authorization"):::cwe
  T7M0C0 --> T7M0C0W2
  T7M0C1[["ADAS Sensor and Perception Systems"]]:::component
  T7M0 --> T7M0C1
  T7M0C1W0("CWE-1039: Inadequate Detection or<br/>Handling of Adversarial Input<br/>Perturbations in Automated Recognition<br/>Mechanism"):::cwe
  T7M0C1 --> T7M0C1W0
  T8("Disrupt Fleet Dispatch and EV Charging<br/>Operations"):::threat
  T8M0["Deny dispatch and routing capabilities to<br/>commercial fleet operators by disabling<br/>fleet management infrastructure"]:::motive
  T8 --> T8M0
  T8M0C0[["Fleet Management Platform"]]:::component
  T8M0 --> T8M0C0
  T8M0C0W0("CWE-400: Uncontrolled Resource<br/>Consumption"):::cwe
  T8M0C0 --> T8M0C0W0
  T8M0C0W1("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T8M0C0 --> T8M0C0W1
  T8M0C0W2("CWE-287: Improper Authentication"):::cwe
  T8M0C0 --> T8M0C0W2
  T8M1["Disable EV charging availability across<br/>networks to deny electric vehicle mobility<br/>and undermine EV adoption"]:::motive
  T8 --> T8M1
  T8M1C0[["EV Charging Network Platform"]]:::component
  T8M1 --> T8M1C0
  T8M1C0W0("CWE-287: Improper Authentication"):::cwe
  T8M1C0 --> T8M1C0W0
  T8M1C0W1("CWE-285: Improper Authorization"):::cwe
  T8M1C0 --> T8M1C0W1
  T8M1C0W2("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T8M1C0 --> T8M1C0W2
  T9("Expose Dealership Customer Records and<br/>Financial Data"):::threat
  T9M0["Extract customer personal and financial<br/>records from dealer management systems for<br/>identity theft and fraud"]:::motive
  T9 --> T9M0
  T9M0C0[["Dealer Management System (DMS)"]]:::component
  T9M0 --> T9M0C0
  T9M0C0W0("CWE-287: Improper Authentication"):::cwe
  T9M0C0 --> T9M0C0W0
  T9M0C0W1("CWE-285: Improper Authorization"):::cwe
  T9M0C0 --> T9M0C0W1
  T9M0C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T9M0C0 --> T9M0C0W2
  T9M0C1[["Customer Financing and Credit Systems"]]:::component
  T9M0 --> T9M0C1
  T9M0C1W0("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T9M0C1 --> T9M0C1W0
  T9M0C1W1("CWE-89: Improper Neutralization of<br/>Special Elements used in an SQL Command<br/>('SQL Injection')"):::cwe
  T9M0C1 --> T9M0C1W1
  T10("Commit Financial Fraud Against Automotive<br/>Dealerships"):::threat
  T10M0["Manipulate vehicle financing records and<br/>ownership documentation for financial gain"]:::motive
  T10 --> T10M0
  T10M0C0[["Dealer Management System (DMS)"]]:::component
  T10M0 --> T10M0C0
  T10M0C0W0("CWE-285: Improper Authorization"):::cwe
  T10M0C0 --> T10M0C0W0
  T10M0C0W1("CWE-472: External Control of Assumed-<br/>Immutable Web Parameter"):::cwe
  T10M0C0 --> T10M0C0W1
  T10M0C1[["Dealership Payment Systems"]]:::component
  T10M0 --> T10M0C1
  T10M0C1W0("CWE-285: Improper Authorization"):::cwe
  T10M0C1 --> T10M0C1W0
  T11("Sell Driver Behavioral and Location Data to<br/>Third Parties Without Consent"):::threat
  T11M0["Monetize continuous driver location and<br/>behavioral data through unauthorized third-<br/>party data sales"]:::motive
  T11 --> T11M0
  T11M0C0[["Vehicle Telematics Data Monetization<br/>Platform"]]:::component
  T11M0 --> T11M0C0
  T11M0C0W0("CWE-269: Improper Privilege Management"):::cwe
  T11M0C0 --> T11M0C0W0
  T11M0C0W1("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T11M0C0 --> T11M0C0W1
  T11M0C0W2("CWE-359: Exposure of Private Personal<br/>Information to an Unauthorized Actor"):::cwe
  T11M0C0 --> T11M0C0W2
  T11M0C0W3("CWE-221: Information Loss or Omission"):::cwe
  T11M0C0 --> T11M0C0W3
  T11M0C1[["Connected Vehicle Consent Management System"]]:::component
  T11M0 --> T11M0C1
  T11M0C1W0("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T11M0C1 --> T11M0C1W0
  T12("Exploit Supplier Network Trust to Infiltrate<br/>OEM Manufacturing Systems"):::threat
  T12M0["Use trusted supplier-to-OEM network<br/>connections to access and attack OEM<br/>production systems that are inaccessible<br/>from the internet"]:::motive
  T12 --> T12M0
  T12M0C0[["Automotive Supplier Network Integration"]]:::component
  T12M0 --> T12M0C0
  T12M0C0W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T12M0C0 --> T12M0C0W0
  T12M0C0W1("CWE-269: Improper Privilege Management"):::cwe
  T12M0C0 --> T12M0C0W1
  T12M0C1[["OEM Supplier Collaboration Portal"]]:::component
  T12M0 --> T12M0C1
  T12M0C1W0("CWE-918: Server-Side Request Forgery<br/>(SSRF)"):::cwe
  T12M0C1 --> T12M0C1W0
  T12M0C1W1("CWE-221: Information Loss or Omission"):::cwe
  T12M0C1 --> T12M0C1W1
  T13("Corrupt Vehicle-to-Everything Communications<br/>to Endanger Road Users"):::threat
  T13M0["Inject false V2X messages to cause vehicles<br/>to make dangerous navigation decisions"]:::motive
  T13 --> T13M0
  T13M0C0[["V2X Communication Infrastructure"]]:::component
  T13M0 --> T13M0C0
  T13M0C0W0("CWE-940: Improper Verification of Source<br/>of a Communication Channel"):::cwe
  T13M0C0 --> T13M0C0W0
  T13M0C0W1("CWE-287: Improper Authentication"):::cwe
  T13M0C0 --> T13M0C0W1
  T13M0C1[["V2X Onboard Vehicle Processing Unit"]]:::component
  T13M0 --> T13M0C1
  T13M0C1W0("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T13M0C1 --> T13M0C1W0
  T13M0C1W1("CWE-346: Origin Validation Error"):::cwe
  T13M0C1 --> T13M0C1W1
  T14("Steal Vehicles Through Keyless Entry and In-<br/>Vehicle Network Access"):::threat
  T14M0["Steal a parked vehicle by defeating keyless<br/>entry"]:::motive
  T14 --> T14M0
  T14M0C0[["Passive Keyless Entry and Immobiliser<br/>Systems"]]:::component
  T14M0 --> T14M0C0
  T14M0C0W0("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T14M0C0 --> T14M0C0W0
  T14M0C0W1("CWE-300: Channel Accessible by Non-<br/>Endpoint"):::cwe
  T14M0C0 --> T14M0C0W1
  T14M0C0W2("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T14M0C0 --> T14M0C0W2
  T14M0C0W3("CWE-1191: On-Chip Debug and Test<br/>Interface With Improper Access Control"):::cwe
  T14M0C0 --> T14M0C0W3
  T14M0C1[["In-Vehicle Network and Body Control Modules"]]:::component
  T14M0 --> T14M0C1
  T14M0C1W0("CWE-940: Improper Verification of Source<br/>of a Communication Channel"):::cwe
  T14M0C1 --> T14M0C1W0
  T14M0C1W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T14M0C1 --> T14M0C1W1
  T14M0C1W2("CWE-1263: Improper Physical Access<br/>Control"):::cwe
  T14M0C1 --> T14M0C1W2
  T14M0C1W3("CWE-1299: Missing Protection Mechanism<br/>for Alternate Hardware Interface"):::cwe
  T14M0C1 --> T14M0C1W3
  T14M1["Retain or obtain a working digital key to<br/>access a vehicle"]:::motive
  T14 --> T14M1
  T14M1C0[["Phone-as-Key and Digital Key Provisioning"]]:::component
  T14M1 --> T14M1C0
  T14M1C0W0("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T14M1C0 --> T14M1C0W0
  T14M1C0W1("CWE-285: Improper Authorization"):::cwe
  T14M1C0 --> T14M1C0W1
  T14M1C0W2("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T14M1C0 --> T14M1C0W2
  T15("Compromise the Vehicle Cabin Through<br/>Infotainment and Cellular Interfaces"):::threat
  T15M0["Gain code execution on the infotainment head<br/>unit"]:::motive
  T15 --> T15M0
  T15M0C0[["In-Vehicle Infotainment and Head Unit"]]:::component
  T15M0 --> T15M0C0
  T15M0C0W0("CWE-287: Improper Authentication"):::cwe
  T15M0C0 --> T15M0C0W0
  T15M0C0W1("CWE-1299: Missing Protection Mechanism<br/>for Alternate Hardware Interface"):::cwe
  T15M0C0 --> T15M0C0W1
  T15M0C0W2("CWE-250: Execution with Unnecessary<br/>Privileges"):::cwe
  T15M0C0 --> T15M0C0W2
  T15M0C0W3("CWE-78: Improper Neutralization of<br/>Special Elements used in an OS Command<br/>('OS Command Injection')"):::cwe
  T15M0C0 --> T15M0C0W3
  T15M1["Falsify the vehicle's position data"]:::motive
  T15 --> T15M1
  T15M1C0[["Telematics Control Unit and Cellular<br/>Interface"]]:::component
  T15M1 --> T15M1C0
  T15M1C0W0("CWE-923: Improper Restriction of<br/>Communication Channel to Intended<br/>Endpoints"):::cwe
  T15M1C0 --> T15M1C0W0
  T15M1C0W1("CWE-1256: Improper Restriction of<br/>Software Interfaces to Hardware Features"):::cwe
  T15M1C0 --> T15M1C0W1
  T15M1C0W2("CWE-940: Improper Verification of Source<br/>of a Communication Channel"):::cwe
  T15M1C0 --> T15M1C0W2

  classDef threat fill:darkred,stroke:maroon,color:white
  classDef motive fill:chocolate,stroke:sienna,color:white
  classDef component fill:navy,stroke:midnightblue,color:white
  classDef cwe fill:darkgreen,stroke:darkslategrey,color:white
```

Flowchart generated from [`automotive.json`](../automotive.json)
