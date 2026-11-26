# Research Questions

**Status:** Provisional research-design draft. All constructs and wave-to-wave comparisons must be verified against the official IFLS questionnaires, codebooks, and data files before analysis.

## Working Title

**Socioeconomic Conditions and Depressive Symptoms Among Indonesian Adults: A Longitudinal Analysis of IFLS Data**

## Research Background

Socioeconomic conditions may be associated with mental health through multiple pathways, including material resources, employment security, educational opportunities, and household living conditions. The direction and magnitude of these relationships may vary across demographic and household contexts.

This project will use the Indonesia Family Life Survey (IFLS) to investigate these relationships. IFLS4 and IFLS5 are the intended waves for the initial study design; their exact analytic compatibility, eligible sample, and availability of mental-health measures remain subject to documentation and data audits.

## Primary Research Question

Among eligible Indonesian adults observed in the selected IFLS waves, how are socioeconomic conditions associated with depressive symptoms?

## Secondary Research Questions

1. How are educational attainment, employment status, household economic resources, and other verified socioeconomic indicators associated with depressive symptoms?
2. Do these associations differ across relevant demographic groups, such as age and sex, where the required variables and sample sizes permit?
3. Among individuals observed in more than one eligible wave, are changes in socioeconomic conditions associated with changes in depressive-symptom scores?
4. Which socioeconomic indicators show the strongest adjusted associations with the selected mental-health outcome?
5. Do flexible predictive models identify nonlinear patterns or interactions that are not adequately represented by prespecified regression models?

## Research Objectives

1. Describe the distribution of the selected mental-health outcome and socioeconomic characteristics in the eligible IFLS sample.
2. Estimate adjusted associations between verified socioeconomic indicators and the mental-health outcome.
3. Examine heterogeneity in these associations across prespecified demographic subgroups, where supported by the data.
4. Assess within-person changes only if longitudinal linkage, repeated measures, and measurement comparability are established.
5. Evaluate whether machine-learning models provide useful predictive information beyond interpretable statistical baselines.

## Working Hypotheses

These hypotheses are provisional and will be finalized after operational definitions and the relevant literature have been reviewed.

- **H1:** Less advantaged socioeconomic conditions are associated with higher depressive-symptom scores.
- **H2:** The magnitude of socioeconomic associations differs across selected demographic groups.
- **H3:** Deterioration in socioeconomic conditions is associated with an increase in depressive-symptom scores among individuals with comparable repeated measurements.

The null hypotheses for inferential analyses will state that the relevant adjusted association or prespecified contrast is zero.

## Scope and Design

- **Country:** Indonesia.
- **Data source:** Indonesia Family Life Survey (IFLS).
- **Initial waves of interest:** IFLS4 and IFLS5.
- **Target population:** Adults meeting eligibility criteria to be specified after reviewing the survey design and outcome instrument.
- **Design:** Observational secondary-data analysis. A longitudinal component will be used only if respondent linkage and repeated-measure comparability are verified.
- **Primary outcome:** A validated depressive-symptom measure available in the relevant IFLS wave(s), potentially CES-D. The exact instrument, scoring rules, cut-offs (if any), and eligible respondents must be confirmed from official documentation.
- **Exposures:** Socioeconomic indicators such as education, employment, and household economic resources, restricted to variables confirmed in the data.
- **Covariates:** Demographic, household, and other theoretically justified confounders, selected through a documented causal/conceptual rationale and constrained by data availability.
- **Analytical approaches:** Descriptive analysis and appropriately specified regression models as primary methods; longitudinal models and machine learning as secondary approaches when their assumptions and data requirements are met.

## Conceptual Framework

The working conceptual model is:

Socioeconomic conditions → material and social circumstances → depressive symptoms

Demographic and household characteristics may influence both socioeconomic conditions and depressive symptoms and will be considered as potential confounders or effect modifiers where justified.

This framework is not a causal identification strategy by itself. Any causal interpretation would require a separate identification argument, explicit assumptions, and sensitivity analyses.

## Methodological Guardrails

1. Do not describe associations as causal effects without a defensible causal design.
2. Do not assume that a variable, instrument, respondent group, or measure exists in both waves until verified.
3. Distinguish depressive symptoms from a clinical diagnosis of depressive disorder and from broader psychological distress.
4. Do not apply a clinical cut-off unless its validity and scoring protocol are supported for the relevant population and instrument.
5. Account for the IFLS sampling design, weights, clustering, and stratification where required by the estimand and analysis.
6. Document sample restrictions, attrition, missing-data handling, and the consequences of complete-case analysis.
7. Prevent data leakage in predictive modeling; split data by respondent for repeated observations and use validation procedures appropriate to the study design.
8. Treat feature importance and explainability outputs as predictive descriptions, not evidence of causation.
9. Report uncertainty, effect sizes, model diagnostics, and sensitivity analyses rather than relying on statistical significance or accuracy alone.

## Decisions Deferred Until Data Audit

The following decisions must remain open until the official documentation and data are inspected:

- Exact outcome instrument and scoring procedure.
- Adult age threshold and respondent eligibility.
- Socioeconomic variable definitions and harmonization across waves.
- Whether the primary estimand is cross-sectional, longitudinal, or both.
- Treatment of survey weights and complex sample design.
- Final confounder set and subgroup analyses.
- Missing-data strategy and attrition analysis.
- Whether machine learning adds value beyond the statistical analysis.

## Next Step

Audit the IFLS4 and IFLS5 questionnaires, codebooks, respondent identifiers, and candidate outcome variables. Then revise this document into a data-verified protocol before implementing the analysis.
