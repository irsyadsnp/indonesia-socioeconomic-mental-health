# IFLS4–IFLS5 KP Item-Level Response and Comparability Audit

**Stage:** 01.6  
**Status:** Response-pattern audit completed; cross-wave item mapping and score construction are not approved.  
**Population for paired descriptive checks:** 21,249 people present in both IFLS4 and IFLS5 KP respondent extracts.  
**Data governance:** Only aggregate item counts are reported. No respondent IDs or row-level data are included.

## 1. Objective and source files

This audit examines item-level response structure in `B3B_KP` for the 21,249 shared PIDLINK respondents. It checks:

- whether each respondent has the expected A–J item rows;
- IFLS4 screening (`KP01`) and frequency (`KP02`) patterns;
- IFLS5 frequency (`KP02`) patterns;
- missing and out-of-range response codes;
- whether the item codes can safely be treated as semantically equivalent across waves.

Files inspected locally:

- IFLS4 `b3b_kp.dta`, release 1.0.
- IFLS5 `b3b_kp.dta`, release 1.3.

Documentation inspected:

- IFLS4 and IFLS5 B3B codebooks.
- IFLS4 English and Bahasa questionnaire versions and IFLS5 English B3B questionnaire, as recorded in the documentation audit.

## 2. Structure and paired respondent coverage

| Check | IFLS4 | IFLS5 |
|---|---:|---:|
| Paired respondents | 21,249 | 21,249 |
| KP rows | 212,490 | 212,490 |
| Rows per respondent | 10 | 10 |
| KPTYPE values | A–J | A–J |
| Rows per KPTYPE | 21,249 each | 21,249 each |
| Missing PIDLINK | 0 | 0 |
| Duplicate PIDLINK–KPTYPE | 0 | 0 |

The structure is balanced: every paired respondent has exactly one record for each of the ten KPTYPE codes in each wave. This establishes structural coverage, not semantic equivalence of the item labels.

## 3. IFLS4 screening and frequency responses

IFLS4 uses two variables:

- `KP01`: whether the respondent experienced the feeling in the past week (1 = Yes, 3 = No, 9 = Missing).
- `KP02`: frequency (1 = Rarely, 2 = Some days, 3 = Occasionally, 4 = Most of the time, 9 = Missing).

Across all 212,490 paired-respondent item records:

| KP01 | Count |
|---:|---:|
| 1 — Yes | 67,441 |
| 3 — No | 145,048 |
| 9 — Missing | 1 |
| **Total** | **212,490** |

`KP02` distribution:

| KP02 | Meaning | Count |
|---:|---|---:|
| 1 | Rarely (≤1 day) | 8,719 |
| 2 | Some days (1–2 days) | 9,795 |
| 3 | Occasionally (3–4 days) | 23,118 |
| 4 | Most of the time (5–7 days) | 25,808 |
| 9 | Missing | 2 |
| System missing | Skip / no frequency value | 145,048 |
| **Total** | | **212,490** |

The 145,048 system-missing KP02 values coincide with KP01=3. This is consistent with the documented screening/skip pattern. However, the raw paired data also contain two discordant missing-code records: one KP01=1 with KP02=9 and one KP01=9 with KP02=9. These must remain flagged; do not silently recode them.

### 3.1 IFLS4 screening by item code

| KPTYPE | KP01=1 Yes | KP01=3 No | KP01=9 Missing |
|---|---:|---:|---:|
| A | 2,690 | 18,559 | 0 |
| B | 3,845 | 17,404 | 0 |
| C | 2,848 | 18,401 | 0 |
| D | 7,479 | 13,770 | 0 |
| E | 19,169 | 2,080 | 0 |
| F | 3,282 | 17,967 | 0 |
| G | 5,747 | 15,501 | 1 |
| H | 19,531 | 1,718 | 0 |
| I | 1,251 | 19,998 | 0 |
| J | 1,599 | 19,650 | 0 |

The distribution differs substantially by item code. This is a descriptive observation only; because the IFLS4 KPTYPE label conflict remains unresolved, these letters must not yet be assigned the IFLS5 item meanings.

## 4. IFLS5 frequency responses

IFLS5 records `KP02` frequency directly in the delivered KP extract. The observed paired-respondent counts are:

| KPTYPE | 1 Rarely / none | 2 Some days | 3 Occasionally | 4 Most of the time |
|---|---:|---:|---:|---:|
| A | 14,155 | 3,277 | 2,920 | 897 |
| B | 14,123 | 3,351 | 2,921 | 854 |
| C | 16,074 | 2,455 | 1,935 | 785 |
| D | 12,352 | 3,192 | 3,110 | 2,595 |
| E | 2,724 | 3,516 | 4,750 | 10,259 |
| F | 15,058 | 2,803 | 2,336 | 1,052 |
| G | 13,277 | 2,509 | 3,116 | 2,347 |
| H | 1,879 | 3,673 | 5,969 | 9,728 |
| I | 17,452 | 1,548 | 1,556 | 693 |
| J | 15,906 | 2,121 | 2,361 | 861 |

Each IFLS5 KPTYPE row sums to 21,249. No KP02 missing codes or system-missing values were observed in the paired subset of the delivered IFLS5 KP extract. This is a property of the delivered extract, not proof that no item nonresponse occurred elsewhere in the survey.

## 5. Critical cross-wave instrument discrepancy

The item code sequence A–J exists in both data files, but the IFLS4 and IFLS5 codebook descriptions are not consistent.

### 5.1 IFLS4 questionnaire versus IFLS4 codebook

The IFLS4 English and Bahasa questionnaire versions inspected in the documentation audit list the ten Section KP prompts in the same sequence as the IFLS5 questionnaire:

A. Bothered by things that usually do not bother the respondent  
B. Trouble concentrating  
C. Felt depressed  
D. Everything done was an effort  
E. Hopeful about the future  
F. Fearful  
G. Sleep was restless  
H. Happy  
I. Lonely  
J. Could not get going

However, the IFLS4 B3B codebook's `KPTYPE` value descriptions list a different sequence:

A. Bothered by things that usually do not bother the respondent  
B. Did not feel like eating / appetite was poor  
C. Could not shake off the blues  
D. Felt as good as other people  
E. Everything done was an effort  
F. Hopeful about the future  
G. Thought life had been a failure  
H. Fearful  
I. Happy  
J. Talked less than usual

The IFLS4 Stata `b3b_kp.dta` file stores `KPTYPE` as A–J and does not embed value labels that resolve this discrepancy. The raw data alone therefore cannot establish whether the IFLS4 codebook descriptions are stale/mismatched or whether the questionnaire documentation does not represent the exact instrument administered to all respondents.

### 5.2 IFLS5 codebook

The IFLS5 codebook's KPTYPE A–J descriptions match the ten-item sequence listed in the IFLS5 questionnaire and in the IFLS4 questionnaire versions inspected.

### 5.3 Consequence

Do **not** map IFLS4 KPTYPE letters to IFLS5 item meanings solely by their letter codes. Do not calculate a combined score, reverse-code selected items, or claim longitudinal measurement invariance until the IFLS4 codebook-versus-questionnaire discrepancy is resolved from an authoritative release clarification or other primary documentation.

The questionnaire text comparison is evidence about the documented instrument. It does not, by itself, prove which exact item wording was administered in every IFLS4 interview.

## 6. Screening difference and missing-data implications

IFLS4 uses KP01 screening before KP02 frequency, while IFLS5's delivered KP extract contains KP02 directly. Therefore:

1. IFLS4 KP01=3 with system-missing KP02 is a documented skip pattern, not ordinary item nonresponse.
2. IFLS4 KP01=1 with KP02=9 and KP01=9 with KP02=9 are discordant records and must be retained as flagged until adjudicated.
3. IFLS5 KP02 values 1–4 in this paired extract do not establish that its measurement process is identical to IFLS4's screening-plus-frequency process.
4. Do not automatically convert IFLS4 KP01=3 into KP02=1. The questionnaire and codebook need to establish whether the screening response means the same thing as the IFLS5 lowest frequency category ("Rarely or none").
5. Do not treat structural skips, explicit missing codes, and absent records as one undifferentiated missing category.

## 7. Decisions

Provisional decisions for the project:

- Structural completeness of the paired KP extract is confirmed: 21,249 people × 10 item rows per wave.
- The paired set remains a candidate cohort, not yet a scored analytic sample.
- Preserve original KP01 and KP02 values; do not recode or score them at this stage.
- Retain KPTYPE as a raw categorical code until the IFLS4 label discrepancy is resolved.
- Report IFLS4 and IFLS5 item distributions separately in descriptive work until semantic mapping is justified.
- Do not call the measure a clinical diagnosis.
- No cut-off, reverse coding, total score, or cross-wave invariance claim is approved by this audit.

## 8. Required next action

Before constructing a psychological-distress score, obtain authoritative clarification of the IFLS4 KPTYPE discrepancy and confirm the relationship between the IFLS4 screening response and IFLS5's frequency response. The appropriate next task is a focused primary-documentation/release-note investigation. If no authoritative clarification is available, the analysis plan must be revised to avoid unsupported cross-wave item equivalence.

## 9. Reproducibility and data governance

The audit used local copies of the supplied Stata archives. Only aggregate counts and methodological notes are recorded in this public repository. Raw IFLS files and respondent-level identifiers remain local and must not be committed. Any future analysis code must preserve raw values, document recodes explicitly, and keep row-level outputs outside version control.

---

**Conclusion:** The paired KP extracts are structurally complete for 21,249 people in both waves, but this does not establish longitudinal comparability. The unresolved IFLS4 KPTYPE codebook-versus-questionnaire discrepancy and the different IFLS4/IFLS5 screening structures block defensible score construction. No score or model should be built until these issues are addressed.
