# MIRA GDPR Peer Audit — Debrief and Remediation Plan

**Participants:** Paola Hintze (auditor) and Maria Cavali (builder)  
**Status:** Complete. Maria accepted all five findings with qualifications and approved the joint closing note.

## Phase 5 — Debrief record

### 1. Auditor presents

Paola will present the report without interruption. The independent conclusion is **Do not proceed with production personal-data processing** until three blocking prerequisites are evidenced: (1) a purpose-specific lawful-basis and Article 9 control map, (2) a completed DPIA, and (3) Article 28 processor agreements. The other priority gaps are international-transfer documentation, data minimisation—especially unused V4 birth details—and operational transparency, retention, deletion, and data-subject rights.

### 2. Builder responds

Maria confirmed that she selected Article 6(1)(b) contract for the core V4 service because the processing is necessary to provide the personalised creative direction requested by the user. She also selected contract for optional inspiration/personal reference images when a user chooses that feature, and provisionally for stored birth details, while flagging that the necessity of exact birth time and city and the retention period remain to be tested. She did not conclude that MIRA intentionally processes Article 9 data, but acknowledged that free text, photographs, and Creative DNA inferences could incidentally reveal sensitive information and would require legal review of the relevant Article 9 condition.

On the DPIA, Maria concluded that one is strongly recommended before launch, while treating strict Article 35 necessity as unresolved until scale, geography, model behaviour, and relevant supervisory-authority guidance are confirmed. Her identified criteria were evaluation/scoring through Creative DNA, innovative AI, and potentially highly personal or sensitive data. She requested the external findings so she can state which she accepts, challenges, or believes are already addressed but under-documented.

### 3. Compare lawful-basis selections

- **Paola's independent selection:** Article 6(1)(b) may support core processing that is objectively necessary to provide the user-requested creative-direction service. Account security may also use Article 6(1)(f), subject to a documented legitimate-interests assessment where relied upon. Optional inspiration images, currently unnecessary birth data, analytics, support reuse, and model improvement each require separate necessity and lawful-basis analysis. If MIRA intentionally processes Article 9 data, it also needs an Article 9 condition; explicit consent under Article 9(2)(a) may be appropriate for a truly optional use, but avoidance/minimisation is preferable.
- **Maria's self-audit selection:** Article 6(1)(b) for the core service, user-selected inspiration/reference images, and provisionally the stored birth details. No intentional Article 9 processing was identified, although incidental disclosure or inference was flagged for legal review.
- **Agreement or difference and why:** We agree that Article 6(1)(b) is the strongest candidate for data objectively necessary to provide the core V4 service. We also agree that birth-field necessity, retention, and incidental Article 9 data require further analysis. We differ on optional images: selecting a feature does not by itself make all related processing objectively necessary for the contract, so the exact service promise and necessity test must be documented; consent may be more appropriate if the feature is genuinely optional. Maria's provisional contract basis for exact birth time/city remains unsupported until those fields are shown to be necessary.

### 4. Compare DPIA conclusions

- **Paola's independent conclusion:** Complete a full DPIA before production because MIRA combines several EDPB risk indicators: evaluation/profiling, innovative AI, potentially sensitive or highly personal content, images, multiple vendors, and uncertain cross-border flows. Article 22 does not currently appear to apply because the described creative outputs do not make solely automated decisions with legal or similarly significant effects.
- **Maria's self-audit conclusion:** A DPIA is strongly recommended before launch, but strict Article 35 necessity is TBD pending scale, geography, model behaviour, and supervisory-authority guidance.
- **Agreed conclusion or precise unresolved ambiguity:** We agree on the relevant risk indicators and on completing the DPIA before launch as the practical action. The remaining legal-characterisation difference is whether Article 35 already makes it mandatory: Paola's audit says the combined indicators make high risk sufficiently likely; Maria reserves that conclusion until the missing deployment facts and applicable authority list are confirmed. This distinction does not change the operational launch condition: the DPIA should be completed before production personal-data processing.

### 5. Compare gap lists

| Comparison | Result |
|---|---|
| External audit's top gaps | Lawful-basis/Article 9 map; DPIA; DPAs/vendor governance; transfers; minimisation; notice/retention/rights operations |
| Builder self-audit gaps not caught externally | The builder audit gave more detail on third-party image permissions, access-export friction and provenance, rectification of inferred attributes, security-log lawful basis, cookies/ePrivacy, possible vendor independent-controller roles, and limited Data Act relevance. |
| External gaps the builder had not identified | The external audit applied a firmer production boundary, questioned whether optional images satisfy contractual necessity, treated exact V4 birth details as a minimisation issue because they do not drive the current output, and treated missing Article 28 evidence as blocking unless verified. |
| Factual corrections to the external audit | Maria clarified her selected bases and DPIA position. Her audit expanded the hypothetical processing inventory but supplied no contradictory architecture facts. |

### 6. Joint closing note

> We agreed that contract is the strongest candidate for the core service and that a DPIA should be completed before launch, while we differed on whether optional images are contractually necessary and whether Article 35 already makes the DPIA mandatory. The comparison showed that self-audits benefit from implementation context, while external audits make undocumented assumptions—especially around vendors, transfers, retention, and deletion—more visible; the hardest gaps to catch in one's own work are often controls that feel implicit but are not yet evidenced or testable.

**Approved by Paola Hintze and Maria Cavali.**

## External findings presented to Maria

Paola presented these external findings for direct comparison:

1. **Purpose-specific lawful bases and Article 9 controls — Blocking.** The core contract basis may be appropriate, but optional images, birth details, secondary use, and incidental sensitive data need their own necessity/basis analysis and controls.
2. **DPIA before production — Blocking.** The external audit treats the combined risk indicators as sufficient to require an Article 35 DPIA before processing production personal data.
3. **Processor governance and DPAs — Blocking unless existing agreements are evidenced.** Legal entities, processor terms, subprocessors, security obligations, and deletion duties were not documented in the brief.
4. **International transfers — Significant.** Vendor regions and Chapter V mechanisms were not documented; DPF/adequacy or SCCs plus a transfer impact assessment must be verified as applicable.
5. **Transparency, retention, deletion, and rights operations — Significant.** The brief did not evidence a complete AI privacy notice, retention schedule, deletion propagation, or tested data-subject-rights workflow.

### Builder response to the external findings

Maria accepted all five findings, with two qualifications:

| External finding | Maria's response |
| --- | --- |
| 1. Purpose-specific lawful bases and Article 9 controls | **Accepted.** Contract is strongest for the core service, while necessity for optional images and exact birth details still needs to be demonstrated. Article 9 data are not intentionally collected but may be revealed or inferred, so appropriate controls remain necessary. |
| 2. DPIA before production | **Accepted as the operational condition.** Maria agrees that a DPIA should be completed before production, while retaining her self-audit qualification that strict legal necessity under Article 35 remains TBD pending further evidence and legal review. |
| 3. Processor governance and DPAs | **Accepted.** This may partly be an evidence/documentation gap, but it must be resolved before production if compliant agreements are not already in place. |
| 4. International transfers | **Accepted.** Vendor regions and applicable transfer mechanisms still need to be verified and documented. |
| 5. Transparency, retention, deletion, and rights operations | **Accepted.** Some controls may exist technically, but they are not yet sufficiently documented or tested as compliance evidence. |

Maria also confirmed that the joint note accurately reflects both the implementation knowledge available in a self-audit and the evidence gaps surfaced by an external reviewer.

## Peer review of Maria's recommendation memo

| Criterion | Score 1–3 | Comment |
| --- | ---: | --- |
| Clear bottom-line recommendation | 3 | The **GO WITH CONDITIONS** recommendation is explicit and consistently supported. The memo clearly explains that MIRA may continue toward launch only after the missing privacy, vendor, transfer, retention, and rights controls are evidenced. |
| Lawful basis selection is justified | 2 | Contract under Article 6(1)(b) is well justified for the core personalised creative-direction service, and legitimate interests for proportionate security logging is appropriately limited. However, the contract basis for optional reference images and exact birth details still depends on demonstrating objective necessity. User choice alone does not establish contractual necessity, so consent or removal/minimisation may be more appropriate if those features are genuinely optional. |
| Top actions are specific and sequenced | 3 | The three actions are practical and well ordered: complete the processing blueprint and privacy notice, close vendor and international-transfer gaps, and then conduct and operationalise the DPIA with access and deletion tests. Each action identifies concrete evidence and implementation work. |
| Residual risks are named honestly | 3 | The memo clearly acknowledges incidental sensitive information, unwanted AI inferences, imperfect deletion across subprocessors and backups, and changing transfer or subprocessor arrangements. It does not overstate compliance or pretend unresolved information is already known. |
| Law stacking is addressed (AI Act / ePrivacy) | 3 | The memo correctly distinguishes GDPR from the AI Act transparency assessment and also considers ePrivacy rules for cookies, SDKs, and device access. The Data Act is discussed conservatively without claiming it applies merely because MIRA uses cloud infrastructure. |

**Total: 14/15**

### Client response

I accept the overall recommendation and the three proposed actions. I would clarify that **GO WITH CONDITIONS** should not be interpreted as permission to launch with EU personal data before the processor agreements, transfer safeguards, DPIA, retention rules, privacy notice, and rights workflows are completed and evidenced; development can continue with synthetic or irreversibly anonymised data in the meantime. I also ask the team to reconsider Article 6(1)(b) for optional reference images and exact birth details unless their necessity for the contracted service can be demonstrated, using minimisation or a separate valid basis where appropriate.

## Stretch — Remediation plan for the DPIA finding

**Deliverable that closes the gap.** A controller-approved MIRA DPIA with: precise purposes and lawful bases; data-subject and data-flow inventory; necessity and proportionality assessment; Article 9 and Article 22 screening; vendor/subprocessor and transfer analysis; risk scoring; technical and organisational measures; retention/deletion design; residual-risk decision; and an approval/change log.

**Ownership.** The MIRA controller is accountable. A privacy lead or DPO facilitates; product and engineering supply architecture and operational evidence; security performs threat and control analysis; procurement supplies contracts and transfer records; qualified counsel reviews the final legal positions.

**Timeline.** Ten working days for discovery and a first draft, five working days for control design and evidence gathering, then five working days for review and approval. Production remains gated during this approximately four-week process. If high residual risk remains, add time for Article 36 consultation before processing.

**Closure evidence.** A signed and dated DPIA; completed risk register; approved data-flow/vendor map; linked DPAs and transfer safeguards; privacy notice; retention schedule; screenshots or test logs for consent, deletion and rights workflows; security test evidence; named control owners; and a review trigger for new purposes, vendors, models, regions, or data categories.
