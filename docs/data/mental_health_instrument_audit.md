# Mental Health Instrument Audit — IFLS4 and IFLS5

**Project:** Indonesia Socioeconomic Factors & Mental Health  
**Stage:** 01.2 — Mental-health variable audit  
**Status:** Documentary comparison and structural raw-data audit completed; item-label reconciliation and scoring remain pending  
**Review date:** 2026-11-26

> **Correction and supersession notice:** This document's earlier version incorrectly stated that the IFLS4 item-level questionnaire/codebook comparison was pending and repeated an IFLS5 record count of 314,530. The user-provided documentation ZIP archives have now been inspected directly. The detailed, current findings are recorded in [IFLS4–IFLS5 Documentation Audit: Mental Health (Section KP)](ifls4_ifls5_kp_documentation_audit.md).

## 1. Confirmed documentary findings

Both English Book 3B questionnaires (IFLS4 and IFLS5) print the same ten Section KP statements and use a past-week recall period:

| KPTYPE | Statement |
|---|---|
| A | I was bothered by things that usually don't bother me |
| B | I had trouble concentrating in what I was doing |
| C | I felt depressed |
| D | I felt everything I did was an effort |
| E | I felt hopeful about the future |
| F | I felt fearful |
| G | My sleep was restless |
| H | I was happy |
| I | I felt lonely |
| J | I could not get going |

The IFLS4 questionnaire uses KP01 (Yes/No screening) followed by KP02 (frequency). The IFLS5 questionnaire presents KP02 directly. The frequency categories are substantively similar, but the IFLS4 skip pattern and special missing values require explicit validation.

## 2. Critical unresolved discrepancy

The IFLS4 B3B codebook's KPTYPE labels list a different set of statements from the ten statements printed in the IFLS4 English questionnaire. The codebook labels include appetite, inability to shake off the blues, feeling as good as others, life failure, and talking less than usual. The questionnaire instead lists the ten statements shown above, which match the IFLS5 English questionnaire.

This is unresolved. Check the IFLS4 Bahasa Indonesia questionnaire, IFLS4 updates/data notes, released Stata data, and if necessary RAND clarification. Do not assign IFLS4 KPTYPE labels to item meanings until the conflict is resolved.

## 3. Codebook facts

### IFLS4 B3B_KP
- Keys/identifiers listed: HHID07, PID07, PIDLINK, MODULE, KP01, KP02, KPTYPE.
- Total question-level records: 290,290.
- KP01: Yes = 92,566; No = 197,686; Missing code 9 = 38.
- KP02: structural missing = 197,686; response 1 = 12,067; 2 = 13,886; 3 = 31,678; 4 = 34,930; missing code 9 = 43.
- The matching KP01 No and KP02 structural-missing counts are consistent with skip logic, but do not prove that skipped responses should be assigned a score of zero.

### IFLS5 B3B_KP
- Keys/identifiers listed: HHID14, HHID14_9, PID14, PIDLINK, MODULE, KP02, KPTYPE.
- Total question-level records: 314,470 (not 314,530).
- KPTYPE has ten categories A–J, each with 31,447 records.
- KP02: response 1 = 174,397; 2 = 47,524; 3 = 47,259; 4 = 45,290.

## 4. Scoring decision

No production scoring rule has been approved. In particular, do not:
- assume IFLS4 KP01 = No should automatically be scored as zero;
- treat all missing values as equivalent;
- apply reverse coding without a documented scoring specification;
- apply a clinical cutoff or diagnostic interpretation;
- claim measurement invariance based only on matching English questionnaire text.

The measure should be described as depressive symptoms / a depressive-symptom indicator, not a psychiatric diagnosis.

## 5. Next validation steps

1. Inspect the IFLS4 Bahasa Indonesia Book 3B questionnaire and updates/data notes.
2. Inspect the released `hh07_b3b` and `hh14_b3b` Stata files for actual variables, value labels, KPTYPE values, special codes, and row uniqueness.
3. Verify PIDLINK uniqueness and cross-wave linkage using the tracking files.
4. Establish the scoring and missing-data rules only after the preceding checks.

## 6. Data governance

Keep raw IFLS files locally under `data/raw/IFLS4/` and `data/raw/IFLS5/`. Do not commit raw IFLS data to this public repository. Commit only documentation, code, variable dictionaries, and disclosure-safe aggregate outputs consistent with RAND's data-use conditions.


## 7. Raw-data validation update (2026-11-26)

The supplied IFLS4 and IFLS5 B3B archives were inspected directly. Both contain `b3b_kp.dta`, each with exactly ten rows per PIDLINK and no duplicate PIDLINK–KPTYPE combinations. IFLS4 has 29,029 unique PIDLINKs and IFLS5 has 31,447. The files contain KPTYPE A–J as strings without embedded value labels.

The IFLS4 KP01/KP02 cross-tab confirms 197,686 KP02 system-missing rows coincide with KP01 = 3 (No), consistent with skip logic. Ten records involve discordant special code 9 patterns and require review. The direct PIDLINK set overlap between these two KP files is 21,249 people; this is not yet a final longitudinal sample or attrition estimate.

Full aggregate findings, variable storage types, distributions, and decisions are recorded in [IFLS4–IFLS5 KP Raw Data Validation](ifls4_ifls5_kp_raw_data_validation.md).

The IFLS4 KPTYPE semantic discrepancy remains unresolved: the released file contains only A–J codes, while the IFLS4 codebook labels conflict with the English and Bahasa questionnaire wording. Do not finalize item-label mapping or scoring until official updates/data notes or RAND clarification resolve the discrepancy.
