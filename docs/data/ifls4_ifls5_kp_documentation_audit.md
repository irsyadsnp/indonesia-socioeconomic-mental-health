# IFLS4–IFLS5 Documentation Audit: Mental Health (Section KP)

**Status:** Documentation audit completed; raw-data validation pending  
**Source packages inspected:** `hh07_all_doc.zip`, `IFLS5_all_doc.zip`  
**Scope:** IFLS4 and IFLS5 Household Survey, Book 3B, Section KP  
**Purpose:** Establish the documentary basis for constructing a comparable mental-health measure before processing respondent-level data.

## 1. Executive findings

1. The English Book 3B questionnaires included in the two documentation packages show the same ten Section KP statements in IFLS4 and IFLS5.
2. IFLS4 uses two question variables in the questionnaire flow: KP01 (yes/no screening for each statement) followed by KP02 (frequency). IFLS5 presents KP02 frequency directly, without the KP01 screening question in the questionnaire.
3. The IFLS4 B3B codebook reports KP01 and KP02. For KP02, 197,686 of 290,290 question-level records are structurally missing, matching the number of KP01 responses coded No (197,686). This is consistent with skip logic, but the respondent-level data must be checked before recoding.
4. There is an unresolved discrepancy between the IFLS4 English questionnaire and the IFLS4 B3B codebook's KPTYPE labels. The questionnaire text matches the IFLS5 ten items, while the IFLS4 codebook labels list a different set of statements. Do not resolve this discrepancy by assumption; verify the actual data and the Bahasa questionnaire / updates and data notes.
5. The documentation supports treating IFLS4 and IFLS5 as candidate repeated measures, but it does not by itself establish a valid scoring algorithm, missing-data rule, clinical cutoff, or strict measurement invariance.

## 2. Documentary sources inspected

### IFLS4 package
- `hh07_all_doc.zip`
- `ifls2007_hhd_B3B.txt` — IFLS4 Household Survey Codebook, Book 3B
- `HH BOOK 3B FINAL.pdf` — English questionnaire extracted from `hh07_english_pqx.zip`
- `IFLS2007_UsersGuide_vol1-6-23-09.pdf`
- `IFLS2007_UsersGuide_vol2.pdf`

### IFLS5 package
- `IFLS5_all_doc.zip`
- `ifls2014_hhd_B3B.txt` — IFLS5 Household Survey Codebook, Book 3B
- `08 IFLS5 HH BOOK 3B.pdf` — English questionnaire extracted from `IFLS5_HH_PQX_Public_Eng.zip`
- `IFLS5_User_Guide_Vol_1.pdf`
- `IFLS5_User_Guide_Vol_2.pdf`

## 3. Ten Section KP statements in the English questionnaires

The following statements appear in both the IFLS4 and IFLS5 English Book 3B questionnaires:

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

Both questionnaires introduce Section KP with a recall period of the past week.

**Important:** This table transcribes the English questionnaire wording. It is not a claim that the IFLS4 codebook's KPTYPE value labels have been reconciled.

## 4. IFLS4 questionnaire flow and codebook findings

### Questionnaire flow
- Section KP is titled Mental Health.
- KP01 asks whether the respondent experienced each statement during the past week, with Yes = 1 and No = 3.
- KP02 asks how often, with response categories:
  - 1 = Rarely (≤1 day)
  - 2 = Some days (1–2 days)
  - 3 = Occasionally (3–4 days)
  - 4 = Most of the time (5–7 days)

### IFLS4 codebook
The B3B codebook identifies:
- `HHID07`: 2007 household ID
- `PID07`: 2007 person ID within household
- `PIDLINK`: 2007 person ID
- `MODULE`: survey module; `B3B_KP`
- `KP01`: screening response
- `KP02`: frequency response
- `KPTYPE`: type of mental-health statement

Reported codebook frequencies:
- KP01 Yes (1): 92,566 records (31.89%)
- KP01 No (3): 197,686 records (68.10%)
- KP01 Missing (9): 38 records (0.01%)
- KP02 structurally missing: 197,686 records (68.10%)
- KP02 = 1: 12,067 records
- KP02 = 2: 13,886 records
- KP02 = 3: 31,678 records
- KP02 = 4: 34,930 records
- KP02 = 9 (Missing): 43 records
- Total: 290,290 question-level records

The equality between the KP01 No count and KP02 structurally missing count is consistent with the skip pattern. It is not sufficient evidence to assign a numerical zero to every skipped response. The raw data and instrument instructions must be checked first.

### IFLS4 codebook–questionnaire discrepancy
The IFLS4 codebook's KPTYPE labels list:
- A: bothered by things that usually ...
- B: did not feel like eating / appetite ...
- C: could not shake off the blues ...
- D: just as good as other people ...
- E: everything was an effort
- F: hopeful about the future
- G: life had been a failure
- H: fearful
- I: happy
- J: talked less than usual

This does not match the ten statements printed in the IFLS4 English questionnaire (Section 3), which do match the IFLS5 questionnaire. This conflict must remain open until verified against:
1. IFLS4 Bahasa Indonesia Book 3B questionnaire;
2. IFLS4 data updates and data notes;
3. actual `hh07_b3b` data values and KPTYPE codes;
4. any relevant release/version notes or clarification from RAND.

Do not map IFLS4 KPTYPE A–J to item labels solely on the basis of the current codebook or questionnaire until this discrepancy is resolved.

## 5. IFLS5 questionnaire flow and codebook findings

### Questionnaire flow
- Section KP is titled Mental Health.
- The questionnaire presents KP02 directly for each KPTYPE statement.
- Response categories:
  - 1 = Rarely or none (≤1 day)
  - 2 = Some days (1–2 days)
  - 3 = Occasionally (3–4 days)
  - 4 = Most of the time (5–7 days)

### IFLS5 codebook
The B3B codebook identifies:
- `HHID14`: 2014 household ID
- `HHID14_9`: 2014 household ID, 9 digit
- `PID14`: 2014 person ID within household
- `PIDLINK`: 2014 person ID
- `MODULE`: survey module; `B3B_KP`
- `KP02`: frequency response
- `KPTYPE`: type of KP feeling

Reported codebook frequencies:
- Total `B3B_KP` records: 314,470
- `KPTYPE` has ten categories A–J, each with 31,447 records
- KP02 = 1: 174,397 (55.46%)
- KP02 = 2: 47,524 (15.11%)
- KP02 = 3: 47,259 (15.03%)
- KP02 = 4: 45,290 (14.40%)

The IFLS5 codebook reports 314,470 question-level records. Do not substitute a different record count from secondary summaries without checking the relevant release documentation.

## 6. Cross-wave comparison: current assessment

| Feature | IFLS4 | IFLS5 | Assessment |
|---|---|---|---|
| Book / module | Book 3B / B3B_KP | Book 3B / B3B_KP | Same module name |
| Recall period | Past week | Past week | Same in English questionnaires |
| Item count | 10 | 10 | Same |
| English questionnaire statements | Set A–J listed in Section 3 | Set A–J listed in Section 3 | Same printed statements |
| Screening | KP01 Yes/No | No KP01 in questionnaire | Different response flow |
| Frequency variable | KP02 | KP02 | Same variable name |
| Frequency values | 1–4, plus code 9 missing | 1–4 | Similar categories; missing conventions differ |
| KPTYPE codebook labels | Conflict with IFLS4 English questionnaire | Match IFLS5 English questionnaire | IFLS4 unresolved |
| Person linkage field | PIDLINK | PIDLINK | Candidate longitudinal key; verify uniqueness and tracking rules |

**Conclusion:** The waves are promising for longitudinal analysis, but a comparable derived score is not yet approved. The IFLS4 KPTYPE discrepancy and KP01 skip logic are blocking issues.

## 7. Scoring and recoding decisions: deliberately not finalized

The documentation audit does not authorize us to:
- treat KP01 = No as a score of zero without confirming the intended skip interpretation;
- assume that KP02 missing values all have the same meaning;
- reverse-code positive-affect items without confirming the chosen scoring specification;
- apply a clinical cutoff or diagnostic interpretation;
- claim measurement invariance across waves.

Before deriving a score, inspect raw records and verify item coding, respondent-level completeness, skip logic, special missing values, and the IFLS4 KPTYPE discrepancy. The resulting measure should be described as a depressive-symptom indicator/score, not a psychiatric diagnosis.

## 8. Next required files and actions

1. Inspect the Bahasa Indonesia IFLS4 Book 3B questionnaire to check whether its Section KP wording resolves the codebook conflict.
2. Inspect the IFLS4 and IFLS5 updates and data notes for corrections affecting B3B_KP.
3. Inspect the actual Stata files `hh07_b3b` and `hh14_b3b`:
   - variable names and storage types;
   - KPTYPE values and labels;
   - KP01 / KP02 value distributions;
   - uniqueness of person-item records;
   - respondent counts and item completeness.
4. Inspect tracking files and confirm PIDLINK uniqueness and valid cross-wave matches.
5. Only then specify scoring, missing-data handling, and longitudinal inclusion criteria.

## 9. Data governance

The raw IFLS files are not to be committed to this public GitHub repository. Keep them locally under `data/raw/IFLS4/` and `data/raw/IFLS5/`. Commit only documentation, code, variable dictionaries, and disclosure-safe aggregate outputs consistent with RAND's data-use conditions.

---
*Prepared from the two user-provided documentation ZIP archives. This is a documentary audit, not an audit of respondent-level Stata data.*
