# MIRA GDPR Peer Audit — Evidence and Questions Log

**Auditor:** Paola Hintze  
**Teammate / builder:** Maria Cavali (`mariacavali`)  
**Project audited:** MIRA V4 (with V3 shared-platform context)  
**Review date:** 19 August 2026  
**Status:** Independent review completed; builder debrief pending

## Kick-off and independence record

Only Maria's data-processing brief and technical documentation were used before forming the conclusions. I did **not** review Maria's lawful-basis assessment, DPIA analysis, compliance memo, or gap findings. I worked independently and deferred discussion of conclusions until Phase 5.

Materials reviewed:

- [MIRA system brief for peer audit](https://github.com/mariacavali/MIRA-asignment-/blob/main/MIRA_SYSTEM_BRIEF_FOR_PEER_AUDIT.md)
- [AI and data inventory](https://github.com/mariacavali/MIRA-asignment-/blob/main/docs/MIRA_AI_AND_DATA_INVENTORY.md)
- [Architecture for audit](https://github.com/mariacavali/MIRA-asignment-/blob/main/docs/MIRA_ARCHITECTURE_FOR_AUDIT.md)
- [MIRA V4 current state](https://github.com/mariacavali/MIRA-asignment-/blob/main/docs/MIRA_V4_CURRENT_STATE.md)

Where those materials are silent, this log records the gap and the provisional assumption rather than treating an assumption as fact.

## Phase 1 — Read and annotate

I read the brief once without notes and a second time using these annotation tags:

- **[PD]** personal data
- **[SC?]** Article 9 special-category data may be volunteered, depicted, or inferred
- **[CLARIFY]** information needed before a final opinion
- **[TRANSFER?]** vendor or data flow whose legal entity, hosting region, or transfer mechanism is unknown
- **[PURPOSE?]** possible purpose-limitation or minimisation concern

### Annotated evidence extract

1. MIRA is a private, authenticated creative-direction application for an individual founder, creator, or consultant. **[PD: account identity, session and cookie identifiers]**
2. V4 collects what the user is building, audience, desired feeling, moodboard purpose, recognition answers, and a structured creative brief. **[PD: linked to an identifiable account] [SC?: free text can reveal health, beliefs, sexuality, ethnicity, or other sensitive facts]**
3. V4 stores birth date, optional birth time, city, country, and time zone, but the current V4 output does not use those details for Human Design or numerology. **[PD] [PURPOSE?: necessity and current purpose unclear]**
4. A user may upload one inspiration image and an explanation; V3 separately supports up to six consent-gated reference images. **[PD: image, metadata and explanation] [SC?: images may depict or reveal sensitive traits; they are not biometric data merely because faces appear]**
5. Forge chat (`gpt-5-mini`) generates adaptive questions and a stored Creative DNA profile; Forge ImageService generates and refines visual assets. **[PD: prompts, responses and inferred profile] [TRANSFER?: service entity/region not stated]**
6. Data is stored in owner-scoped MySQL/TiDB tables and S3-backed object storage. **[TRANSFER?: host, location and subprocessors not stated]**
7. Manus OAuth authenticates users; optional integrations include Dakidarts and Notion. **[TRANSFER?: legal entities/regions and DPA status not stated]**
8. Production hosting, processor regions, retention periods, deletion operations, and final operating organisation are not confirmed. **[CLARIFY: controller, Article 28 contracts, Chapter V transfers, Articles 13–14 notice, Articles 15–22 rights, Article 5 storage limitation]**
9. Human choice is built into creative selection and refinement. **[CLARIFY: useful human involvement, but no evidence that MIRA currently makes decisions with legal or similarly significant effects]**

## Phase 2 — Personal data summary

| Data category | Source | Purpose(s) stated or inferred from brief | Crosses EU border? | Special category? |
|---|---|---|---|---|
| Account identity, OAuth/session and cookie data | User; Manus OAuth | Authentication, owner-scoped access, security | Cannot determine | No, ordinarily |
| Creative/business context and brief | User | Generate creative direction and campaign outputs | Possibly, through Forge | Not inherently; free text may contain Article 9 data |
| Birth date/time/place/time zone | User | Retained by V4; current operational purpose unclear | Possibly, if sent to vendors; brief does not confirm | No, by itself |
| Recognition and discovery answers/messages | User; adaptive AI questions | Generate Creative DNA and creative direction | Likely possible through Forge; region unknown | May reveal or support sensitive inferences |
| Inspiration/reference images, explanations and metadata | User; may depict third parties | Visual synthesis and refinement | Possibly through Forge/S3 | Not automatically biometric; may reveal Article 9 information |
| Creative DNA / profile and generated assets | MIRA and Forge | Personalised creative direction and moodboard | Possibly | Inferences could become special-category data depending on content |
| Operational logs and object identifiers | Application/vendors | Delivery, reliability and security | Cannot determine | Usually no; may contain personal data |
| Optional V3 numerology result | Dakidarts, derived from user input | Feature-gated V3 experience | Cannot determine | Not inherently; still profiling/personal data |

## Role map

| Entity | Provisional GDPR role | Processing activity | DPA needed? |
|---|---|---|---|
| Final organisation operating MIRA | Controller | Determines why and how MIRA processes user data | N/A internally; must contract its processors |
| Maria / development team | Authorised personnel if inside the controller; processor only if a separate entity acts on instructions | Builds, maintains, and may access test/support data | Only if a separate service provider processes personal data for the controller |
| Manus OAuth/platform | Processor or independent controller for limited account purposes; contract/privacy terms must confirm | Authentication and platform services | Yes for processing on the controller's behalf |
| Forge chat and ImageService | Processor/subprocessor | Receives prompts/images; generates questions, profiles and visuals | Yes |
| MySQL/TiDB hosting provider | Processor/subprocessor | Structured storage | Yes |
| S3/object-storage provider | Processor/subprocessor | Image and asset storage | Yes |
| Dakidarts and Notion, if enabled with personal data | Processor or separate controller depending on purpose/terms | Optional enrichment/export | DPA required where acting as processor |
| OpenAI-compatible embedding service, if enabled with personal data | Processor/subprocessor | Embedding or related model processing | Yes |

The brief does not identify the contracting entities, locations, subprocessors, or signed DPAs. For any data exported from the EEA, the controller must document an applicable Chapter V mechanism. An adequacy decision may apply to the destination; for a U.S. recipient, the EU–U.S. Data Privacy Framework works only for a participating/certified entity. Otherwise, the controller would normally need the Commission's Standard Contractual Clauses, a transfer impact assessment, and appropriate supplementary measures. A DPA alone is not a transfer mechanism.

## Phase 3 — Clarifying questions log

| # | What I need to know | Why it matters / GDPR obligation | Provisional assumption without an answer |
|---|---|---|---|
| 1 | Which legal entity determines MIRA's purposes and means, and which exact legal entities provide OAuth, Forge, database, storage and optional integrations? Are Article 28 DPAs and subprocessor terms signed? | Establishes controller/processor roles and accountability under Articles 5(2), 24 and 28. | The future MIRA operator is controller; vendors acting on instructions are processors. DPA evidence is absent, so production processing should not proceed until verified. |
| 2 | What lawful basis is documented for each purpose: account/security, core creative service, birth data, optional images, support/analytics, and any model improvement? How are accidental Article 9 disclosures handled? | Articles 5(1)(b), 6 and 9 require a purpose-specific basis; consent must be freely given, specific, informed and withdrawable. | Article 6(1)(b) may cover data objectively necessary for the requested service. Optional/unnecessary data needs a separate basis; Article 9 data should be blocked or supported by an Article 9 condition, likely explicit consent if appropriate. |
| 3 | Where is each vendor's processing/storage located, and what adequacy decision, DPF certification, SCCs/TIA or other Chapter V mechanism covers each transfer? | Articles 44–49 regulate transfers outside the EEA. | Cross-border transfers are possible but undocumented; no transfer is treated as lawful until the map and mechanism are evidenced. |
| 4 | What retention schedule and deletion workflow applies to database rows, images, logs, backups, vendor copies and deactivated accounts? Can access, correction, deletion, restriction, portability and objection requests be completed on time? | Articles 5(1)(e), 12 and 15–22 require storage limitation and operational rights handling. | Retention/deletion and rights workflows are not yet demonstrated. |
| 5 | Has the controller completed a DPIA screening or full DPIA covering AI profiling, free text, images, possible sensitive inferences, vendors, security and transfers? Could any future use affect access to work, credit, insurance or another significant opportunity? | Article 35 requires a DPIA before likely high-risk processing; Article 22 applies to solely automated decisions with legal or similarly significant effects. | A full DPIA is required before production. Current creative outputs do not appear to trigger Article 22, but this must be reassessed if use changes. |

## Reference framework

- [GDPR consolidated text, including Articles 5, 6, 9, 12–22, 28, 35 and 44–49](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng)
- [EDPB-endorsed DPIA and automated-decision-making guidelines](https://www.edpb.europa.eu/endorsed-wp29-guidelines_en)
- [European Commission adequacy decisions](https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/adequacy-decisions_en)
- [European Commission: EU–U.S. data transfers](https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/eu-us-data-transfers_en)
