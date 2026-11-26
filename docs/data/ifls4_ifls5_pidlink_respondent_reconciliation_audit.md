# IFLS4–IFLS5 PIDLINK and Respondent Reconciliation Audit

**Stage:** 01.5  
**Status:** Aggregate reconciliation completed; case-level adjudication and analytic inclusion rules remain open.  
**Repository:** `irsyadsnp/indonesia-socioeconomic-mental-health`

## 1. Purpose

This audit reconciles the person tracking files (`PTRACK`) with the Section KP respondent extracts (`B3B_KP`) for IFLS4 (2007–2008) and IFLS5 (2014–2015). It investigates whether a person appearing in one KP extract but not the other can be classified using tracking status and household membership indicators.

All linkage uses `PIDLINK`. No respondent-level identifiers or row-level records are included in this report.

## 2. Source and key definitions

Files inspected locally:

- IFLS4: `ptrack.dta`, `b3b_kp.dta`
- IFLS5: `ptrack.dta`, `b3b_kp.dta`

Documentation inspected:

- IFLS4 `ifls2007_hhd_PTRACK.txt` from the supplied `hh07_all_doc.zip`.
- IFLS5 `ifls2014_hhd_PTRACK.txt` from the nested `IFLS5_hh_codebooks.zip` inside `IFLS5_all_doc.zip`.

The codebooks describe `PIDLINK` as the person-level key for linking individuals across waves. `MEMBER07` and `MEMBER14` indicate whether a person was found as a current resident in the corresponding wave. `RES07B3B` and `RES14B3B` record Book 3B completion status: 1 = complete, 2 = partially complete, 3 = not completed; missing values are also present.

Important distinction: Book 3B completion status is not a direct flag for whether a particular Section KP record is present in the KP-specific data extract. Similarly, current household membership is not itself a measure of interview completion.

## 3. Integrity checks

### 3.1 Section KP files

- IFLS4 `B3B_KP`: 290,290 rows; 29,029 unique PIDLINK; exactly 10 rows per person (KPTYPE A–J).
- IFLS5 `B3B_KP`: 314,470 rows; 31,447 unique PIDLINK; exactly 10 rows per person (KPTYPE A–J).
- No missing PIDLINK values or duplicate PIDLINK–KPTYPE combinations were observed in either KP extract.

### 3.2 PTRACK files

- IFLS4 PTRACK: 66,784 rows and 66,784 unique PIDLINK values; no duplicate PIDLINK.
- IFLS5 PTRACK: 83,780 rows and 83,777 unique PIDLINK values; three duplicated PIDLINK groups (six rows).

The three IFLS5 duplicate groups were inspected without exposing their identifiers:
- One group consists of two identical rows.
- One group differs in `HHID14`.
- One group differs in `HHID14`, `PID14`, and three DBS-related weight variables (`PWT14DBSXA`, `PWT14DBSX_`, `PWT14DBSLA`).

None of these three duplicated PIDLINK groups occurs in the IFLS5 KP respondent set. They must nevertheless be resolved before a general person-level PTRACK merge is used. No arbitrary first-row/last-row deduplication was performed.

### 3.3 KP-to-PTRACK linkage

Every unique PIDLINK in each KP extract is present in the corresponding PTRACK file:

| Check | IFLS4 | IFLS5 |
|---|---:|---:|
| Unique KP respondent PIDLINK | 29,029 | 31,447 |
| Found in corresponding PTRACK | 29,029 | 31,447 |
| Not found in PTRACK | 0 | 0 |

Thus, the person-level linkage key is operational for the KP respondent extracts.

## 4. Reconciliation of KP extract presence with PTRACK status

### 4.1 IFLS4 KP respondents against IFLS4 PTRACK

All 29,029 IFLS4 KP respondents have `MEMBER07=1`. Their `RES07B3B` distribution is:

| RES07B3B | Meaning | KP respondents |
|---:|---|---:|
| 1 | Complete | 29,012 |
| 2 | Partially complete | 14 |
| 3 | Not completed | 0 |
| Missing | Missing | 3 |
| **Total** | | **29,029** |

The full IFLS4 PTRACK codebook reports 29,014 complete, 16 partially complete, and 936 not completed (plus 36,818 missing) for `RES07B3B`. The KP extract contains 29,012 of the PTRACK-complete records and 14 of the PTRACK-partial records, while three KP respondent IDs have missing completion status. The two complete and two partial PTRACK records not represented in the KP respondent extract, together with the three missing-status KP records, require record-level review against the release documentation and source files.

Do not infer that a row in the KP-specific extract proves the entire Book 3B was completed, or that the tracking status is necessarily wrong. These are distinct data products and their relationship needs clarification.

### 4.2 IFLS5 KP respondents against IFLS5 PTRACK

| RES14B3B | Meaning | KP respondents |
|---:|---|---:|
| 1 | Complete | 31,394 |
| 2 | Partially complete | 50 |
| 3 | Not completed | 3 |
| Missing | Missing | 0 |
| **Total** | | **31,447** |

The full IFLS5 PTRACK codebook reports 34,201 complete, 69 partially complete, and 2,118 not completed (plus 47,392 missing) for `RES14B3B`. The KP extract contains 31,394 complete, 50 partial, and three not-completed status records. The three KP-extract respondents marked as not completed must be examined rather than automatically discarded.

Current household membership cross-check:

| MEMBER14 | KP respondents |
|---:|---:|
| 1 (current resident) | 31,445 |
| 0 (not current resident) | 2 |
| **Total** | **31,447** |

The two records marked `MEMBER14=0` both have `RES14B3B=1`. This combination is a reconciliation flag, not proof of invalid data. The records are not in the three duplicated PTRACK groups.

## 5. Reconciliation of IFLS4 KP respondents in IFLS5 PTRACK

All 29,029 IFLS4 KP respondent PIDLINK values are also present in IFLS5 PTRACK. Their 2014 membership and Book 3B status are:

| 2014 status among IFLS4 KP cohort | In IFLS5 KP extract | Not in IFLS5 KP extract | Total |
|---|---:|---:|---:|
| MEMBER14 = 1 | 21,247 | 2,574 | 23,821 |
| MEMBER14 = 0 | 2 | 5,206 | 5,208 |
| **Total** | **21,249** | **7,780** | **29,029** |

The 7,780 people from the IFLS4 KP cohort who are absent from the IFLS5 KP extract have the following `RES14B3B` statuses:

| RES14B3B | Meaning | IFLS4 KP respondents absent from IFLS5 KP |
|---:|---|---:|
| 1 | Complete | 1,505 |
| 2 | Partially complete | 11 |
| 3 | Not completed | 994 |
| Missing | Missing | 5,270 |
| **Total** | | **7,780** |

This is a central reconciliation result: **1,516 people absent from the IFLS5 KP extract have a PTRACK Book 3B status of complete or partially complete.** The status variable alone therefore cannot identify KP-section participation. A further 994 have Book 3B marked not completed and 5,270 have missing Book 3B status.

Among the 21,249 people shared by the two KP extracts, `RES14B3B` is 1 for 21,214, 2 for 34, and 3 for 1. All 21,249 are marked `MEMBER07=1` in IFLS5 PTRACK. The one shared KP respondent with `RES14B3B=3` also requires investigation.

The IFLS5 PTRACK file reports `DIED07=0` and `CONTACTALIVE07=1` for 29,027 of the IFLS4 KP cohort; two have missing values. These variables do not justify treating all KP-extract absences as deaths or attrition.

## 6. Reconciliation of IFLS5 KP respondents absent from IFLS4 KP

There are 10,198 IFLS5 KP respondents who are not present in the IFLS4 KP extract. In IFLS5 PTRACK, their 2007 indicators are:

| MEMBER07 | Count |
|---:|---:|
| 0 (not current resident in 2007) | 5,222 |
| 1 (current resident in 2007) | 4,976 |
| **Total** | **10,198** |

Their `RES07B3B` distribution is:

| RES07B3B | Meaning | IFLS5 KP respondents absent from IFLS4 KP |
|---:|---|---:|
| 1 | Complete | 0 |
| 2 | Partially complete | 1 |
| 3 | Not completed | 288 |
| Missing | Missing | 9,909 |
| **Total** | | **10,198** |

The 4,976 people marked `MEMBER07=1` have the following `RES07B3B` statuses: 4,687 missing, 288 marked not completed, and one marked partially complete. The 5,222 people marked `MEMBER07=0` all have missing `RES07B3B`. The aggregate counts show that IFLS5-only KP respondents are a mixture of membership histories and 2007 Book 3B tracking statuses. The reason for absence from the IFLS4 KP extract cannot be determined from these flags alone.

## 7. What can and cannot be concluded

Supported by these files:

1. `PIDLINK` links every KP respondent to the corresponding wave's PTRACK.
2. The intersection of the two KP respondent sets is 21,249 people.
3. Absence from a KP extract is not equivalent to absence from PTRACK, death, or a specific nonresponse mechanism.
4. Book 3B completion status and KP-extract presence are not interchangeable.
5. IFLS5 PTRACK contains three duplicate PIDLINK groups, none in the IFLS5 KP respondent set.

Not established by this audit:

- The exact reason each person is absent from a wave's KP extract.
- Whether a partially completed Book 3B includes a valid response to all or some KP items.
- Whether a person marked as not currently resident was interviewed through another household or split-off route for the relevant section.
- A definitive attrition rate or causal explanation for panel loss.
- A final two-wave survey weight or design-based variance specification.
- Measurement equivalence or valid cross-wave KP scoring.

## 8. Decisions for the research protocol

Provisional decisions:

1. Retain `PIDLINK` as the sole person-level cross-wave key.
2. Define the candidate paired KP cohort as the intersection of the two KP-specific respondent ID sets (21,249 before item-level eligibility and missingness checks).
3. Do not automatically exclude paired respondents based only on `RES07B3B`, `RES14B3B`, `MEMBER07`, or `MEMBER14`; first verify the relevant Section KP item records and resolve the discordant statuses.
4. Keep cross-sectional IFLS4 and IFLS5 analyses distinct from paired-panel analysis.
5. Do not classify KP-extract absence as death, attrition, or nonresponse without further evidence.
6. Preserve the IFLS5 PTRACK duplicate records as an explicit unresolved issue; no arbitrary deduplication.
7. Do not finalize survey weights or the panel estimand at this stage.

## 9. Next required audit

The next stage should be **Stage 01.6 — KP Item-Level Response and Eligibility Audit**. It should inspect the actual KP item responses for the 21,249 paired respondents, reconcile IFLS4 `KP01` screening with `KP02` frequencies, quantify item-level missingness and discordant values, and determine whether the same ten item codes can be compared across waves. It must also revisit the unresolved IFLS4 KPTYPE codebook-versus-questionnaire discrepancy before any score is calculated.

## 10. Data governance

Only aggregate counts and methodological findings are committed. Raw Stata data and respondent-level identifiers remain local and must not be uploaded to this public repository. Analysis scripts should use local ignored data paths and should not print or export PIDLINK-level tables into tracked files.

---

**Conclusion:** The candidate paired KP respondent set contains 21,249 people. The reconciliation audit demonstrates why the paired cohort cannot be defined from PTRACK completion or membership flags alone. The next necessary task is item-level response validation and instrument comparability, not statistical modeling.
