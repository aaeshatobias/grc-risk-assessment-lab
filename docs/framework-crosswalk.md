# Framework Crosswalk: NIST CSF 2.0 to NIST SP 800-53 Rev. 5, SOC 2, and ISO/IEC 27001:2022

**Project:** GRC Risk Assessment and Control Gap Analysis for Anita & Daughters, a fictional 50-person medical billing firm and HIPAA business associate.

**Files:** `framework-crosswalk.md` (this page) and `framework-crosswalk.csv` (the same data in a sortable table).

## Why this crosswalk exists

The original assessment mapped the firm against NIST CSF 2.0. Real organizations rarely answer to one framework:

- Client medical practices may ask for a **SOC 2** report.
- Larger clients and partners may ask about **ISO 27001**.
- Federal and federally funded work points to **NIST SP 800-53**.

This crosswalk shows that the same 24 controls and 21 gaps line up across all four frameworks. Fixing a gap once can close it everywhere.

## Summary

| Measure | Count |
|---|---|
| NIST CSF 2.0 subcategories assessed | 24 (3 Implemented, 10 Partial, 11 Missing) |
| Gaps (Partial + Missing) | 21 |
| NIST SP 800-53 Rev. 5 controls and enhancements mapped | 56 (50 linked to gaps) |
| SOC 2 Trust Services Criteria mapped | 24 (22 linked to gaps) |
| ISO/IEC 27001:2022 Annex A controls mapped | 32 (30 linked to gaps) |

## Key findings

1. **The gaps cluster in two SOC 2 areas.** CC7 (system operations: vulnerability management, monitoring, incident response, recovery) is touched by 8 gaps and CC6 (logical and physical access) by 6. A SOC 2 readiness effort for this firm would start there.
2. **Most gaps fall in four 800-53 families.** The gaps trace most often to AC (Access Control), IA (Identification and Authentication), IR (Incident Response), and CP (Contingency Planning). The firm's weak points are identity, incident handling, and recovery, not exotic technical controls.
3. **One fix can satisfy several frameworks.** For example, MFA for all staff and the VPN (GAP-01) closes CSF PR.AA-03, 800-53 IA-2(2), SOC 2 CC6.1 and CC6.6, and ISO 8.5 at the same time.
4. **The enhancement level shows the precise gap.** The firm meets 800-53 IA-2(1) (MFA for privileged accounts: the 2 IT admins) but not IA-2(2) (MFA for non-privileged accounts: the 50 staff). The same split shows up in the CSF assessment as Partial.

## The crosswalk

> **Status** is the fictional firm's control status from the original assessment (Implemented, Partial, or Missing), not the status of the mapping. Every one of the 24 controls is mapped.

### Govern

| CSF 2.0 | What it means | Status | 800-53 Rev. 5 | SOC 2 | ISO 27001:2022 |
|---|---|---|---|---|---|
| GV.RR-02 | Someone is named responsible for cybersecurity risk, and everyone knows who | Partial | PM-2, PM-29, PS-9 | CC1.3 | 5.2 |
| GV.PO-01 | The company has a written policy for managing cybersecurity risk | Missing | PM-1, AC-1, IR-1, PL-4 | CC5.3 | 5.1, 5.10 |
| GV.SC-05 | Vendors must meet security requirements, and those requirements are written into contracts | Missing | SA-4, SA-9, SR-6 | CC9.2 | 5.19, 5.20 |

### Identify

| CSF 2.0 | What it means | Status | 800-53 Rev. 5 | SOC 2 | ISO 27001:2022 |
|---|---|---|---|---|---|
| ID.AM-02 | The company keeps a list of its software, services, and systems | Implemented | CM-8, PM-5 | CC6.1 | 5.9 |
| ID.AM-05 | Assets are ranked by how sensitive and how important they are | Implemented | RA-2, RA-9 | CC3.2, C1.1 | 5.12 |
| ID.RA-01 | Weaknesses in systems are found and written down | Partial | RA-5, CA-7 | CC7.1 | 8.8 |
| ID.RA-05 | Threats, weaknesses, likelihood, and impact are used to rank risks | Implemented | RA-3, PM-9 | CC3.2 | Clause 6.1.2, Clause 8.2 |

### Protect

| CSF 2.0 | What it means | Status | 800-53 Rev. 5 | SOC 2 | ISO 27001:2022 |
|---|---|---|---|---|---|
| PR.AA-01 | Each person, service, and device has its own managed identity and credentials | Partial | AC-2, IA-2, IA-4, IA-5 | CC6.1, CC6.2 | 5.16, 5.17 |
| PR.AA-03 | Users, services, and hardware prove who they are before getting access | Partial | IA-2(1), IA-2(2), AC-17 | CC6.1, CC6.6 | 8.5 |
| PR.AA-05 | Access is defined in a policy, limited to what each job needs, and reviewed | Missing | AC-2, AC-6, PS-4, PS-5 | CC6.2, CC6.3 | 5.15, 5.18 |
| PR.AA-06 | Physical access to offices, devices, and paper records is controlled | Partial | PE-3, MP-4, MP-6 | CC6.4, CC6.5, C1.2 | 7.2, 7.7, 7.10 |
| PR.AT-01 | Staff get security awareness and training that fits their jobs | Partial | AT-2, AT-2(1), AT-2(3) | CC1.4, CC2.2 | 6.3 |
| PR.AT-02 | People in specialized roles get training that fits their risks | Missing | AT-3 | CC1.4 | 6.3 |
| PR.DS-01 | Stored data is protected, for example by encryption | Partial | SC-28(1), AC-19(5), SC-12 | CC6.1, CC6.7 | 8.1, 8.24 |
| PR.DS-11 | Backups are created, protected, and tested | Partial | CP-9, CP-9(1) | A1.2, A1.3 | 8.13 |
| PR.PS-01 | Systems are set up in a standard, managed way | Missing | CM-2, CM-6, CM-7 | CC7.1 | 8.1, 8.9 |
| PR.PS-02 | Software is kept up to date and old software is retired | Partial | SI-2, SA-22 | CC7.1, CC8.1 | 8.8, 8.19 |
| PR.IR-01 | Networks are protected from unauthorized access | Partial | SC-7, AC-17 | CC6.6 | 8.20 |

### Detect

| CSF 2.0 | What it means | Status | 800-53 Rev. 5 | SOC 2 | ISO 27001:2022 |
|---|---|---|---|---|---|
| DE.CM-03 | Staff activity and technology use are watched for signs of trouble | Missing | AU-6, SI-4, AC-2(12) | CC7.2 | 8.15, 8.16 |
| DE.AE-02 | Suspicious events are analyzed to understand what is happening | Missing | AU-6, SI-4, IR-4 | CC7.3 | 5.25 |

### Respond

| CSF 2.0 | What it means | Status | 800-53 Rev. 5 | SOC 2 | ISO 27001:2022 |
|---|---|---|---|---|---|
| RS.MA-01 | The incident response plan is carried out once an incident is declared | Missing | IR-4, IR-8, IR-3 | CC7.4 | 5.24, 5.26 |
| RS.CO-02 | The right people inside and outside the company are told about incidents | Missing | IR-6 | CC7.4, CC2.3 | 5.5, 5.26, 6.8 |

### Recover

| CSF 2.0 | What it means | Status | 800-53 Rev. 5 | SOC 2 | ISO 27001:2022 |
|---|---|---|---|---|---|
| RC.RP-01 | Recovery steps are carried out once recovery starts | Missing | CP-2, CP-10 | CC7.5 | 5.29, 5.30 |
| RC.RP-03 | Backups are checked for integrity before they are used to restore | Missing | CP-9(1), CP-4 | A1.3 | 8.13 |

## Why each mapping holds

The label in parentheses is the firm's control status, not the mapping's.

- **GV.RR-02** (Partial): All three require named, written ownership of security and risk. PM-2 names a security program lead, PS-9 puts security duties in position descriptions, and SOC 2 CC1.3 asks for defined authorities and reporting lines. The firm has only an informal COO contact.
- **GV.PO-01** (Missing): Each 800-53 family starts with a '-1' policy control. Your three Phase 5 policies line up with AC-1 (access control), IR-1 (incident response), and PL-4 Rules of Behavior (acceptable use). ISO 5.10 is the acceptable use control.
- **GV.SC-05** (Missing): Security requirements belong in supplier contracts (SA-4, ISO 5.20) and suppliers should be assessed (SR-6, CC9.2). The help desk contract has no security terms and the processor attestation is missing.
- **ID.AM-02** (Implemented): Asset inventory. CM-8 is the system component inventory, and SOC 2 CC6.1 includes identifying and managing the inventory of information assets. Your Assets tab satisfies this.
- **ID.AM-05** (Implemented): Classification and criticality. RA-2 is security categorization and RA-9 is criticality analysis, matching your classification column and 1-5 criticality score.
- **ID.RA-01** (Partial): Vulnerability identification. RA-5 is vulnerability monitoring and scanning, and SOC 2 CC7.1 covers detecting newly discovered vulnerabilities. No routine scanning is the gap.
- **ID.RA-05** (Implemented): Risk assessment itself. RA-3 is the risk assessment control and CC3.2 asks the entity to identify and analyze risk. In ISO this sits in the main clauses, not Annex A. Your 5x5 Risk Register satisfies this.
- **PR.AA-01** (Partial): Unique identities. IA-2 requires each user to be uniquely identified, so the shared clearinghouse login and shared backup console password both fail it.
- **PR.AA-03** (Partial): MFA. IA-2(1) is MFA for privileged accounts and IA-2(2) is MFA for non-privileged accounts, so the firm meets IA-2(1) (2 admins) but not IA-2(2) (50 staff). AC-17 and CC6.6 cover remote access, which is the password-only VPN.
- **PR.AA-05** (Missing): Least privilege and access reviews. AC-6 is least privilege, AC-2 includes periodic account review, PS-4 and PS-5 cover leavers and movers, and CC6.2 and CC6.3 cover provisioning, modifying, and removing access.
- **PR.AA-06** (Partial): Physical access, including paper. In 800-53, 'media' includes paper, so unlocked cabinets fall under MP-4 (media storage) and the monthly shred bin under MP-6 (sanitization). ISO 7.7 is clear desk.
- **PR.AT-01** (Partial): Awareness training. AT-2(1) is practical exercises such as phishing simulations and AT-2(3) is social engineering awareness. Both match GAP-02.
- **PR.AT-02** (Missing): Role-based training. AT-3 covers training for specialized roles, here payroll staff who must spot fake bank-detail change requests.
- **PR.DS-01** (Partial): Encryption at rest. AC-19(5) is full-device encryption for mobile devices like laptops, SC-28(1) is cryptographic protection of stored data, and SC-12 covers the recovery keys in GAP-11.
- **PR.DS-11** (Partial): Backups. CP-9 is system backup and CP-9(1) is testing backups for reliability and integrity. SOC 2 A1.x applies only if the Availability category is in scope.
- **PR.PS-01** (Missing): Standard configurations. CM-2 is the baseline configuration, CM-6 the settings, and CM-7 least functionality. CC7.1 asks for defined configuration standards, and central device management (GAP-04) is how you enforce them.
- **PR.PS-02** (Partial): Patching. SI-2 is flaw remediation and SA-22 covers unsupported software. SOC 2 treats patches as changes under CC8.1.
- **PR.IR-01** (Partial): Network protection. SC-7 is boundary protection (the default-config firewall), AC-17 is remote access (the VPN), and CC6.6 covers access from outside system boundaries.
- **DE.CM-03** (Missing): Monitoring. AU-6 is audit record review, SI-4 is system monitoring, and AC-2(12) is monitoring accounts for unusual use. Nobody reviews Microsoft 365 sign-in logs.
- **DE.AE-02** (Missing): Event analysis. CC7.3 and ISO 5.25 both ask the organization to evaluate events and decide whether they are incidents. There is no process for that today.
- **RS.MA-01** (Missing): Incident response. IR-8 is the written plan, IR-4 is incident handling, and IR-3 is testing it, which matches the practice drill in GAP-15.
- **RS.CO-02** (Missing): Notification. IR-6 is incident reporting and CC2.3 covers communicating with external parties. As a HIPAA business associate, the firm must also notify each covered entity of a breach under 45 CFR 164.410.
- **RC.RP-01** (Missing): Recovery. CP-2 is the contingency plan and CP-10 is system recovery. CC7.5 asks for recovery activities after incidents. GAP-09's runbook is the fix.
- **RC.RP-03** (Missing): Backup integrity before restore. CP-9(1) tests backups for integrity, CP-4 tests the contingency plan, and A1.3 includes testing the integrity and completeness of backup data.

## How to read the identifiers

- **NIST SP 800-53 Rev. 5:** controls are written as family plus number (AC-2 = Access Control, control 2). A number in parentheses is an enhancement, a stronger or more specific version of the base control: IA-2(1) is MFA for privileged accounts.
- **SOC 2 Trust Services Criteria (2017, with revised points of focus, 2022):** CC = Common Criteria (Security), which apply to every SOC 2 report. A1 = Availability and C1 = Confidentiality, which apply only if the firm puts those categories in scope.
- **ISO/IEC 27001:2022:** numbers are Annex A controls in four themes: 5 Organizational, 6 People, 7 Physical, 8 Technological. Risk assessment (ID.RA-05) is a requirement in the main body of the standard (Clauses 6.1.2 and 8.2), not an Annex A control.

## Method and limits

- **Source:** the 24 subcategories, statuses, and risk links come from the Control Map tab of `risk-assessment.xlsx`. The crosswalk does not change any status.
- **Selection:** each row lists the primary related controls, chosen by reading each subcategory's outcome against the control text. It is not an exhaustive list.
- **Official references:** NIST publishes official informative references from CSF 2.0 to SP 800-53 in its Cybersecurity and Privacy Reference Tool (CPRT). The SOC 2 and ISO mappings are interpretive, and an auditor may scope them differently.
- **Learning project:** this is a portfolio exercise on a fictional company and has not been reviewed by an auditor.
