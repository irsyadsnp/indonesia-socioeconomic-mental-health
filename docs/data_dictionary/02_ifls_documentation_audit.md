# IFLS4–IFLS5 Documentation Audit

**Audit stage:** 05-A — source and documentation architecture  
**Status:** Partially completed. Official documentation structure and critical audit rules have been identified. Variable-level verification is pending inspection of the downloaded documentation and data files.

## 1. Audit Objective

Establish an evidence trail from each research construct to the official IFLS questionnaire item, codebook entry, source data file, respondent universe, and verified variable.

This audit must be performed separately for IFLS4 and IFLS5. Similar labels or variable names do not establish measurement equivalence.

## 2. Authoritative Documentation Sources

The primary source is the RAND IFLS Data and Documentation page:

- RAND IFLS Data and Documentation: https://www.rand.org/health/surveys/FLS/IFLS/download.html
- RAND IFLS Data Updates, Notes, Tips, and FAQs: https://www.rand.org/health/surveys/FLS/IFLS/datanotes.html
- RAND IFLS data access and registration: https://www.rand.org/health/surveys/FLS/IFLS/access.html

The official documentation series identified for the two candidate waves is:

| Wave | Publication series | Required documentation |
|---|---|---|
| IFLS4 (2007–2008) | WR-675 | Overview/field report; User's Guide; household questionnaire; community-facility questionnaire; household codebook; community-facility codebook |
| IFLS5 (2014–2015) | WR-1143 | Overview/field report; User's Guide; household questionnaire; community-facility questionnaire; household codebook; community-facility codebook |

Relevant overview references:
- IFLS4: Strauss, Witoelar, Sikoki, and Wattie. *The Fourth Wave of the Indonesian Family Life Survey (IFLS4): Overview and Field Report*. April 2009. WR-675/1-NIA/NICHD.
- IFLS5: Strauss, Witoelar, and Sikoki. *The Fifth Wave of the Indonesia Family Life Survey (IFLS5): Overview and Field Report*. March 2016. WR-1143/1-NIA/NICHD.

The RAND documentation page states that users should read both volumes of the User's Guide and review the questionnaires before working with the data. It also advises consulting earlier-wave documentation when exploiting the longitudinal structure because information and event histories are not necessarily repeated in every wave.

## 3. Confirmed Documentation-Level Findings

The official RAND documentation page establishes several rules that directly affect this project:

1. **Different units of observation exist.** Files may represent individuals, households, events, or multiple records for one respondent. The unit of observation and record identifiers must be checked before merging.
2. **Questionnaire skip patterns are extensive.** A blank value can mean that a respondent was not eligible for a question. It must not automatically be classified as ordinary item nonresponse.
3. **Missing-value codes require interpretation.** Refusal, don't know, and other nonresponse codes must be distinguished from structural skips and not-applicable responses.
4. **Wave documentation is not interchangeable.** Questionnaire content and documentation can change between waves. Earlier-wave documentation may be needed even when the analysis focuses on a later wave.
5. **Data structure must be inspected directly.** Codebook descriptions and frequency tables alone are not sufficient to establish record structure or merge validity.

These are documentation-level findings. They do not yet verify any specific depressive-symptom, education, employment, income, expenditure, or asset variable.

## 4. Project-Specific Documentation Inventory

The following inventory records the source materials that must be inspected. Exact local filenames and extracted contents must be confirmed against the user's downloaded packages.

| Material | IFLS4 source | IFLS5 source | Audit status |
|---|---|---|---|
| Overview and field report | WR-675/1 | WR-1143/1 | SOURCE IDENTIFIED; CONTENT REVIEW PENDING |
| User's Guide, Volume 1 | WR-675/2 series documentation | WR-1143/2 series documentation | CONTENT REVIEW PENDING |
| User's Guide, Volume 2 | Included in wave guide series / package | Included in wave guide series / package | CONTENT REVIEW PENDING |
| Household questionnaire | WR-675/3 | WR-1143/3 | CONTENT REVIEW PENDING |
| Community-facility questionnaire | WR-675/4 | WR-1143/4 | CONTENT REVIEW PENDING |
| Household codebook | WR-675/5 | WR-1143/5 | CONTENT REVIEW PENDING |
| Community-facility codebook | WR-675/6 | WR-1143/6 | CONTENT REVIEW PENDING |
| Data update notes and FAQs | RAND IFLS data notes page | RAND IFLS data notes page | REVIEW REQUIRED |

**Note:** The exact volume packaging and filenames must be checked against the downloaded archive. Do not infer a volume's contents from a local filename alone.

## 5. Variable Domains to Audit First

The order below prioritizes the feasibility of the research question. It is not a claim that the constructs are present in either wave.

| Priority | Domain | Required evidence |
|---|---|---|
| 1 | Depressive-symptom outcome | Exact instrument, item wording, response scale, reference period, respondent eligibility, scoring and missing-item rules |
| 2 | Education | Exact attainment item, coding, respondent universe, timing |
| 3 | Employment | Employment status and/or work characteristics, reference period, eligibility |
| 4 | Household economic resources | Exact income, expenditure, consumption, or asset measure; aggregation and reference period |
| 5 | Demographics | Exact age and sex variables, category definitions, interview timing |
| 6 | Household and geographic context | Unit of observation, identifiers, urban/rural definitions and access restrictions |
| 7 | Potential confounders and mediators | Exact item, temporal ordering, and theoretical role |
| 8 | Survey design | Weights, strata, clusters, sample design and wave-specific guidance |

## 6. Required Audit Procedure

For every candidate variable and each wave:

1. Locate the relevant questionnaire module and exact question.
2. Record question wording, item number, response options, reference period, and skip instructions.
3. Identify the intended respondent and eligibility universe.
4. Locate the matching codebook entry.
5. Record the exact data filename, variable name, label, type, and value labels.
6. Inspect the actual data file to verify the variable exists and understand its record grain.
7. Inspect special missing codes, structural skips, distributions, and plausible ranges.
8. Identify the correct person, household, or event keys for linkage.
9. Compare the item, respondent universe, response scale, timing, and coding across waves.
10. Assign a verification status and cite the exact source page, section, or codebook entry.

## 7. Evidence and Verification Labels

Use the following labels independently for IFLS4 and IFLS5:

- **NOT REVIEWED:** source has not been inspected.
- **CANDIDATE:** construct identified, exact item not confirmed.
- **DOCUMENTED:** official questionnaire and codebook identify the item and variable.
- **DATA VERIFIED:** variable exists in the corresponding data file and its values/codes have been inspected.
- **COMPARABILITY VERIFIED:** wave-specific measurement, eligibility, coding, and timing have been assessed.
- **EXCLUDED:** unsuitable or unavailable, with reason documented.

Do not upgrade a variable to DATA VERIFIED using a codebook alone. Do not upgrade it to COMPARABILITY VERIFIED merely because both waves contain a similarly named variable.

## 8. Data Security and Repository Rules

- Do not commit IFLS microdata, respondent-level extracts, credentials, or restricted-use geographic coordinates to this repository.
- Do not redistribute IFLS data packages. Follow RAND's registration, access, citation, and confidentiality requirements.
- Keep raw data outside the public Git repository.
- Commit only research documentation, reproducible code, non-disclosive metadata, and permitted derived outputs.
- Check the repository's ignore rules before placing any local data or temporary extracts in the project directory.

## 9. Current Audit Result and Blocking Dependency

**Completed:** official source hierarchy identified; wave-specific publication series recorded; key rules concerning units of observation, skip patterns, missing codes, and longitudinal documentation recorded.

**Not completed:** exact variable mapping, questionnaire page references, codebook entries, actual data-file verification, and cross-wave comparability.

The IFLS documentation and data archives previously reported as downloaded are not currently present as readable files in this ChatGPT Library. The only accessible project source found here is a saved copy of the RAND download-page HTML. Therefore, no variable-level findings are claimed in this audit.

### Required input to complete Stage 05-B

Make the downloaded documentation archives available in this conversation, starting with:
1. IFLS4 documentation archive (the package reported as `hh07_all_doc`).
2. IFLS5 documentation archive (the package reported as `IFLS5_all_doc`).

If the archives are too large, upload the relevant household questionnaire and household codebook files for both waves first. Do not upload or commit the raw respondent-level data archives at this stage.

Once the documentation is available, populate the variable-mapping register with exact question wording, source file, variable name, codebook evidence, respondent universe, and wave-specific verification status.

## 10. Source References

- RAND. IFLS Data and Documentation: https://www.rand.org/health/surveys/FLS/IFLS/download.html
- RAND. IFLS Data Updates, Notes, Tips, and FAQs: https://www.rand.org/health/surveys/FLS/IFLS/datanotes.html
- Strauss, J., Witoelar, F., Sikoki, B., and Wattie, A. (2009). *The Fourth Wave of the Indonesian Family Life Survey (IFLS4): Overview and Field Report*. WR-675/1-NIA/NICHD.
- Strauss, J., Witoelar, F., and Sikoki, B. (2016). *The Fifth Wave of the Indonesia Family Life Survey (IFLS5): Overview and Field Report*. WR-1143/1-NIA/NICHD.
