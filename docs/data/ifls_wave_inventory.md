# IFLS Wave Inventory and Initial Feasibility Map

**Project:** Indonesia Socioeconomic Factors & Mental Health  
**Stage:** 01.1 — Dataset and wave mapping  
**Status:** Preliminary desk review; not a substitute for questionnaire/codebook audit  
**Review date:** 2026-11-26

## 1. Purpose

This document records the known IFLS survey rounds and an initial assessment of their suitability for a study of socioeconomic conditions and mental-health-related outcomes.

The inventory is a planning aid. A wave is not considered analytically eligible until its questionnaires, codebooks, data notes, sample definitions, identifiers, and access conditions have been inspected.

## 2. IFLS survey-round inventory

| Survey round | Fieldwork period | Coverage / design note | Initial role in this project |
|---|---|---|---|
| IFLS1 | 1993–1994 | Baseline survey; 13 provinces; approximately 83% of the Indonesian population at baseline | Historical baseline; inspect mental-health item availability and respondent coverage |
| IFLS2 | 1997–1998 | Follow-up of the original sample | Candidate for socioeconomic and demographic panel history; mental-health outcome availability must be verified |
| IFLS2+ | 1998 | Approximately 25% subsample, conducted after IFLS2 during the economic crisis | Special subsample only; do not treat as a full survey wave or pool naively with IFLS2 |
| IFLS3 | 2000 | Follow-up of the full IFLS sample | Candidate for repeated socioeconomic measures and historical mental-health items |
| IFLS4 | 2007–2008 | Follow-up survey; added a dedicated KP depression-scale section | Strong candidate for the main mental-health analysis, subject to full audit |
| IFLS5 | 2014–2015 | Follow-up survey; KP depression scale retained from IFLS4 | Strong candidate for the main mental-health analysis and comparison with IFLS4 |

IFLS-East was conducted in 2012 in eastern Indonesian provinces not covered by the original 13-province IFLS sample. It is a related extension, not simply another standard IFLS panel round. It must be evaluated separately and should not be appended to the core IFLS panel without a defensible design and harmonization plan.

## 3. Initial mental-health measurement map

The available IFLS5 documentation describes a dedicated **KP (Depression Scale / Mental Health)** section. The IFLS5 KP questions ask about how respondents felt during the past week and use a 10-item short CES-D measure. IFLS4 introduced the KP section and IFLS5 retained it.

The IFLS5 overview documentation also notes that IFLS1 and IFLS3 included an earlier set of eight mental-health questions, while IFLS4 and IFLS5 used the 10-item short CES-D questions to improve comparability with other surveys.

| Wave | Initial documentation finding | Analytical implication |
|---|---|---|
| IFLS1 | Earlier set of 8 mental-health questions reported in IFLS5 overview documentation | Do not assume equivalence to CES-D-10 |
| IFLS2 | Exact mental-health instrument and eligible respondent universe not yet confirmed | Inspect wave-specific questionnaire and codebook |
| IFLS2+ | Exact mental-health instrument and eligible respondent universe not yet confirmed | Treat separately; inspect subsample documentation |
| IFLS3 | Earlier set of 8 mental-health questions reported in IFLS5 overview documentation | Do not assume equivalence to CES-D-10 |
| IFLS4 | Dedicated KP depression-scale section introduced; documented as short CES-D | Candidate for comparable analysis with IFLS5 after item-level verification |
| IFLS5 | Dedicated KP depression-scale section retained; 10-item short CES-D | Candidate primary outcome wave |

**Important:** This is a documentation-level map, not a validated scoring specification. The precise item wording, response codes, reverse-scored items, missing-item rules, age eligibility, respondent universe, and scale construction must be verified against the official questionnaire and codebook before calculating scores.

The CES-D-10 captures depressive symptoms. It does not independently establish a clinical diagnosis of depression.

## 4. Initial socioeconomic coverage

IFLS documentation and survey descriptions identify broad information at individual, household, and community levels. Candidate domains include:

- household consumption and expenditure;
- income and labor earnings;
- employment and work histories;
- household and individual assets;
- education and migration histories;
- household composition and demographic characteristics;
- health conditions and health-service utilization;
- community characteristics and access to facilities.

The presence of a domain in the survey series does not guarantee that a variable is available, identically defined, or measured for the same respondent universe in every wave. Each variable must be mapped at question and codebook level.

## 5. Preliminary wave-selection recommendation

Use **IFLS4 and IFLS5 as the first candidate pair** for the primary repeated-outcome analysis because the documentation indicates that the KP depression scale was introduced in IFLS4 and retained in IFLS5.

Use IFLS1 and IFLS3 only as a separate historical measurement track unless item-level review establishes a defensible harmonization strategy. Do not combine the older eight-item questions with CES-D-10 scores by simply summing, standardizing, or applying the same cut-off.

IFLS2 and IFLS2+ remain unresolved for the mental-health outcome and must be checked before inclusion.

A two-wave IFLS4–IFLS5 analysis can estimate changes or associations across the 2007–2008 and 2014–2015 observations, but it does not by itself establish causal effects. Attrition, respondent linkage, time-varying confounding, survey design, and measurement comparability remain central considerations.

## 6. Required verification checklist

- [ ] Obtain official IFLS4 and IFLS5 questionnaires for the relevant individual/adult modules.
- [ ] Obtain matching codebooks and data notes.
- [ ] Identify the KP section files and exact variable names for each wave.
- [ ] Confirm age eligibility and respondent universe for KP in each wave.
- [ ] Verify item wording, recall period, response categories, and coding.
- [ ] Verify reverse coding and missing-item/scoring rules from documentation.
- [ ] Check whether IFLS4 and IFLS5 KP items are identical or changed.
- [ ] Identify socioeconomic variables and map their question/codebook references across IFLS4 and IFLS5.
- [ ] Confirm respondent identifiers and cross-wave linkage procedures.
- [ ] Inspect sample weights, strata, primary sampling units, and guidance for each wave.
- [ ] Document attrition and non-response relevant to the analytic sample.
- [ ] Verify data access and use conditions before downloading or processing files.

## 7. Source documents

1. RAND, *The Fifth Wave of the Indonesia Family Life Survey (IFLS5): Overview and Field Report*, WR-1143/1. https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z1/RAND_WR1143z1.pdf
2. RAND, *User's Guide for the Indonesia Family Life Survey, Wave 5*, WR-1143/2. https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z2/RAND_WR1143z2.pdf
3. RAND, IFLS overview and data access. https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS.html
4. RAND, IFLS data access conditions. https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/access.html
5. Strauss, J. et al., IFLS overview and field report materials, including IFLS5 survey design and history. See the RAND IFLS documentation portal above.
6. Marvianto, R. D. (2023). *Psychometric properties of Mental Health Scale: An Item Response Theory Approach*. Gadjah Mada Journal of Psychology. https://doi.org/10.22146/gamajop.73878

## 8. Decision log

| Date | Decision | Rationale |
|---|---|---|
| 2026-11-26 | Prioritize IFLS4 and IFLS5 for initial KP/CES-D-10 feasibility review | Available IFLS5 documentation states that the KP depression-scale section was introduced in IFLS4 and retained in IFLS5 |
| 2026-11-26 | Keep IFLS1 and IFLS3 as a separate historical measurement track | Earlier eight-question mental-health measures should not be assumed equivalent to CES-D-10 |
| 2026-11-26 | Keep IFLS2 and IFLS2+ unresolved pending instrument review | Exact measure and respondent universe have not yet been confirmed |
| 2026-11-26 | Exclude IFLS-East from the core wave inventory for now | It is a separate geographic extension and requires its own sample/design assessment |

---

**Next task:** Stage 01.2 — inspect official IFLS4 and IFLS5 questionnaires, codebooks, and data notes to build an item-level mental-health variable map.
