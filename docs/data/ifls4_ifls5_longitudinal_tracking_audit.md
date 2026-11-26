# IFLS4–IFLS5 Longitudinal Tracking Audit

**Status:** Completed initial tracking audit; analytic cohort and survey-weight specification remain provisional.  
**Scope:** Person tracking (PTRACK), household tracking (HTRACK), and linkage to the previously audited `B3B_KP` respondent files.  
**Waves:** IFLS4 (2007–2008) and IFLS5 (2014–2015).  
**Privacy:** This report contains aggregate counts only. No respondent IDs, household IDs, row-level records, or raw IFLS data are stored in this repository.

## 1. Files and documentation inspected

The following tracking files were read from the supplied archives:

- IFLS4 `ptrack.dta` and `htrack.dta` (release version 1.0).
- IFLS5 `ptrack.dta` and `htrack.dta` (release version 1.3).

Documentation inspected:

- IFLS4 codebooks: `ifls2007_hhd_PTRACK.txt` and `ifls2007_hhd_HTRACK.txt`, from `hh07_all_doc.zip`.
- IFLS5 codebooks: `ifls2014_hhd_PTRACK.txt` and `ifls2014_hhd_HTRACK.txt`, from `IFLS5_hh_codebooks.zip` nested in `IFLS5_all_doc.zip`.

The codebooks designate `PIDLINK` as the key for linking people across waves. They explicitly caution against linking respondents across waves using wave-specific household/person identifiers (HHID/PID), because people can move to split-off households and receive different identifiers. `MEMBER93`–`MEMBER14` indicate whether a person was found in a given wave.

## 2. PTRACK structural validation

| Check | IFLS4 PTRACK | IFLS5 PTRACK |
|---|---:|---:|
| Rows | 66,784 | 83,780 |
| Unique non-missing PIDLINK | 66,784 | 83,777 |
| Missing PIDLINK | 0 | 0 |
| Duplicate PIDLINK rows | 0 | 6 (3 groups) |
| Release version | 1.0 | 1.3 |

IFLS4 PTRACK has one row per PIDLINK. IFLS5 PTRACK contains three duplicated PIDLINK groups. One group is an exact duplicate; two groups differ in 2014 household/person identifiers and associated 2014 weights. These rows were not automatically deduplicated. None of the three duplicated PIDLINKs occurs in the audited IFLS5 `B3B_KP` respondent set, but the duplicate issue must be resolved before using the full IFLS5 PTRACK file in a general person-level merge.

## 3. Linkage to B3B_KP respondent files

Every PIDLINK in each previously audited `B3B_KP` file is present in the corresponding PTRACK file.

| Measure | IFLS4 (2007) | IFLS5 (2014) |
|---|---:|---:|
| B3B_KP respondents (unique PIDLINK) | 29,029 | 31,447 |
| B3B_KP IDs found in PTRACK | 29,029 | 31,447 |
| B3B_KP IDs absent from PTRACK | 0 | 0 |
| Marked current household member in that wave | 29,029 | 31,445 |
| Not marked current household member in that wave | 0 | 2 |

The two IFLS5 records marked `MEMBER14=0` should be investigated before defining the final 2014 analytic sample. The other IFLS5 B3B_KP respondents are marked as current household members in 2014.

### Book 3B completion-status cross-check

The PTRACK status variables are `RES07B3B` and `RES14B3B`. The codebooks define 1 as complete, 2 as partially complete, and 3 as not completed.

Among the linked B3B_KP respondent IDs:

| PTRACK status | IFLS4 RES07B3B | IFLS5 RES14B3B |
|---|---:|---:|
| 1 — Complete | 29,012 | 31,394 |
| 2 — Partially complete | 14 | 50 |
| 3 — Not completed | 0 | 3 |
| Missing | 3 | 0 |
| **Total linked B3B_KP IDs** | **29,029** | **31,447** |

These counts do not exactly match the aggregate PTRACK codebook frequencies. In IFLS4, the full PTRACK codebook reports 29,014 complete, 16 partially complete, and 936 not completed; the raw B3B_KP respondent set has three IDs with missing PTRACK status and does not include two PTRACK-complete and two PTRACK-partial IDs. In IFLS5, the full PTRACK codebook reports 34,201 complete, 69 partially complete, and 2,118 not completed; the B3B_KP respondent set includes three IDs marked not completed, while many PTRACK Book 3B records are not present in the KP-specific file.

This is a reconciliation issue between book-level tracking status and the KP-section data extract. Do not use `RES07B3B` or `RES14B3B` alone as a substitute for checking the actual KP-section respondent records. Do not silently drop or recode the discordant records.

## 4. Cross-wave overlap of KP respondents

Linkage was performed using PIDLINK only.

| Group | Unique respondents |
|---|---:|
| IFLS4 B3B_KP respondents | 29,029 |
| IFLS5 B3B_KP respondents | 31,447 |
| Present in both B3B_KP respondent files | 21,249 |
| IFLS4 only | 7,780 |
| IFLS5 only | 10,198 |

The shared set is 73.20% of the IFLS4 KP respondent set and 67.57% of the IFLS5 KP respondent set. These are **observed respondent-set overlap proportions**, not attrition rates. They must not be described as attrition without accounting for survey eligibility, household/person tracking outcomes, split-offs, deaths, nonresponse, and the target population.

For the 21,249 shared KP respondents, IFLS5 PTRACK reports:

- `MEMBER07=1` for all 21,249.
- `RES07B3B=1` for 21,241.
- `RES07B3B=2` for 6.
- `RES07B3B` missing for 2.

The two missing status values are unresolved and should be checked against the relevant release documentation and raw records before final inclusion rules are set.

### IFLS5 KP respondents not present in IFLS4 KP

Of the 10,198 IFLS5 KP respondents absent from the IFLS4 KP respondent set:

- 5,222 are marked `MEMBER07=0`.
- 4,976 are marked `MEMBER07=1`.
- `RES07B3B` is missing for 9,909, is 3 for 288, and is 2 for 1.

Therefore, the IFLS5-only group is not a homogeneous “new entrant” group. It includes people not marked as current household members in 2007 and people who were members in 2007 but do not appear in the 2007 KP respondent file. The reason for each case is not established by these aggregate counts.

### IFLS4 KP respondents not present in IFLS5 KP

The 7,780 IFLS4 KP respondents absent from the IFLS5 KP respondent set are still represented in IFLS5 PTRACK. Within this group:

- 2,574 are marked `MEMBER14=1`; 5,206 are marked `MEMBER14=0`.
- `RES14B3B` is 1 for 1,505, 2 for 11, 3 for 994, and missing for 5,270.
- `DIED07=0` and `CONTACTALIVE07=1` are recorded for 7,778; two records have missing values.

This confirms that absence from the 2014 KP-specific file must not be equated with death or loss to follow-up. In particular, some individuals have a non-missing 2014 Book 3B tracking status but are not in the KP-specific respondent extract. The distinction between book completion, KP-section participation, current household membership, and survey follow-up needs further documentation review.

## 5. HTRACK household-level context

HTRACK is a household-level tracking file. Its counts must not be mixed with person-level PTRACK counts or treated as the analytic sample size.

### IFLS4 HTRACK

There are 15,146 rows. `RESULT07` is documented as the 2007 household interview result:

| RESULT07 | Codebook meaning | Count |
|---:|---|---:|
| 1 | Interviewed | 13,270 |
| 2 | Joined other household | 301 |
| 3 | All target members dead | 167 |
| 4 | Refused | 300 |
| 5 | Not found | 973 |
| Missing | Missing | 135 |

### IFLS5 HTRACK

There are 19,401 rows. `RESULT14` is documented as the 2014 household interview result:

| RESULT14 | Codebook meaning | Count |
|---:|---|---:|
| 1 | Interviewed | 15,921 |
| 2 | Refused | 199 |
| 3 | Joined with other IFLS household | 485 |
| 4 | Died | 386 |
| 5 | Household unavailable/not found | 1,069 |
| 6 | Household not yet interviewed | 88 |
| 8 | Moved out household confirmation | 129 |
| Missing | Missing | 1,124 |

The IFLS5 codebook also identifies `SPLITOFF07` and `SPLITOFF14`. These variables support the need to account for split-off households when interpreting household tracking and longitudinal follow-up. Household-level interview outcomes do not directly determine whether an individual completed the KP section.

## 6. Survey-weight availability observed in the KP respondent sets

Non-missing weight availability in the linked KP respondent sets:

| Weight variable | IFLS4 non-missing | IFLS5 non-missing | Codebook description / caution |
|---|---:|---:|---|
| `PWT07XA` | 29,027 / 29,029 | — | IFLS4 person cross-sectional weight with attrition correction |
| `PWT07X_` | 29,027 / 29,029 | — | IFLS4 person cross-sectional weight without attrition correction |
| `PWT07LA` | 21,598 / 29,029 | — | IFLS4 longitudinal weight for 1993 household members found in 2007 |
| `PWT14XA` | — | 31,445 / 31,447 | IFLS5 cross-sectional member weight with attrition correction |
| `PWT14X_` | — | 31,445 / 31,447 | IFLS5 cross-sectional member weight without attrition correction |
| `PWT14LA` | — | 17,983 / 31,447 | IFLS5 person longitudinal weight for 1993 household members found in 2014, with attrition correction |
| `PWT_5_WAVES_L` | — | 10,362 / 31,447 | IFLS5 longitudinal weight for being interviewed in all five waves, with attrition |
| `PWT_5_WAVES_LR` | — | 15,068 / 31,447 | IFLS5 longitudinal weight for being in the roster in all five waves, with attrition correction |
| `PWT_5_WAVES_USL` | — | 10,436 / 31,447 | IFLS5 longitudinal weight for being measured in all five waves, with attrition correction |

Weight availability is not proof that a weight is appropriate for the proposed estimand. These variables target different populations and follow-up histories. In particular, the five-wave weights do not automatically represent a two-wave 2007–2014 KP respondent panel. The final weight, strata, PSU, and variance-estimation specification must be selected only after the target population and estimand are defined and the relevant survey documentation is checked. Do not substitute cross-sectional weights for a longitudinal weight without justification.

## 7. Implications for study design

1. Use `PIDLINK` for person-level linkage across IFLS waves. Do not use wave-specific HHID/PID as a cross-wave key.
2. Define the paired KP respondent cohort by the observed intersection of the two KP respondent ID sets (21,249 before item-level exclusions), then apply transparent eligibility and missing-data rules.
3. Keep cross-sectional analyses separate from paired longitudinal analyses. The full IFLS4 and IFLS5 KP samples are not identical populations.
4. Do not call the 7,780 IFLS4-only KP respondents “deceased” or “attrited”; PTRACK shows that most have `DIED07=0` and `CONTACTALIVE07=1`, while 2014 household membership and Book 3B status vary.
5. Do not classify all 10,198 IFLS5-only KP respondents as new entrants. Nearly half are marked `MEMBER07=1`.
6. Resolve the small KP/PTRACK status discrepancies and IFLS5 duplicate PIDLINK records before constructing reusable tracking tables.
7. Do not finalize survey weights until the target population, panel definition, and design variables are established.
8. The KP measure remains a symptom/indicator measure, not a clinical diagnosis. This tracking audit does not validate the instrument, scoring, or cross-wave measurement invariance.

## 8. Outstanding issues

- Reconcile the IFLS4 and IFLS5 book-level PTRACK completion flags against the KP-specific extracts.
- Investigate the three IFLS5 PTRACK duplicate PIDLINK groups; do not deduplicate by arbitrary first/last-row selection.
- Investigate the two IFLS5 KP respondents with `MEMBER14=0`.
- Review why some 2007 KP respondents have 2014 Book 3B completion status but are absent from the 2014 KP extract.
- Confirm the exact longitudinal target population and appropriate person weights, strata, PSU, and variance estimation from official documentation.
- Establish whether IFLS4/IFLS5 KP item comparability and the previously documented IFLS4 KPTYPE codebook discrepancy can be resolved. This tracking audit does not resolve that instrument issue.

## 9. Reproducibility and data governance

The audit was performed on the supplied IFLS4 and IFLS5 tracking and KP archives. Only aggregate statistics and methodological notes are recorded here. Raw Stata files and respondent-level identifiers must remain outside this public repository. Any future scripts should read local, ignored data files and must not commit raw or row-level IFLS data.

---

**Audit conclusion:** The official PIDLINK linkage is operational and yields 21,249 shared KP respondents across IFLS4 and IFLS5. This is a viable candidate paired cohort, not yet a finalized analytic sample. The book-status discrepancies, IFLS5 duplicate PTRACK IDs, item-level missingness, instrument comparability, and longitudinal weight specification remain open before analysis.
