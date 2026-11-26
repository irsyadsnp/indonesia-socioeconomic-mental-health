# Variable Architecture and Variable-Domain Inventory

**Status:** Initial inventory; all variable names, file locations, respondent universes, and wave availability remain unverified until matched to official IFLS questionnaires, codebooks, and data files.

## 1. Purpose

This document translates the provisional conceptual framework into an auditable variable architecture. It is not a claim that every construct is measured in IFLS4 and IFLS5.

The inventory separates:
- The research construct.
- The candidate operational measure.
- The expected data level.
- The documentation required for verification.
- The status of the mapping.

No variable should be included in an analysis dataset solely because its label appears plausible.

## 2. Verification Status Definitions

| Status | Meaning |
|---|---|
| NOT REVIEWED | The relevant questionnaire/codebook has not yet been checked. |
| CANDIDATE | A construct or measure is proposed, but the exact item and variable are not confirmed. |
| DOCUMENTED | The official documentation identifies the item/variable and its meaning. |
| DATA VERIFIED | The variable is present in the relevant data file and its values/codes have been inspected. |
| COMPARABILITY VERIFIED | Measurement meaning, coding, respondent universe, and timing have been assessed across waves. |
| EXCLUDED | The variable is unavailable, unsuitable, or outside the defined scope; reason must be recorded. |

A variable can have different statuses in IFLS4 and IFLS5.

## 3. Core Variable-Domain Inventory

### 3.1 Outcome: Depressive Symptoms

| Field | Initial specification |
|---|---|
| Construct | Depressive symptoms |
| Candidate instrument | CES-D, subject to verification |
| Candidate operationalization | Documented total or subscale score using the official item set and scoring rules |
| Unit of analysis | Individual respondent |
| IFLS4 status | NOT REVIEWED |
| IFLS5 status | NOT REVIEWED |
| Required verification | Instrument name, item wording, item count, response options, recall period, scoring, reverse-coded items, missing-item rule, respondent eligibility, file and variable names |
| Key caution | A symptom score is not a clinical diagnosis. Do not assume identical instruments or scoring across waves. |

The primary outcome must not be finalized until the exact instrument and scoring protocol have been confirmed from the official documentation.

### 3.2 Socioeconomic Exposures

| Construct | Candidate measures to investigate | Likely data level | IFLS4 status | IFLS5 status |
|---|---|---|---|---|
| Education | Highest grade completed, highest educational attainment, years of schooling | Individual | NOT REVIEWED | NOT REVIEWED |
| Employment | Current employment status, labor-force participation, occupation, work arrangement | Individual | NOT REVIEWED | NOT REVIEWED |
| Work conditions | Working hours, job characteristics, employment security, where measured | Individual | NOT REVIEWED | NOT REVIEWED |
| Household economic resources | Household income, expenditure/consumption, asset ownership or an official wealth measure | Individual/household | NOT REVIEWED | NOT REVIEWED |
| Material conditions | Housing characteristics, utilities, crowding, durable assets | Household | NOT REVIEWED | NOT REVIEWED |

These are candidate domains, not confirmed IFLS variables. Income, expenditure, consumption, assets, and wealth indices are distinct constructs and must not be substituted for one another without justification.

### 3.3 Demographic and Contextual Variables

| Construct | Candidate measures to investigate | Likely data level | IFLS4 status | IFLS5 status |
|---|---|---|---|---|
| Age | Age at interview or derived age using documented birth/interview dates | Individual | NOT REVIEWED | NOT REVIEWED |
| Sex/gender | Exact demographic item and categories recorded by IFLS | Individual | NOT REVIEWED | NOT REVIEWED |
| Marital status | Current marital status and documented categories | Individual | NOT REVIEWED | NOT REVIEWED |
| Household composition | Household size, relationship to household head, living arrangement | Individual/household | NOT REVIEWED | NOT REVIEWED |
| Geography | Province, district, urban/rural classification, or other available geographic identifiers | Individual/household/community | NOT REVIEWED | NOT REVIEWED |
| Migration | Residence history or migration indicators, if available and relevant | Individual/household | NOT REVIEWED | NOT REVIEWED |

Use the categories and terminology documented by IFLS. Do not infer gender identity from a variable that only records sex.

### 3.4 Potential Confounder Domains

| Candidate domain | Why it may matter | Conditions for inclusion |
|---|---|---|
| Childhood socioeconomic background | May precede adult socioeconomic position and influence later mental health | Verify measurement, timing, and relevance to the exposure being studied |
| Family background | May shape education, employment opportunities, and mental health | Define the construct and establish that it precedes the exposure period |
| Prior health | May influence both later socioeconomic conditions and depressive symptoms | Distinguish pre-exposure health from health measured after exposure |
| Prior mental-health status | May influence later employment/resources and subsequent symptoms | Verify timing and measurement; consider how adjustment changes the estimand |
| Geographic context | May influence economic opportunity and access to resources | Establish appropriate geographic level and survey design implications |

This is a candidate-domain list, not a ready-made adjustment set. The final set must be exposure-specific and justified by temporal ordering and a causal diagram.

### 3.5 Potential Mediators and Effect Modifiers

| Role | Candidate domain | Verification and analysis requirement |
|---|---|---|
| Mediator | Financial strain or material hardship | Confirm construct, timing, and whether it follows the exposure |
| Mediator | Housing/living conditions | Determine whether it is part of the exposure definition or a downstream pathway |
| Mediator | Work conditions | Establish whether the target exposure is employment status or a broader socioeconomic construct |
| Mediator | Social support/resources | Confirm measurement and temporal position |
| Effect modifier | Age group | Prespecify rationale and assess subgroup sample sizes |
| Effect modifier | Sex/gender category as recorded | Use documented categories and assess interaction uncertainty |
| Effect modifier | Urban/rural or regional context | Confirm definitions, sampling structure, and sufficient observations |

Do not adjust for a potential mediator in a model intended to estimate a total association without explicitly acknowledging the change in estimand.

## 4. Data-Level and Linkage Architecture

The project may involve several distinct data levels:

1. **Individual respondent:** education, employment, demographic characteristics, and individual outcome measures.
2. **Household:** household roster, economic resources, assets, and housing conditions.
3. **Community or geographic context:** contextual characteristics, where available and justified.
4. **Repeated respondent observations:** wave-specific records linked using official respondent identifiers.

Before merging files, document:
- The unique key in each source file.
- Whether the key identifies a person, household, or community.
- The expected row grain of each file.
- Whether one-to-one, one-to-many, or many-to-one joins are expected.
- Duplicate-key checks before and after each join.
- Whether household membership or identifiers change across waves.
- The handling of respondents who split off, move, or are not re-interviewed.

Never merge files using row order or an unverified identifier.

## 5. Required Variable-Mapping Register

Complete one record for every variable selected for analysis. Keep the original IFLS variable name and labels intact.

| Field | Required entry |
|---|---|
| Construct | Concept represented by the variable |
| Analysis role | Outcome / exposure / confounder / mediator / effect modifier / design variable |
| Wave | IFLS4 / IFLS5 / both |
| Source file | Exact official filename |
| Questionnaire section | Exact section/module |
| Variable name | Exact variable name from the data |
| Variable label | Exact documented label |
| Question wording | Verbatim or faithful transcription from official documentation |
| Respondent universe | Who was eligible to answer |
| Reference period | Period covered by the question |
| Data type | Numeric / categorical / string / date / other |
| Value labels | All documented codes and meanings |
| Missing codes | Refusal, don't know, not applicable, system missing, and other special codes |
| Transformation | Recode, derivation, aggregation, or score construction |
| Wave comparability | Comparable / partly comparable / not comparable / not assessed |
| Verification status | One of the defined statuses |
| Evidence | Documentation filename and page/table/section |
| Notes | Ambiguities, decisions, and limitations |

## 6. File and Documentation Audit Procedure

For each candidate construct:

1. Locate the official questionnaire and codebook for the relevant wave.
2. Search for the construct and related question wording; do not rely on filename similarity alone.
3. Record the exact module, item, respondent universe, and reference period.
4. Identify the corresponding data file and exact variable name.
5. Inspect the data dictionary/value labels and confirm the variable exists in the downloaded file.
6. Inspect frequencies, ranges, missing codes, and unusual values.
7. Compare the item, response scale, eligibility, and timing across IFLS4 and IFLS5.
8. Record the evidence and assign a verification status.
9. Only then decide whether the variable can be used in the analysis.

## 7. Measurement and Data-Quality Rules

- Preserve raw source variables; create derived variables in a separate, documented analysis layer.
- Keep special missing codes distinct until their meanings have been checked.
- Do not treat structural skips or not-applicable responses as ordinary zero values.
- Do not calculate scale scores until item inclusion, reverse coding, and missing-item rules are documented.
- Report the denominator and missingness for each analysis variable.
- Check distributions and implausible values against the questionnaire and codebook.
- Do not combine individual- and household-level measures without a documented linkage procedure.
- Do not compare waves solely because variable names or labels look similar.
- Document all exclusions and sample restrictions.

## 8. Current Decisions and Open Questions

| Decision or question | Current position |
|---|---|
| Primary outcome | Depressive-symptom measure; exact instrument and scoring not yet confirmed |
| CES-D | Candidate only; must be verified in each wave |
| Main socioeconomic exposures | Education, employment, and household economic resources; operational measures not yet selected |
| Study waves | IFLS4 and IFLS5 are provisional candidate waves |
| Longitudinal analysis | Conditional on respondent linkage, repeated measurement, timing, and comparability |
| Confounder set | Not finalized; requires exposure-specific reasoning |
| Mediators | Exploratory candidates; not automatically included as controls |
| Effect modifiers | To be prespecified and limited by measurement and statistical power |
| Survey design | Weights, strata, clusters, and applicable design variables must be identified from documentation |

## 9. Exit Criteria Before Analysis Dataset Construction

The variable architecture is ready for implementation only when:

- The primary outcome is documented and its scoring is reproducible.
- Each primary exposure has an exact source file, variable, definition, and coding rule.
- Respondent eligibility and sample restrictions are explicit.
- Cross-wave comparability is assessed for every repeated measure.
- Person/household linkage keys and join cardinalities are verified.
- Missing-value codes and derivations are documented.
- Survey-design variables and their intended use are identified.
- The analysis estimand and covariate strategy are written down.

**Next step:** conduct a source-by-source IFLS documentation audit and populate the mapping register with exact file names, questionnaire references, variable names, and evidence. Do not begin outcome scoring or model fitting before the relevant verification criteria are met.
