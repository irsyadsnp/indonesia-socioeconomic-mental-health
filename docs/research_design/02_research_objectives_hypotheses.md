# Research Objectives and Hypotheses

**Status:** Provisional protocol document. This document defines the intended analytical questions and testable hypotheses. It does not establish that the required measures are available or comparable in IFLS4 and IFLS5. Those points must be verified from the official questionnaires, codebooks, and data.

## 1. Overall Research Aim

To examine the association between socioeconomic conditions and depressive symptoms among eligible Indonesian adults using IFLS data, and to assess whether a longitudinal and predictive analysis is justified by the available measurements and survey structure.

## 2. Specific Objectives

### Primary Objective

Estimate the association between selected socioeconomic indicators and the selected depressive-symptom measure among eligible respondents, adjusting for a prespecified set of theoretically justified covariates.

### Secondary Objectives

1. Describe the distribution of depressive-symptom scores and socioeconomic characteristics in the eligible analytic sample.
2. Estimate separate and mutually adjusted associations for socioeconomic indicators that are sufficiently measured and conceptually distinct.
3. Assess whether selected associations differ across prespecified demographic groups, provided subgroup definitions and sample sizes are adequate.
4. If repeated measures and respondent linkage are verified, examine whether within-person changes in socioeconomic conditions are associated with within-person changes in depressive-symptom scores.
5. Evaluate predictive performance of selected machine-learning models against transparent statistical baselines, using validation that respects respondent-level dependence and the survey structure.
6. Assess robustness of the findings to reasonable alternative outcome definitions, covariate specifications, missing-data approaches, and sample restrictions.

## 3. Primary Outcome and Exposure Definitions

### Outcome

The intended outcome is a depressive-symptom measure documented in the relevant IFLS wave(s). CES-D is a candidate instrument only; its presence, item set, respondent eligibility, scoring algorithm, direction, and cross-wave comparability must be verified before it is adopted.

The primary analysis should retain a continuous score if the instrument and distribution support that approach. A binary threshold outcome should be secondary and used only if a defensible, documented cut-off is appropriate for the instrument and population. A symptom scale must not be described as a clinical diagnosis.

### Socioeconomic Exposures

Candidate domains include:

- Educational attainment.
- Employment status and employment characteristics.
- Household economic resources, using a documented measure such as consumption or income if available and appropriate.
- Household material conditions or assets, if a valid and interpretable measure can be constructed.

Each domain must be operationalized using verified variables, units, reference periods, coding rules, and missing-value conventions. Avoid combining unlike constructs into a single index without a clear rationale and validation.

## 4. Working Hypotheses

The hypotheses below are directional where a defensible direction can be stated, but remain provisional until the measures and relevant literature are reviewed.

### H1 — Socioeconomic Advantage

More advantaged socioeconomic conditions are associated with lower depressive-symptom scores, conditional on the prespecified covariates.

**Null (H01):** The adjusted association between the socioeconomic indicator and depressive-symptom score is zero.

### H2 — Heterogeneity Across Demographic Groups

The association between socioeconomic conditions and depressive-symptom scores differs across at least one prespecified demographic subgroup.

**Null (H02):** The relevant socioeconomic association is equal across the prespecified groups; the corresponding interaction term(s) are jointly zero.

Subgroup analyses must be limited to a small, theory-driven set defined before examining outcome associations. Interaction tests should be interpreted cautiously and supported by adequate sample sizes.

### H3 — Within-Person Change

Among respondents with comparable repeated measures, deterioration in socioeconomic conditions is associated with an increase in depressive-symptom scores over time.

**Null (H03):** The within-person association between change in the socioeconomic indicator and change in depressive-symptom score is zero.

H3 will be tested only if respondent identifiers, repeated measures, timing, and measurement comparability are verified. Otherwise, it will be marked not estimable rather than replaced with an unsupported cross-sectional claim.

## 5. Predictive Analysis: Exploratory Objective, Not a Causal Hypothesis

Machine learning will be treated as a predictive extension, not as a method for establishing causal effects.

The predictive task, target definition, feature availability, and validation design will be specified after the data audit. Performance should be compared with an appropriate simple baseline and reported using metrics suited to the outcome type. Calibration and uncertainty should be considered alongside discrimination or prediction error.

Feature importance, SHAP values, and partial-dependence patterns describe model behavior under the fitted data and assumptions. They do not establish that changing a feature would change mental health.

## 6. Analysis Principles

1. Define the target population, unit of analysis, outcome, exposure contrasts, and estimand before fitting models.
2. Prefer effect estimates with confidence intervals and substantive interpretation over significance-only reporting.
3. Distinguish minimally adjusted from fully adjusted models, with covariate choices justified by subject-matter reasoning.
4. Avoid adjusting for variables that may be mediators of the socioeconomic relationship when estimating a total association; if mediation is studied, define it separately.
5. Consider nonlinear functional forms where theoretically and empirically justified.
6. Account for IFLS sampling weights, strata, and clusters as appropriate to the target estimand and estimation method.
7. Address repeated observations, attrition, missingness, and respondent-level dependence explicitly.
8. Predefine a limited set of primary tests. Treat additional subgroup, interaction, and model-search results as exploratory and address multiplicity where appropriate.
9. Do not infer causality from regression adjustment, longitudinal ordering, predictive accuracy, or explainability alone.

## 7. Decision Rules After the IFLS Data Audit

The research team will finalize the protocol only after confirming:

- Which IFLS waves and respondents contain the candidate outcome instrument.
- Whether the same or harmonizable items and scoring procedures are used across waves.
- Which socioeconomic variables are available, their measurement units, reference periods, and comparability.
- Whether respondent-level linkage supports a repeated-measures design.
- The appropriate age and respondent eligibility criteria.
- Survey design variables and the correct use of weights.
- Sample size, missingness, attrition, and the feasibility of planned subgroup and interaction analyses.

Any hypothesis that cannot be operationalized with verified data will be revised, downgraded to exploratory, or removed with a documented rationale.

## 8. Status

This document is a research-design specification, not a completed statistical analysis plan. No empirical result, variable availability, or causal conclusion is implied.
