# Research Protocol
## Indonesia Socioeconomic Factors & Mental Health

**Protocol status:** Draft v0.1 — pre-data-access and pre-analysis  
**Repository:** `irsyadsnp/indonesia-socioeconomic-mental-health`  
**Primary candidate data source:** Indonesia Family Life Survey (IFLS)  
**Last updated:** 2026-11-26

---

## 1. Project overview

This project investigates how socioeconomic conditions are associated with mental-health-related outcomes among people observed in the Indonesia Family Life Survey (IFLS). The intended design is longitudinal where repeated, comparable measurements are available.

The project will prioritize transparent descriptive and statistical analysis. Longitudinal, multilevel, predictive, and explainable-machine-learning methods will be used only when the data structure, measurement quality, sample size, and research question justify them.

This protocol is provisional. No outcome, exposure, sample, wave combination, or model is considered finalized until the relevant questionnaires, codebooks, data files, and survey documentation have been audited.

## 2. Background and rationale

Socioeconomic conditions may be related to mental health through multiple pathways, including material hardship, employment conditions, educational opportunity, household resources, social support, and access to health services. These relationships may differ across age groups, sex, life stages, locations, and survey periods.

IFLS is a longitudinal household survey that includes individual, household, community, and health information. Its first wave was conducted in 1993–1994. The baseline sample covered 13 provinces and was designed to represent approximately 83% of the Indonesian population at that time; it should therefore not be described as a nationally representative sample of every Indonesian province. IFLS waves and modules differ, so the availability and comparability of mental-health and socioeconomic measures must be verified before analysis.

## 3. Research problem

There is a need to characterize the relationship between socioeconomic circumstances and mental-health-related outcomes using individual- and household-level longitudinal information, while accounting for survey design, measurement differences, repeated observations, and potential attrition.

The study will not assume that observed associations represent causal effects.

## 4. Main research question

**How are socioeconomic conditions associated with variation in mental-health-related outcomes among IFLS participants, and how do these associations vary across observed survey waves?**

### 4.1 Secondary research questions

1. How are income, consumption or expenditure, assets, education, and employment associated with the selected mental-health outcome?
2. Do these associations differ by age, sex, marital status, or household circumstances?
3. Where comparable repeated measures exist, how do within-person changes in socioeconomic circumstances relate to within-person changes in the outcome?
4. How much do estimates change under alternative outcome definitions, sample restrictions, missing-data approaches, and model specifications?
5. If predictive modeling is justified, how well can the selected outcome be predicted in held-out data, and which features contribute to prediction?

## 5. Objectives

### 5.1 General objective

To examine associations between socioeconomic factors and mental-health-related outcomes in IFLS data using a reproducible and methodologically defensible analytical workflow.

### 5.2 Specific objectives

- Identify relevant IFLS waves, modules, variables, and measurement instruments.
- Document the provenance, structure, quality, and comparability of the selected data.
- Describe the distribution of the outcome and socioeconomic characteristics.
- Estimate adjusted associations using statistical models appropriate to the outcome and survey structure.
- Evaluate longitudinal associations if repeated measures and respondent linkage are adequate.
- Conduct sensitivity and robustness analyses.
- Publish reproducible code, documentation, and non-disclosive aggregate results.

## 6. Data source and access

### 6.1 Primary candidate

The primary candidate is the **Indonesia Family Life Survey (IFLS)**, conducted by RAND in collaboration with Indonesian research institutions.

Official resources:

- IFLS overview: https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS.html
- Data access: https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/access.html
- Data notes and documentation: https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/datanotes.html
- IFLS publications: https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/papers.html

Access is subject to the data provider's registration, use, and distribution conditions. Restricted-use variables or files must not be obtained or redistributed without authorization.

### 6.2 Candidate waves

Potential waves include IFLS1 (1993–1994), IFLS2 (1997–1998), IFLS2+ (1998 subsample), IFLS3 (2000), IFLS4 (2007–2008), and IFLS5 (2014–2015), subject to verified availability and access.

IFLS2+ is a subsample and must not be treated as a full-wave observation. The study will not combine waves automatically. Each wave and module must first be checked against its questionnaire, codebook, data notes, and sample design.

### 6.3 Data acquisition record

Before analysis, record:
- date of access and download;
- provider and official source URL;
- wave, module, file name, version, and format;
- access conditions and permitted uses;
- checksum for each locally stored source file, where feasible;
- documentation and codebook versions;
- any transformations or exclusions.

Raw IFLS files must not be committed to this public repository.

## 7. Study population and analytical sample

The target analytical population will be defined only after the outcome instrument and eligible waves are identified.

Provisional inclusion criteria:
- respondent belongs to an eligible IFLS wave and module;
- respondent can be linked across waves where longitudinal analysis is intended;
- the selected outcome can be computed according to its documented scoring rules;
- required exposure and covariate information is available or can be handled under a pre-specified missing-data strategy.

Exclusion criteria will be documented with counts and reasons. The project will distinguish:
- cross-sectional samples for each wave;
- balanced panels observed in all selected waves;
- unbalanced panels observed in at least one selected wave;
- outcome-specific analytical samples.

No sample size will be asserted before the data audit.

## 8. Outcome definition: mental-health-related measure

The primary outcome is **not yet finalized**. The data audit must establish which mental-health-related instrument or indicator is available, in which waves and respondent groups, and whether item wording, response options, recall periods, and scoring are comparable.

If a depressive-symptom scale such as CES-D is available and suitable, its exact version, item set, response coding, reverse-scored items, missing-item rules, and scoring procedure will be documented from official instrument and IFLS materials.

Important interpretation rule: a symptom-scale score indicates reported symptoms under that instrument. It is not, by itself, a clinical diagnosis of depressive disorder or another mental disorder.

If no sufficiently comparable outcome is available across waves, the project will use a wave-specific or cross-sectional design rather than manufacture longitudinal comparability.

## 9. Exposures and covariates

All candidate variables below are subject to a variable-level audit. Names are conceptual, not confirmed IFLS variable names.

### 9.1 Main socioeconomic exposures

- Household or individual income, where defined and measured comparably.
- Household consumption or expenditure, including per-capita or equivalized measures if justified.
- Household assets or wealth indicators.
- Employment status and labor-market characteristics.
- Educational attainment and, where available, years of schooling.

### 9.2 Candidate demographic and household covariates

- Age and age group.
- Sex as recorded in the survey.
- Marital status.
- Household size and composition.
- Urban/rural or community characteristics, where permitted and appropriately documented.
- Other health, social, or household variables only where theoretically justified and measured reliably.

### 9.3 Operationalization principles

- Preserve original variables and create documented derived variables separately.
- Record units, reference periods, category definitions, and source file locations.
- Examine skewness and extreme values before transformations.
- Do not combine income, consumption, and assets into one index without a defensible construction method.
- Avoid adjusting for variables that may be mediators or colliders without an explicit causal rationale.
- Distinguish individual-level from household- and community-level measurements.

## 10. Conceptual framework

The working framework treats socioeconomic conditions as exposures associated with mental-health-related outcomes, potentially through material resources, work, education, household circumstances, and access to services.

Age, sex, marital status, and contextual characteristics may act as confounders, effect modifiers, or descriptive stratification variables depending on the specific question and temporal ordering.

A directed acyclic graph (DAG) and an explicit adjustment set will be developed before final regression modeling. The adjustment set will not be selected solely by statistical significance or automated feature selection.

## 11. Hypotheses

These are provisional, non-directional or cautiously directional hypotheses to be evaluated after measurement audit and literature review:

- **H1:** Socioeconomic indicators are associated with the selected mental-health-related outcome after adjustment for a justified set of covariates.
- **H2:** The magnitude or pattern of associations differs across selected demographic or household subgroups.
- **H3:** Where repeated comparable measures exist, changes in socioeconomic circumstances are associated with changes in the outcome within individuals.

The null hypothesis for each inferential model will be specified in its statistical analysis plan. These hypotheses do not imply causality.

## 12. Statistical analysis plan

### 12.1 Data preparation and audit

- Inspect file structure, labels, types, identifiers, and wave-specific documentation.
- Verify respondent and household identifiers before merging.
- Check uniqueness and expected merge cardinality.
- Quantify missingness, duplicates, invalid values, and outliers.
- Check item-level and scale-level scoring rules.
- Assess cross-wave measurement comparability.
- Maintain a reproducible log of all transformations and exclusions.

### 12.2 Descriptive analysis

- Report sample flow and analytic sample sizes.
- Summarize outcome and socioeconomic variables using statistics appropriate to their distributions and measurement scales.
- Describe missingness by variable and wave.
- Present wave-specific summaries before pooled comparisons.
- Apply survey weights and design information where appropriate and documented.

### 12.3 Primary inferential analysis

The primary model family will depend on the verified outcome scale and distribution. Candidate approaches include:
- linear regression for an appropriately treated continuous score, with diagnostics;
- generalized linear models for binary, count, or other outcomes where justified;
- ordinal models for genuinely ordinal outcomes where category assumptions are defensible.

Report effect estimates, uncertainty intervals, model specification, sample size, and diagnostics. Statistical significance will not be treated as a measure of practical importance.

### 12.4 Longitudinal analysis

If respondent identifiers and repeated comparable measures support longitudinal analysis, candidate approaches include:
- pooled models with appropriate time indicators and dependence adjustments;
- individual fixed-effects models for within-person associations;
- random-effects models only when their assumptions are defensible;
- mixed-effects or multilevel models when the hierarchy and number of clusters support them.

The choice between fixed and random effects will be justified rather than selected by a mechanical test alone. Time-varying confounding, reverse directionality, attrition, and measurement changes will be discussed.

### 12.5 Survey design

The analysis will inspect available sampling weights, strata, primary sampling units, and documentation for each wave. Weighting and variance estimation will follow the relevant IFLS guidance. If a pooled multi-wave design requires harmonization or rescaling of weights, the method will be documented and sensitivity-tested. The project will not assume that one weight is valid for every wave or estimand.

### 12.6 Missing data

- Describe missingness patterns and rates by wave and variable.
- Distinguish structural missingness, non-response, and inapplicable items.
- Do not automatically impute structural missingness.
- Consider complete-case analysis only with explicit limitations.
- Consider multiple imputation only if its assumptions, variable structure, and survey design can be handled defensibly.
- Compare conclusions across reasonable missing-data strategies where feasible.

### 12.7 Multiple testing and subgroup analysis

Primary hypotheses and outcomes will be distinguished from exploratory analyses. Subgroup analyses will be limited and theoretically motivated. Where many comparisons are made, the project will report the multiplicity strategy or clearly label results as exploratory.

## 13. Predictive modeling and explainable AI

Machine learning is a secondary, optional component, not the primary inferential method.

It will proceed only if:
- the outcome is sufficiently well-defined;
- the sample size and event distribution support model development;
- the prediction target and intended use are explicit;
- data leakage can be prevented;
- validation can respect repeated respondents and survey structure.

If the same respondent appears in multiple records, train/test splitting must prevent that respondent from appearing in both partitions. Grouped or temporal validation will be considered according to the prediction task.

Candidate models may include regularized regression, tree-based methods, and gradient boosting. Performance will be assessed using metrics appropriate to the outcome, with uncertainty where feasible. Calibration and class imbalance will be addressed where relevant.

SHAP or other explainability methods may describe model behavior, but feature attribution is not evidence of causal effects. Predictive feature importance will not be presented as a causal ranking of socioeconomic determinants.

## 14. Robustness and sensitivity analyses

Potential checks, conditional on data availability:
- alternative defensible outcome scoring or thresholds;
- alternative socioeconomic operationalizations;
- alternative adjustment sets based on the causal framework;
- complete-case versus justified imputation approaches;
- weighted versus unweighted descriptive or inferential estimates, with interpretation;
- balanced versus unbalanced panel samples;
- alternative model families and functional forms;
- exclusion of observations with questionable measurement quality;
- wave-specific versus pooled estimates.

All deviations from the planned analyses will be logged and explained.

## 15. Bias, limitations, and interpretation

Potential limitations include:
- baseline geographic coverage does not include every Indonesian province;
- attrition and sample composition may change across waves;
- self-reported outcomes and socioeconomic measures may contain measurement error;
- instruments, modules, and question wording may change over time;
- residual confounding and reverse causality may remain;
- household and individual measures may not align temporally;
- survey weights and complex sampling require careful treatment;
- restricted variables may limit geographic or contextual analysis.

The study will use language such as “associated with,” “related to,” or “predicts” according to the design. Causal language such as “causes,” “effect,” or “impact” will be avoided unless a credible causal identification strategy is separately developed and defended.

## 16. Research ethics, privacy, and data governance

- Follow the IFLS data-use agreement and provider requirements.
- Do not publish respondent names, direct identifiers, precise locations, or record-level sensitive data.
- Do not upload raw, restricted, or identifiable data to this public GitHub repository.
- Store source data locally or in an appropriately secured location.
- Share only code, documentation, and aggregate outputs that comply with data-use conditions.
- Review small-cell disclosure risks before publishing tables or figures.
- Seek institutional ethics review or a formal determination if required by the research institution, supervisor, or data provider.
- Document permissions and data-use conditions before analysis or redistribution.

## 17. Reproducibility and project organization

The repository will contain:
- protocol and research-question documentation;
- data provenance, access log, and data dictionary;
- analysis code and notebooks;
- environment and dependency specifications;
- tests for critical transformations and derived variables;
- aggregate figures, tables, and reports cleared for disclosure.

Raw data will remain outside the public repository. All scripts should run from documented inputs and produce traceable outputs. Randomized procedures will use recorded seeds. Software versions and key package dependencies will be recorded.

## 18. Planned project stages

1. **Stage 00 — Project initialization:** repository, protocol, and project conventions.
2. **Stage 01 — Dataset acquisition:** verify access, documentation, waves, and permitted files.
3. **Stage 02 — Data architecture:** define file inventory, identifiers, and merge plan.
4. **Stage 03 — Data quality audit:** inspect structure, missingness, duplicates, and measurement.
5. **Stage 04 — Exploratory analysis:** describe outcome and candidate exposures.
6. **Stage 05 — Statistical analysis:** finalize estimands, DAG, adjustment set, and primary models.
7. **Stage 06 — Longitudinal and multilevel analysis:** proceed if data structure supports it.
8. **Stage 07 — Predictive modeling:** optional secondary analysis.
9. **Stage 08 — Explainable AI:** optional interpretation of validated predictive models.
10. **Stage 09 — Robustness and validation:** evaluate sensitivity and reliability.
11. **Stage 10 — Research synthesis:** integrate findings with relevant literature.
12. **Stage 11 — Publication:** prepare a transparent report or manuscript.

Stages may be revised if data access, measurement, or methodological feasibility requires it.

## 19. Decision gates before confirmatory analysis

The following must be completed before finalizing the primary analysis:
- [ ] Confirm access to the required IFLS waves and modules.
- [ ] Read the relevant questionnaires, codebooks, and data notes.
- [ ] Identify the exact mental-health outcome instrument and scoring rules.
- [ ] Confirm the availability and comparability of socioeconomic exposures.
- [ ] Verify identifiers and cross-wave linkage.
- [ ] Inspect survey design variables and weights.
- [ ] Define the target population and estimand.
- [ ] Complete the variable dictionary and missing-data plan.
- [ ] Draw and review the causal diagram and adjustment set.
- [ ] Finalize the statistical analysis plan before examining outcome-model results.

## 20. Key references and documentation

1. RAND Corporation. **Indonesia Family Life Survey (IFLS)**. https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS.html
2. RAND Corporation. **IFLS Data Access**. https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/access.html
3. RAND Corporation. **IFLS Data Notes**. https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/datanotes.html
4. RAND Corporation. **IFLS Papers and Publications**. https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS/papers.html
5. Strauss, J., et al. **The Fifth Wave of the Indonesia Family Life Survey: Overview and Field Report**. The exact report edition and citation will be verified during the literature and documentation review.

---

**Protocol governance:** This document is a versioned planning record. Any material change to the research question, outcome, sample, exposure definitions, or primary model must be recorded with its rationale and date. Analyses added after inspecting results must be labeled exploratory unless they were independently pre-specified.
