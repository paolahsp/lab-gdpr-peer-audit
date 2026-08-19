# MIRA GDPR Peer Audit Report

**Auditor:** Paola Hintze · **Builder:** Maria Cavali · **Date:** 19 August 2026  
**Scope:** MIRA V4, with V3 shared-platform dependencies considered where relevant

## Section 1 — System summary

MIRA is a private, authenticated web application that helps an individual founder, creator, or consultant develop creative direction and a five-image moodboard. It collects account/session data, creative and recognition answers, a structured brief, birth details, and optionally an inspiration image and explanation. Forge-based language and image services generate adaptive questions, a stored Creative DNA profile, visual directions, and refined assets; MySQL/TiDB and S3-backed storage retain records and images. Human users select and refine creative outputs, while production hosting, vendor regions, retention, deletion operations, and the final operating entity remain unconfirmed.

## Section 2 — Data and role map

The dataset includes identifiers, session data, free text, birth details, images, generated profiles/inferences, outputs, and operational metadata. Birth data is not inherently Article 9 data, and a face image is not automatically biometric special-category data; however, free text, images, and AI inferences may reveal Article 9 information. The final MIRA operator is provisionally the controller. Manus OAuth/platform, Forge, database hosting, object storage, and enabled integrations are processors or subprocessors where they act only on its instructions; Maria/the build team is not automatically a processor unless a separate entity handles data for the controller.

Vendor entities, regions, DPAs and transfer safeguards are not evidenced. Any EEA export therefore requires mapping and a valid GDPR Chapter V mechanism; EU–U.S. DPF reliance is valid only for the certified recipient, otherwise SCCs plus a transfer impact assessment and supplementary measures may be required. See the [GDPR text](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng) and the Commission's [adequacy guidance](https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/adequacy-decisions_en).

## Section 3 — Compliance findings

> **Finding 1 — Purpose-specific lawful bases and sensitive-data controls**  
> **Severity:** Blocking  
> **Description:** Articles 5, 6 and 9 require a defined purpose and lawful basis for each activity, plus an Article 9 condition where special-category data is processed. Article 6(1)(b) may cover data objectively necessary to deliver the requested creative service, but it does not automatically cover optional images, unused birth data, analytics, support reuse, or model improvement. The brief does not evidence the required purpose/basis map or a control for sensitive information volunteered or inferred in free text/images.  
> **Recommended action:** Create a processing-purpose register. Minimise or remove birth data from V4 unless necessary; separate optional processing and obtain valid consent where appropriate; prevent unsupported secondary use; and define how Article 9 content is detected, avoided, deleted, or processed under a valid condition.  
> **Escalation needed?** Yes — controller, privacy counsel/DPO, and product owner.

> **Finding 2 — DPIA before production**  
> **Severity:** Blocking  
> **Description:** Article 35 requires a DPIA before processing likely to create high risk. MIRA combines systematic profiling/evaluation, innovative generative AI, free text and images capable of revealing sensitive data, multiple service providers, and uncertain transfers. No DPIA is evidenced. EDPB-endorsed guidance supports assessing these criteria cumulatively.  
> **Recommended action:** Complete and approve a DPIA covering necessity/proportionality, data subjects, model/vendor flows, sensitive inferences, security, transfers, retention, rights and mitigations. Consult the supervisory authority under Article 36 if high residual risk remains.  
> **Escalation needed?** Yes — controller, DPO/privacy counsel, security and engineering.

> **Finding 3 — Processor governance and DPAs**  
> **Severity:** Blocking  
> **Description:** Article 28 contracts are required before a processor handles personal data. The brief names several services but does not evidence their legal entities, instructions, subprocessors, audit/security terms, deletion duties, or signed DPAs. Because those services already support the private staging environment, this is treated as blocking unless the controller verifies that compliant agreements are already in place.  
> **Recommended action:** Build a vendor register, classify each role, obtain Article 28 terms, approve subprocessors, document security due diligence, and disable any vendor that cannot meet requirements.  
> **Escalation needed?** Yes — controller, procurement/privacy counsel and security.

> **Finding 4 — International transfers**  
> **Severity:** Significant  
> **Description:** Processor regions and transfer mechanisms are unknown. Articles 44–49 require a documented mechanism for every restricted transfer; a DPA alone is insufficient.  
> **Recommended action:** Map data location and remote access by vendor and subprocessor. Record adequacy/DPF status or execute SCCs, complete a transfer impact assessment, and implement supplementary measures before the affected flow.  
> **Escalation needed?** Yes — privacy counsel/DPO and vendor owners.

> **Finding 5 — Transparency, retention and rights operations**  
> **Severity:** Significant  
> **Description:** The brief does not evidence an Articles 13–14 notice explaining AI profiling, recipients, transfers, retention, legal bases, or rights. Retention/deletion across database, S3, logs, backups and vendors is not confirmed, nor is an auditable rights-request workflow.  
> **Recommended action:** Publish a layered privacy notice; adopt a data-by-system retention schedule; implement account deletion and vendor deletion propagation; and test access, correction, deletion, restriction, portability and objection workflows against Article 12 deadlines.  
> **Escalation needed?** Yes — controller, product/engineering and privacy lead.

## Section 4 — Specific GDPR obligations checklist

| Obligation | Assessment | Note |
|---|---|---|
| Lawful basis identified for each processing purpose | **Gap identified** | No purpose-by-purpose record is evidenced. |
| Purpose limitation respected | **Cannot determine from brief** | Improvement/analytics reuse is unspecified. |
| Data minimisation | **Gap identified** | V4 retains birth data not used by current output. |
| Roles mapped and DPAs in place | **Cannot determine from brief** | Provisional roles are mapped; contracts are not evidenced. |
| International transfer mechanism documented | **Gap identified** | Regions and Chapter V mechanisms are unknown. |
| DPIA conducted if required | **Gap identified** | Full DPIA recommended before production; none evidenced. |
| Article 22 safeguard if significant automated decisions occur | **Appears met / not currently applicable** | Human creative selection exists; no legal or similarly significant decision is described. Reassess if purpose changes. |
| Privacy notice covers AI processing | **Cannot determine from brief** | Notice not provided. |
| Data-subject rights operational within deadlines | **Cannot determine from brief** | Workflow and deletion propagation not demonstrated. |

## Section 5 — Overall recommendation

**Do not proceed with production personal-data processing.** The lawful-basis map, DPIA and processor contracts are prerequisites, and their absence would block lawful processing. Production may be reconsidered once these are approved and the vendor/transfer map, privacy notice, retention schedule, deletion propagation, security controls and rights workflow are evidenced and tested. Development may continue with synthetic or irreversibly anonymised data that does not constitute personal data.

## Section 6 — What this report is not

This report is not a legal opinion, a DPIA, or a certification of compliance. It is a first-pass independent review based on the supplied brief; the controller should verify the facts and obtain qualified legal review before relying on it or processing EU personal data in production.
