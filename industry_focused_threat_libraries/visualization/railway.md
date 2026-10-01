# Railway Threat Library

```mermaid
---
config:
  layout: elk
  flowchart:
    curve: step
---
flowchart LR
  T0("Forge Train Braking and Control Commands<br/>over the End-of-Train / Head-of-Train<br/>Radio Link"):::threat
  T0M0["Trigger sudden unintended braking on a<br/>moving freight train to cause derailment,<br/>operational chaos, or physical damage"]:::motive
  T0 --> T0M0
  T0M0C0("End-of-Train / Head-of-Train Device<br/>(EoT/HoT, 'FRED')"):::component
  T0M0 --> T0M0C0
  T0M0C0W0("CWE-1390: Weak Authentication"):::cwe
  T0M0C0 --> T0M0C0W0
  T0M0C0W1("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T0M0C0 --> T0M0C0W1
  T0M0C0W2("CWE-346: Origin Validation Error"):::cwe
  T0M0C0 --> T0M0C0W2
  T0M0C1("Locomotive Brake Control and Air Brake<br/>Interface"):::component
  T0M0 --> T0M0C1
  T0M0C1W0("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T0M0C1 --> T0M0C1W0
  T0M1["Suppress legitimate braking commands to<br/>defeat the train's safety response and<br/>endanger operations"]:::motive
  T0 --> T0M1
  T0M1C0("End-of-Train / Head-of-Train Device<br/>(EoT/HoT, 'FRED')"):::component
  T0M1 --> T0M1C0
  T0M1C0W0("CWE-940: Improper Verification of Source<br/>of a Communication Channel"):::cwe
  T0M1C0 --> T0M1C0W0
  T0M1C0W1("CWE-300: Channel Accessible by<br/>Non-Endpoint"):::cwe
  T0M1C0 --> T0M1C0W1
  T1("Halt Trains by Spoofing Analog Trackside<br/>and Cab Radio Emergency-Stop Signals"):::threat
  T1M0["Cause nationwide service disruption and<br/>sow public fear by remotely forcing<br/>trains to emergency-stop with cheap radio<br/>equipment"]:::motive
  T1 --> T1M0
  T1M0C0("Analog Train Radio and Radio-Stop System<br/>(VHF 150 MHz)"):::component
  T1M0 --> T1M0C0
  T1M0C0W0("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T1M0C0 --> T1M0C0W0
  T1M0C0W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T1M0C0 --> T1M0C0W1
  T1M0C1("GSM-R Cab Radio and Bearer Network"):::component
  T1M0 --> T1M0C1
  T1M0C1W0("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T1M0C1 --> T1M0C1W0
  T1M0C1W1("CWE-940: Improper Verification of Source<br/>of a Communication Channel"):::cwe
  T1M0C1 --> T1M0C1W1
  T2("Spoof or Tamper with Trackside Signalling<br/>to Issue Unsafe Movement Authorities"):::threat
  T2M0["Feed false position or movement-authority<br/>data into train control to cause<br/>overspeed, collision, or wrong-route<br/>movement"]:::motive
  T2 --> T2M0
  T2M0C0("EuroBalise / Trackside Spot-Transmission<br/>System"):::component
  T2M0 --> T2M0C0
  T2M0C0W0("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T2M0C0 --> T2M0C0W0
  T2M0C0W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T2M0C0 --> T2M0C0W1
  T2M0C1("EuroRadio / ETCS Train-to-Trackside<br/>Messaging"):::component
  T2M0 --> T2M0C1
  T2M0C1W0("CWE-327: Use of a Broken or Risky<br/>Cryptographic Algorithm"):::cwe
  T2M0C1 --> T2M0C1W0
  T2M0C1W1("CWE-294: Authentication Bypass by<br/>Capture-replay"):::cwe
  T2M0C1 --> T2M0C1W1
  T2M0C2("Interlocking and Signalling Control<br/>System"):::component
  T2M0 --> T2M0C2
  T2M0C2W0("CWE-287: Improper Authentication"):::cwe
  T2M0C2 --> T2M0C2W0
  T2M0C2W1("CWE-20: Improper Input Validation"):::cwe
  T2M0C2 --> T2M0C2W1
  T3("Compromise Onboard Train Networking and<br/>Gateway Devices to Pivot into Vehicle<br/>Systems"):::threat
  T3M0["Gain remote code execution on the onboard<br/>train router/gateway to establish<br/>persistence and move toward<br/>control-adjacent networks"]:::motive
  T3 --> T3M0
  T3M0C0("Onboard Train Router / Cellular Gateway"):::component
  T3M0 --> T3M0C0
  T3M0C0W0("CWE-78: Improper Neutralization of<br/>Special Elements used in an OS Command<br/>('OS Command Injection')"):::cwe
  T3M0C0 --> T3M0C0W0
  T3M0C0W1("CWE-287: Improper Authentication"):::cwe
  T3M0C0 --> T3M0C0W1
  T3M0C0W2("CWE-1395: Dependency on Vulnerable<br/>Third-Party Component"):::cwe
  T3M0C0 --> T3M0C0W2
  T3M0C1("Train Control &amp; Monitoring System (TCMS)<br/>Network"):::component
  T3M0 --> T3M0C1
  T3M0C1W0("CWE-923: Improper Restriction of<br/>Communication Channel to Intended<br/>Endpoints"):::cwe
  T3M0C1 --> T3M0C1W0
  T3M0C1W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T3M0C1 --> T3M0C1W1
  T4("Embed Hidden Lockout or Kill-Switch Logic<br/>in Rolling-Stock PLC Firmware"):::threat
  T4M0["Introduce covert conditional logic that<br/>disables rolling stock on a trigger<br/>(geofence, timer, date, or remote<br/>command)"]:::motive
  T4 --> T4M0
  T4M0C0("Rolling-Stock PLC and Vehicle Control<br/>Unit Firmware"):::component
  T4M0 --> T4M0C0
  T4M0C0W0("CWE-912: Hidden Functionality"):::cwe
  T4M0C0 --> T4M0C0W0
  T4M0C0W1("CWE-1242: Inclusion of Undocumented<br/>Features or Chicken Bits"):::cwe
  T4M0C0 --> T4M0C0W1
  T4M0C0W2("CWE-506: Embedded Malicious Code"):::cwe
  T4M0C0 --> T4M0C0W2
  T4M0C1("Firmware Update and Signing Pipeline"):::component
  T4M0 --> T4M0C1
  T4M0C1W0("CWE-1277: Firmware Not Using<br/>Cryptographic Signature"):::cwe
  T4M0C1 --> T4M0C1W0
  T5("Tamper with Level-Crossing, Wayside and<br/>Protection Controllers to Create<br/>Hazardous States"):::threat
  T5M0["Suppress level-crossing warnings or force<br/>unsafe wayside states to endanger road<br/>users and trains"]:::motive
  T5 --> T5M0
  T5M0C0("Level-Crossing Controller and Wayside RTU"):::component
  T5M0 --> T5M0C0
  T5M0C0W0("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T5M0C0 --> T5M0C0W0
  T5M0C0W1("CWE-1390: Weak Authentication"):::cwe
  T5M0C0 --> T5M0C0W1
  T5M0C1("Electrical Protection and Traction Power<br/>SCADA"):::component
  T5M0 --> T5M0C1
  T5M0C1W0("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T5M0C1 --> T5M0C1W0
  T5M0C1W1("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T5M0C1 --> T5M0C1W1
  T6("Disrupt Operations Through a Compromised<br/>Railway SaaS or Third-Party Service<br/>Provider"):::threat
  T6M0["Halt train operations by taking down a<br/>SaaS provider whose availability the<br/>railway silently depends on"]:::motive
  T6 --> T6M0
  T6M0C0("Driver / Crew Operational Mobile<br/>Application (SaaS-backed)"):::component
  T6M0 --> T6M0C0
  T6M0C0W0("CWE-1357: Reliance on Insufficiently<br/>Trustworthy Component"):::cwe
  T6M0C0 --> T6M0C0W0
  T6M0C0W1("CWE-1104: Use of Unmaintained Third Party<br/>Components"):::cwe
  T6M0C0 --> T6M0C0W1
  T6M0C1("Enterprise Asset Management / Maintenance<br/>SaaS"):::component
  T6M0 --> T6M0C1
  T6M0C1W0("CWE-287: Improper Authentication"):::cwe
  T6M0C1 --> T6M0C1W0
  T6M0C1W1("CWE-502: Deserialization of Untrusted<br/>Data"):::cwe
  T6M0C1 --> T6M0C1W1
  T6M1["Use a trusted subcontractor connection to<br/>reach railway networks that are not<br/>directly exposed"]:::motive
  T6 --> T6M1
  T6M1C0("Third-Party / Subcontractor Network<br/>Integration"):::component
  T6M1 --> T6M1C0
  T6M1C0W0("CWE-1357: Reliance on Insufficiently<br/>Trustworthy Component"):::cwe
  T6M1C0 --> T6M1C0W0
  T6M1C0W1("CWE-269: Improper Privilege Management"):::cwe
  T6M1C0 --> T6M1C0W1
  T7("Encrypt Railway Enterprise and<br/>Operational IT for Ransom"):::threat
  T7M0["Encrypt crew, scheduling and planning<br/>systems to force manual operation and<br/>extort payment"]:::motive
  T7 --> T7M0
  T7M0C0("Railway Enterprise IT and Operational<br/>Planning Systems"):::component
  T7M0 --> T7M0C0
  T7M0C0W0("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T7M0C0 --> T7M0C0W0
  T7M0C0W1("CWE-307: Improper Restriction of<br/>Excessive Authentication Attempts"):::cwe
  T7M0C0 --> T7M0C0W1
  T7M0C0W2("CWE-732: Incorrect Permission Assignment<br/>for Critical Resource"):::cwe
  T7M0C0 --> T7M0C0W2
  T7M0C0W3("CWE-693: Protection Mechanism Failure"):::cwe
  T7M0C0 --> T7M0C0W3
  T7M1["Exfiltrate employee and passenger PII for<br/>double-extortion leverage"]:::motive
  T7 --> T7M1
  T7M1C0("HR, Payroll and Customer Record Stores"):::component
  T7M1 --> T7M1C0
  T7M1C0W0("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T7M1C0 --> T7M1C0W0
  T7M1C0W1("CWE-285: Improper Authorization"):::cwe
  T7M1C0 --> T7M1C0W1
  T8("Deploy Destructive Wiper Malware Against<br/>Railway Operational and Information<br/>Systems"):::threat
  T8M0["Destroy railway backend data and systems<br/>to cause prolonged, non-recoverable<br/>disruption"]:::motive
  T8 --> T8M0
  T8M0C0("Railway Backend Servers and Workstations"):::component
  T8M0 --> T8M0C0
  T8M0C0W0("CWE-693: Protection Mechanism Failure"):::cwe
  T8M0C0 --> T8M0C0W0
  T8M0C0W1("CWE-306: Missing Authentication for<br/>Critical Function"):::cwe
  T8M0C0 --> T8M0C0W1
  T8M0C0W2("CWE-269: Improper Privilege Management"):::cwe
  T8M0C0 --> T8M0C0W2
  T9("Compromise the Rolling-Stock and<br/>Signalling Software Supply Chain"):::threat
  T9M0["Implant malicious or backdoored code<br/>upstream so it ships to many operators<br/>through trusted updates"]:::motive
  T9 --> T9M0
  T9M0C0("Supplier Firmware Build and Signing<br/>Environment"):::component
  T9M0 --> T9M0C0
  T9M0C0W0("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T9M0C0 --> T9M0C0W0
  T9M0C0W1("CWE-321: Use of Hard-coded Cryptographic<br/>Key"):::cwe
  T9M0C0 --> T9M0C0W1
  T9M0C1("Third-Party and Open-Source Component<br/>Dependencies"):::component
  T9M0 --> T9M0C1
  T9M0C1W0("CWE-1395: Dependency on Vulnerable<br/>Third-Party Component"):::cwe
  T9M0C1 --> T9M0C1W0
  T9M0C1W1("CWE-829: Inclusion of Functionality from<br/>Untrusted Control Sphere"):::cwe
  T9M0C1 --> T9M0C1W1
  T10("Breach Cloud-Hosted Rail Asset-Management<br/>and Analytics Platforms"):::threat
  T10M0["Access or manipulate fleet-wide<br/>asset-health data in a multi-tenant rail<br/>cloud to enable espionage or induce<br/>unsafe maintenance decisions"]:::motive
  T10 --> T10M0
  T10M0C0("Rail Asset-Management Cloud Platform<br/>(HMAX / Railigent X / HealthHub class)"):::component
  T10M0 --> T10M0C0
  T10M0C0W0("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T10M0C0 --> T10M0C0W0
  T10M0C0W1("CWE-285: Improper Authorization"):::cwe
  T10M0C0 --> T10M0C0W1
  T10M0C0W2("CWE-287: Improper Authentication"):::cwe
  T10M0C0 --> T10M0C0W2
  T10M0C0W3("CWE-778: Insufficient Logging"):::cwe
  T10M0C0 --> T10M0C0W3
  T10M0C1("Cloud Tenant and Identity Configuration"):::component
  T10M0 --> T10M0C1
  T10M0C1W0("CWE-522: Insufficiently Protected<br/>Credentials"):::cwe
  T10M0C1 --> T10M0C1W0
  T10M0C1W1("CWE-668: Exposure of Resource to Wrong<br/>Sphere"):::cwe
  T10M0C1 --> T10M0C1W1
  T11("Hijack Passenger-Facing Digital Services:<br/>Ticketing, PIS and Station Wi-Fi"):::threat
  T11M0["Deny or degrade online ticketing to cause<br/>public disruption and reputational harm"]:::motive
  T11 --> T11M0
  T11M0C0("Online / Mobile Ticketing Platform"):::component
  T11M0 --> T11M0C0
  T11M0C0W0("CWE-1333: Inefficient Regular Expression<br/>Complexity"):::cwe
  T11M0C0 --> T11M0C0W0
  T11M0C0W1("CWE-770: Allocation of Resources Without<br/>Limits or Throttling"):::cwe
  T11M0C0 --> T11M0C0W1
  T11M0C0W2("CWE-1357: Reliance on Insufficiently<br/>Trustworthy Component"):::cwe
  T11M0C0 --> T11M0C0W2
  T11M1["Deface public information channels to<br/>spread propaganda or extremist messaging"]:::motive
  T11 --> T11M1
  T11M1C0("Station Wi-Fi Landing Page and Passenger<br/>Information Displays"):::component
  T11M1 --> T11M1C0
  T11M1C0W0("CWE-287: Improper Authentication"):::cwe
  T11M1C0 --> T11M1C0W0
  T11M1C0W1("CWE-269: Improper Privilege Management"):::cwe
  T11M1C0 --> T11M1C0W1
  T11M1C0W2("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T11M1C0 --> T11M1C0W2
  T12("Poison or Evade AI Perception and<br/>Inspection Models Used in Rail Safety"):::threat
  T12M0["Cause AI perception/inspection models to<br/>miss real hazards or report false ones,<br/>degrading rail safety at scale"]:::motive
  T12 --> T12M0
  T12M0C0("Onboard / Trackside AI Perception and<br/>Inspection Model"):::component
  T12M0 --> T12M0C0
  T12M0C0W0("CWE-1039: Inadequate Detection or<br/>Handling of Adversarial Input<br/>Perturbations in Automated Recognition<br/>Mechanism"):::cwe
  T12M0C0 --> T12M0C0W0
  T12M0C0W1("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T12M0C0 --> T12M0C0W1
  T12M0C0W2("CWE-506: Embedded Malicious Code"):::cwe
  T12M0C0 --> T12M0C0W2
  T12M0C1("AI Training Data and MLOps Pipeline"):::component
  T12M0 --> T12M0C1
  T12M0C1W0("CWE-349: Acceptance of Extraneous<br/>Untrusted Data With Trusted Data"):::cwe
  T12M0C1 --> T12M0C1W0
  T12M0C1W1("CWE-285: Improper Authorization"):::cwe
  T12M0C1 --> T12M0C1W1
  T13("Abuse LLM-Based Rail Assistants and<br/>Agentic Operational Tools"):::threat
  T13M0["Manipulate an operational LLM assistant<br/>via prompt injection to leak data or<br/>drive unsafe actions and recommendations"]:::motive
  T13 --> T13M0
  T13M0C0("LLM Operational Assistant / Maintenance<br/>Copilot"):::component
  T13M0 --> T13M0C0
  T13M0C0W0("CWE-1427: Improper Neutralization of<br/>Input Used for LLM Prompting"):::cwe
  T13M0C0 --> T13M0C0W0
  T13M0C0W1("CWE-1426: Improper Validation of<br/>Generative AI Output"):::cwe
  T13M0C0 --> T13M0C0W1
  T13M0C0W2("CWE-200: Exposure of Sensitive<br/>Information to an Unauthorized Actor"):::cwe
  T13M0C0 --> T13M0C0W2
  T13M0C1("Agentic Tool Connectors and RAG Corpus"):::component
  T13M0 --> T13M0C1
  T13M0C1W0("CWE-349: Acceptance of Extraneous<br/>Untrusted Data With Trusted Data"):::cwe
  T13M0C1 --> T13M0C1W0
  T13M0C1W1("CWE-285: Improper Authorization"):::cwe
  T13M0C1 --> T13M0C1W1
  T14("Spoof or Jam GNSS Positioning Relied On<br/>by Train Location and Operations"):::threat
  T14M0["Feed false position, speed or timing into<br/>train location systems by spoofing or<br/>jamming GNSS"]:::motive
  T14 --> T14M0
  T14M0C0("Onboard GNSS Positioning Receiver"):::component
  T14M0 --> T14M0C0
  T14M0C0W0("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T14M0C0 --> T14M0C0W0
  T14M0C0W1("CWE-290: Authentication Bypass by<br/>Spoofing"):::cwe
  T14M0C0 --> T14M0C0W1
  T14M0C0W2("CWE-807: Reliance on Untrusted Inputs in<br/>a Security Decision"):::cwe
  T14M0C0 --> T14M0C0W2
  T15("Harvest and Abuse Passenger Biometric,<br/>Location and Surveillance Data"):::threat
  T15M0["Exfiltrate or abuse concentrated<br/>passenger biometric, location and<br/>behavioural data for surveillance,<br/>profiling or resale"]:::motive
  T15 --> T15M0
  T15M0C0("AI CCTV and Biometric Analytics Platform"):::component
  T15M0 --> T15M0C0
  T15M0C0W0("CWE-285: Improper Authorization"):::cwe
  T15M0C0 --> T15M0C0W0
  T15M0C0W1("CWE-359: Exposure of Private Personal<br/>Information to an Unauthorized Actor"):::cwe
  T15M0C0 --> T15M0C0W1
  T15M0C1("Passenger Travel-History and App<br/>Telemetry Store"):::component
  T15M0 --> T15M0C1
  T15M0C1W0("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T15M0C1 --> T15M0C1W0
  T15M0C1W1("CWE-1220: Insufficient Granularity of<br/>Access Control"):::cwe
  T15M0C1 --> T15M0C1W1
  T16("Abuse Insider and Remote-Maintenance<br/>Access to Rail Control and OT Networks"):::threat
  T16M0["Leverage privileged maintenance or<br/>remote-vendor access to reach and<br/>manipulate rail control/OT systems"]:::motive
  T16 --> T16M0
  T16M0C0("Remote Maintenance / Vendor Access to OT"):::component
  T16M0 --> T16M0C0
  T16M0C0W0("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T16M0C0 --> T16M0C0W0
  T16M0C0W1("CWE-1391: Use of Weak Credentials"):::cwe
  T16M0C0 --> T16M0C0W1
  T16M0C0W2("CWE-923: Improper Restriction of<br/>Communication Channel to Intended<br/>Endpoints"):::cwe
  T16M0C0 --> T16M0C0W2
  T16M0C0W3("CWE-269: Improper Privilege Management"):::cwe
  T16M0C0 --> T16M0C0W3
  T16M0C1("Transient Cyber Assets and Removable<br/>Media"):::component
  T16M0 --> T16M0C1
  T16M0C1W0("CWE-494: Download of Code Without<br/>Integrity Check"):::cwe
  T16M0C1 --> T16M0C1W0
  T17("Commit Fraud and Account Takeover Against<br/>Ticketing and Loyalty Platforms"):::threat
  T17M0["Take over passenger accounts and defraud<br/>ticketing/loyalty systems for financial<br/>gain"]:::motive
  T17 --> T17M0
  T17M0C0("Ticketing / Fare / Loyalty Web and API<br/>Platform"):::component
  T17M0 --> T17M0C0
  T17M0C0W0("CWE-308: Use of Single-factor<br/>Authentication"):::cwe
  T17M0C0 --> T17M0C0W0
  T17M0C0W1("CWE-307: Improper Restriction of<br/>Excessive Authentication Attempts"):::cwe
  T17M0C0 --> T17M0C0W1
  T17M0C0W2("CWE-285: Improper Authorization"):::cwe
  T17M0C0 --> T17M0C0W2
  T17M0C0W3("CWE-345: Insufficient Verification of<br/>Data Authenticity"):::cwe
  T17M0C0 --> T17M0C0W3
  T17M0C1("Stored Payment and Identity Data"):::component
  T17M0 --> T17M0C1
  T17M0C1W0("CWE-311: Missing Encryption of Sensitive<br/>Data"):::cwe
  T17M0C1 --> T17M0C1W0

  classDef threat fill:firebrick,color:white
  classDef motive fill:indianred,color:white
  classDef component fill:chocolate,color:white
  classDef cwe fill:steelblue,color:white
```

Flowchart generated from [`railway.json`](../railway.json)
