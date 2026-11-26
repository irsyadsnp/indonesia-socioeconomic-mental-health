# IFLS4–IFLS5 Raw Data Validation: Section KP

**Project:** Indonesia Socioeconomic Factors & Mental Health  
**Stage:** 01.3 — Raw data validation  
**Status:** Structural audit completed; semantic KPTYPE discrepancy and scoring remain open  
**Audit date:** 2026-11-26  
**Input archives:** User-provided `hh07_b3b_dta.zip` and `hh14_b3b_dta.zip`  
**Scope:** Only `b3b_kp.dta) from each archive was read. No raw respondent-level records are reproduced in this report.

## 1. Executive summary

Both archives contain `b3b_kp.dta`. Each file has eight variables and ten records per unique PIDLINK. The composite key `PIDLINK + KPTYPE` has no duplicate records in either wave.

| Metric | IFLS4 | IFLS5 |
|---|---:|---:|
| File | `b3b_kp.dta` | `b3b_kp.dta` |
| Records | 290,290 | 314,470 |
| Variables | 8 | 8 |
| Unique PIDLINK | 29,029 | 31,447 |
| Records per PIDLINK | Exactly 10 | Exactly 10 |
| KPTYPE categories | A–J | A–J |
| Records per KPTYPE | 29,029 each | 31,447 each |
| Duplicate PIDLINK + KPTYPE | 0 | 0 |
| Missing PIDLINK | 0 | 0 |
| MODULE | B3B_KP throughout | B3B_KP throughout |
| Release version field | 1.0 throughout | 1.3 throughout |

**Interpretation:** The files have a balanced ten-item question-level layout. These record counts are not counts of independent item responses or a final analytic sample size.

## 2. Actual variables and storage types

### IFLS4

| Variable | Storage type | Variable label |
|---|---|---|
| `pid07` | numeric (float) | Respondent's HH member ID # |
| `kptype` | string | Type mental health |
| `kp01` | numeric (float) | In the past week did you feel |
| `kp02` | numeric (float) | How often |
| `hhid07` | string | 2007 household ID |
| `pidlink` | string | current pidlink (a00id) |
| `version` | numeric (float) | IFLS 4 release number |
| `module` | string | IFLS survey module |

### IFLS5

| Variable | Storage type | Variable label |
|---|---|---|
| `hhid14_9` | string | 2014 Household ID (9-digit) |
| `pid14` | numeric (float) | 2014 PID |
| `kptype` | string | TYPE OF KP FEELINGS |
| `kp02` | numeric (float) | How often |
| `hhid14` | string | 2014 Household ID |
| `pidlink` | string | Pidlink |
| `version` | numeric (float) | IFLS 5 release number |
| `module` | string | IFLS survey module |

The IFLS5 file contains value labels for KP02: 1 = Rarely or none (≤1 day), 2 = Some days (1–2 days), 3 = Occasionally (3–4 days), 4 = Most of the time (5–7 days), and 9 = Missing. In the read data, IFLS5 KP02 has observed values 1–4 only. IFLS4 has no embedded value-label dictionary in this file; the questionnaire and codebook provide the response interpretation.

Neither file embeds value labels for the string variable KPTYPE. Both contain the literal categories A–J.

## 3. Response distributions

### IFLS4 KP01

| Value | Count |
|---|---:|
| 1 | 92,566 |
| 3 | 197,686 |
| 9 | 38 |

### IFLS4 KP02

| Value | Count |
|---|---:|
| 1 | 12,067 |
| 2 | 13,886 |
| 3 | 31,678 |
| 4 | 34,930 |
| 9 | 43 |
| System missing | 197,686 |

All 197,686 system-missing KP02 records coincide with KP01 = 3 (No). This is consistent with the questionnaire skip pattern. It does not, by itself, establish that these records should be scored as zero.

### IFLS4 KP01 × KP02 consistency

| KP01 | KP02 = 1 | KP02 = 2 | KP02 = 3 | KP02 = 4 | KP02 = 9 | KP02 system missing |
|---|---:|---:|---:|---:|---:|---:|
| 1 | 12,067 | 13,886 | 31,678 | 34,930 | 5 | 0 |
| 3 | 0 | 0 | 0 | 0 | 0 | 197,686 |
| 9 | 5 | 0 | 0 | 0 | 38 | 0 |

There are ten discordant records involving special code 9:
- Five records have KP01 = 1 and KP02 = 9.
- Five records have KP01 = 9 and KP02 = 1.
- Thirty-eight records have KP01 = 9 and KP02 = 9.

Do not automatically recode these records. Retain flags for review and check RAND's updates/data notes and the original questionnaire/CAPI rules.

### IFLS5 KP02

| Value | Count |
|---|---:|
| 1 | 174,397 |
| 2 | 47,524 |
| 3 | 47,259 |
| 4 | 45,290 |

There are no missing KP02 values in the delivered IFLS5 `b3b_kp.dta` file.

## 4. KPTYPE structure and row uniqueness

Both waves contain exactly ten rows per PIDLINK, one for each KPTYPE value A–J.

| Validation | IFLS4 | IFLS5 |
|---|---:|---:|
| Unique PIDLINK | 29,029 | 31,447 |
| Unique PIDLINK–KPTYPE combinations | 290,290 | 314,470 |
| Duplicate PIDLINK–KPTYPE combinations | 0 | 0 |
| Missing PIDLINK | 0 | 0 |
| KPTYPE categories observed | A–J | A–J |

This confirms the physical structure of the delivered files. It does not settle the semantic discrepancy in the IFLS4 codebook labels. The data store KPTYPE as A–J strings and do not embed an item-label map. The questionnaire maps A–J to the ten printed statements, but the IFLS4 codebook's conflicting labels still require reconciliation with official updates or RAND clarification.

## 5. Cross-wave PIDLINK overlap

The set comparison of unique PIDLINK values in the two KP files gives:

| Metric | Count |
|---|---:|
| IFLS4 unique PIDLINK | 29,029 |
| IFLS5 unique PIDLINK | 31,447 |
| PIDLINK present in both files | 21,249 |
| IFLS4-only PIDLINK | 7,780 |
| IFLS5-only PIDLINK | 10,198 |
| Shared / IFLS4 PIDLINK | 73.20% |
| Shared / IFLS5 PIDLINK | 67.57% |

This is a direct identifier-set overlap between the two delivered KP files, not a completed attrition analysis. It does not yet account for survey eligibility, weights, death, migration, interview status, or other tracking outcomes. The tracking files and survey documentation must be used before defining the longitudinal analysis sample.

## 6. KPTYPE item-label discrepancy: remains unresolved

The raw files confirm that KPTYPE is stored as A–J and that all ten categories are present in each wave. They do not contain embedded value labels for KPTYPE.

The IFLS4 English and Bahasa Indonesia questionnaires print the same ten A–J statements as IFLS5. However, the IFLS4 B3B codebook labels list a different set of statements. Because the raw data contain only letter codes and no semantic value labels, the raw file alone cannot adjudicate which item-label documentation is correct.

Required resolution:
1. Review IFLS4 updates and data notes for B3B_KP/KPTYPE corrections.
2. Compare the official codebook file against the exact delivered data release version.
3. If unresolved, request clarification from RAND.
4. Preserve the discrepancy in the data dictionary until documented.

Do not use the disputed IFLS4 codebook labels as item meanings, and do not silently assume the questionnaire mapping is fully verified at the data-release level.

## 7. Decisions

### Approved
- Read `b3b_kp.dta` from each supplied B3B archive.
- Treat each file as a ten-row-per-person question-level file.
- Use `PIDLINK` as the candidate person-level cross-wave identifier, subject to tracking-file verification.
- Treat `PIDLINK + KPTYPE` as the observed unique row key in these files.
- Keep the raw source archives outside the public GitHub repository.

### Not approved yet
- CES-D scoring or total-score derivation.
- Recoding IFLS4 KP01 = 3 to zero.
- Automatic recoding of special code 9.
- Final semantic mapping of IFLS4 KPTYPE labels.
- Final longitudinal sample definition.
- Survey-weighted estimation or population inference.
- Causal interpretation.

## 8. Next steps

1. Inspect IFLS4 and IFLS5 updates/data notes, especially any correction for B3B_KP or KPTYPE.
2. Confirm the IFLS4 codebook discrepancy with RAND if the updates do not resolve it.
3. Inspect the two tracking files and validate PIDLINK linkage, panel status, and attrition.
4. Audit the B3A, B1, and B2 codebooks before defining socioeconomic exposures.
5. Only after instrument and sample rules are resolved, create a reproducible scoring specification and a wave-harmonized analysis dataset.

## 9. Reproducibility and privacy

This report contains aggregate validation statistics only. It intentionally excludes respondent-level rows and raw identifiers. Raw IFLS data must remain local and must not be committed to this public GitHub repository.

---
*Validation was performed on the two user-supplied ZIP archives by reading only `b3b_kp.dta` from each. The results describe the supplied archive contents and release versions; they do not establish that the archives are the latest RAND release.*
