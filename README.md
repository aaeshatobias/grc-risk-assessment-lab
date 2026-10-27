[README.md](https://github.com/user-attachments/files/34030624/README.md)
# GRC Lab: Risk Assessment & Control Gap Analysis

> **One-line summary:** Performed a risk assessment and NIST CSF 2.0 gap analysis for a fictional 50-person medical billing company, with three security policies, a prioritized remediation plan, an audit evidence tracker, and an executive memo.

> **Note:** The company, people, systems, and data in this project are fictional and were invented for learning. The starting conditions (for example, "MFA is on the two IT admin accounts only") are assumptions I wrote, not findings from a real environment.

## Overview
Anita & Daughters is a fictional medical billing firm in Newark, NJ. I inventoried its 18 systems and assets, identified and scored 15 risks, mapped 24 NIST CSF 2.0 controls, and found 21 gaps. I then wrote three policies, built a remediation plan with owners and dates, listed the evidence an auditor would ask for, and summarized the results for the CEO in a one-page memo.

## Skills Demonstrated
- Risk identification, scoring, and prioritization
- Control framework mapping (NIST CSF 2.0)
- Security policy writing
- Gap analysis and remediation planning
- Audit evidence tracking
- Executive-level communication

## Company Profile (Fictional)
- **Name / industry:** Anita & Daughters, medical billing and claims management
- **Size:** 50 employees (26 office, 15 hybrid, 9 remote)
- **Key systems:** Microsoft 365, billing platform, clearinghouse portal, office file server, cloud backup service, VPN, accounting and payroll software, payment processor
- **Data types:** protected health information (PHI), client contracts, payroll data, payment card data, printed claim documents
- **Regulatory drivers:** HIPAA (the firm acts as a business associate for its client practices) and client contract terms
- Full profile: [docs/01-company-profile.md](docs/01-company-profile.md)

## Deliverables
| Deliverable | File |
|-------------|------|
| Asset inventory, risk register, control map, remediation plan, evidence tracker | [docs/risk-assessment.xlsx](docs/risk-assessment.xlsx) (one workbook, one tab for each) |
| Company profile | [docs/01-company-profile.md](docs/01-company-profile.md) |
| Access Control Policy | [docs/policies/access-control-policy.md](docs/policies/access-control-policy.md) |
| Incident Response Policy | [docs/policies/incident-response-policy.md](docs/policies/incident-response-policy.md) |
| Acceptable Use Policy | [docs/policies/acceptable-use-policy.md](docs/policies/acceptable-use-policy.md) |
| Executive memo | [docs/executive-memo.pdf](docs/executive-memo.pdf) |

## Methodology
1. **Scope and assets:** listed 10 systems and 8 supporting assets, each with an owner, the data it holds, a classification, and a 1 to 5 criticality score.
2. **Starting conditions:** wrote 18 numbered assumptions (S-01 to S-18) describing how the firm works today, so every finding traces to a stated fact.
3. **Threats and vulnerabilities:** for each risk, named the threat and the weakness that lets it happen.
4. **Scoring:** Likelihood (1 to 5) x Impact (1 to 5), giving a score of 1 to 25. Ratings: Low 1 to 4, Medium 5 to 9, High 10 to 16, Critical 17 to 25.
5. **Control mapping:** mapped 24 NIST CSF 2.0 subcategories to the risks and marked each Implemented, Partial, or Missing.
6. **Gaps and priorities:** each Partial or Missing control became a gap (21 in total). Priority follows the highest linked risk: P1 is Critical, P2 is High, P3 is Medium or Low.
7. **Policies, remediation, and evidence:** wrote policies that close gaps, a plan with owners, dates, and success measures, and a tracker of the proof an auditor would ask for.

## Risk Register Results
**Scoring scale:** Likelihood 1 to 5 x Impact 1 to 5

| Rating | Count |
|--------|-------|
| Critical | 2 |
| High | 7 |
| Medium | 5 |
| Low | 1 |
| **Total** | **15** |

Top risks:

| ID | Asset | Threat | Likelihood | Impact | Score | Owner | Treatment |
|----|-------|--------|-----------|--------|-------|-------|-----------|
| R-01 | Staff user accounts | Phishing | 5 | 4 | 20 (Critical) | IT Manager | Mitigate |
| R-02 | Office file server | Ransomware | 4 | 5 | 20 (Critical) | IT Manager | Mitigate |
| R-05 | VPN | Password guessing and credential stuffing | 4 | 4 | 16 (High) | IT Manager | Mitigate |
| R-03 | Cloud backup service | Failed backup, ransomware, or deletion | 3 | 5 | 15 (High) | IT Manager | Mitigate |
| R-10 | Billing platform | Any incident, with no response plan | 3 | 4 | 12 (High) | Compliance and Privacy Officer | Mitigate |

The full register of 15 risks is on the Risk Register tab.

## Control Mapping (NIST CSF 2.0)
24 controls reviewed: **3 Implemented, 10 Partial, 11 Missing.**

| CSF Function | Controls reviewed | Implemented | Partial | Missing | Example gap |
|--------------|-------------------|-------------|---------|---------|-------------|
| Govern | 3 | 0 | 1 | 2 | GV.PO-01: no written security policies |
| Identify | 4 | 3 | 1 | 0 | ID.RA-01: no routine vulnerability scanning |
| Protect | 11 | 0 | 8 | 3 | PR.AA-03: MFA on the 2 IT admin accounts only |
| Detect | 2 | 0 | 0 | 2 | DE.CM-03: no one reviews sign-in logs |
| Respond | 2 | 0 | 0 | 2 | RS.MA-01: no written incident response plan |
| Recover | 2 | 0 | 0 | 2 | RC.RP-03: restores never tested |

## Policies Written
- [Access Control Policy](docs/policies/access-control-policy.md): 11 numbered rules (AC-1 to AC-11)
- [Incident Response Policy](docs/policies/incident-response-policy.md): 14 numbered rules (IR-1 to IR-14)
- [Acceptable Use Policy](docs/policies/acceptable-use-policy.md): 12 numbered rules (AU-1 to AU-12)

Every rule names the NIST control it supports and the risk it reduces.

## Remediation Plan
21 actions: 6 at P1, 11 at P2, 4 at P3. The first six:

| Priority | Action | Owner | Target Date | Evidence of Completion |
|----------|--------|-------|-------------|------------------------|
| P1 | Turn on MFA for all staff accounts and the VPN | IT Manager | 2026-12-15 | 100% of accounts show MFA registered in the sign-in report |
| P1 | Train all staff in English and Thai, with a phishing test | Compliance and Privacy Officer | 2026-12-18 | 50 of 50 staff trained, records kept |
| P1 | Test restoring from backup and stop sharing the console password | IT Manager | 2026-11-30 | Restore test record; 0 shared accounts |
| P1 | Patch the file server monthly; automatic updates on laptops | IT Manager | 2026-12-31 | Patch log; 0 critical updates older than 30 days |
| P1 | Scan for weaknesses quarterly and fix serious findings | IT Manager | 2027-01-15 | First scan report on file |
| P1 | Put all laptops under central management | IT Manager | 2027-01-29 | 50 of 50 devices in the console |

The full plan is on the Remediation Plan tab.

## Audit Evidence Tracker (excerpt)
| Control | Evidence Needed | Source / Owner | Status |
|---------|-----------------|----------------|--------|
| PR.AA-03 | Sign-in report showing MFA registered for every user | IT / Access Evidence, IT Manager | Partial |
| PR.AA-05 | Quarterly access review signed by each manager; leaver tickets; contracts folder permissions | Compliance / Access Reviews, HR Manager | Missing |
| PR.DS-11 | Backup job reports; restore test records | IT / Backups, IT Manager | Partial |
| ID.AM-02 | Current asset inventory with an owner and review date | Compliance / Risk Assessment, IT Manager | Available |

All 24 controls are on the Evidence Tracker tab.

## Key Findings
- Two Critical risks, staff phishing and file-server ransomware, can both be reduced a lot by turning on MFA, patching, and training.
- Backups run every night but have never been tested, so recovery is unproven.
- Leavers are removed only when a manager emails IT, and no one reviews access, so a former employee could keep access.
- The firm has no written incident plan, so it could miss a breach notice deadline to a client.
- The 2-person IT team owns 11 of the 21 actions, so the plan's dates depend on extra help.
- Read the one-page summary: [docs/executive-memo.pdf](docs/executive-memo.pdf)

## Lessons Learned
- Writing the starting conditions down first made every later step easy to check, because each risk and control traces back to a numbered assumption.
- A policy is only useful if each rule is specific and checkable ("must", who, and when). Vague words like "appropriate" cannot be audited.
- A risk register, control map, plan, and evidence tracker work best as one linked set. Pulling status and owners by formula kept the tabs from disagreeing.
- Looking at who owns the work showed a capacity problem that the risk scores alone did not.

## Limitations
- Everything is fictional. The scores and starting conditions are my assumptions, not measurements.
- No real systems were tested or scanned.
- The breach notice timing in the Incident Response Policy should be confirmed with an attorney and each client contract before real use.

## Next Improvements
- Add a vendor risk assessment for the four third parties.
- Add a business continuity plan and a tabletop exercise script.
- Add the CIS Controls as a second framework mapping.

## Repo Structure
```
README.md
docs/
  01-company-profile.md
  risk-assessment.xlsx
  executive-memo.pdf
  policies/
    access-control-policy.md
    incident-response-policy.md
    acceptable-use-policy.md
```
