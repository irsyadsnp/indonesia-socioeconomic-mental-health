# Mental Health Instrument Audit — IFLS4 and IFLS5

**Project:** Indonesia Socioeconomic Factors & Mental Health  
**Stage:** 01.2 — Mental-health variable audit  
**Status:** Partial audit. IFLS5 questionnaire and user-guide file layout reviewed; IFLS4 item-level questionnaire/codebook comparison remains pending.  
**Review date:** 2026-11-26

## 1. Audit objective

Identify the mental-health instrument, item wording, response categories, questionnaire location, data-file reference, respondent universe, and scoring requirements for IFLS4 and IFLS5.

This document distinguishes facts confirmed in official RAND documentation from items that still require inspection of the released data and wave-specific codebooks.

## 2. Confirmed IFLS5 instrument

RAND's IFLS5 documentation states that Section KP was added in IFLS4 and retained in IFLS5. The IFLS5 overview describes the measure as the 10-item short CES-D scale, replacing the earlier eight-question mental-health set used in IFLS1 and IFLS3.

Official questionnaire location:
- Survey round: IFLS5 (2014–2015)
- Questionnaire: Household Survey Questionnaire, Book IIIB (Adult Information, part 2)
- Section: KP — Mental Health
- Questionnaire item: KP02
- Item-type field printed in questionnaire: KPTYPE
- Questionnaire/data-file footer: B3B_KP
- Recall period: past week
- Response categories: 1 = Rarely or none (≤1 day); 2 = Some days (1–2 days); 3 = Occasionally (3–4 days); 4 = Most of the time (5–7 days)

The questionnaire lists the following ten statements:

| Item | Statement in IFLS5 English questionnaire | Directional note |
|---|---|---|
| A | I was bothered by things that usually don't bother me | Negative symptom |
| B | I had trouble concentrating in what I was doing | Negative symptom |
| C | I felt depressed | Negative symptom |
| D | I felt everything I did was an effort | Negative symptom |
| E | I felt hopeful about the future | Positive wording; reverse direction for a conventional depressive-symptom total |
| F | I felt fearful | Negative symptom |
| G | My sleep was restless | Negative symptom |
| H | I was happy | Positive wording; reverse direction for a conventional depressive-symptom total |
| I | I felt lonely | Negative symptom |
| J | I could not get going | Negative symptom |

**Data-structure finding:** The IFLS5 User's Guide lists B3B_KP as a question-level file with observation keys HHID14, PID14, and KPTYPE, and reports 314,530 records. This indicates a repeated-item/grid structure: one respondent can contribute multiple item records, identified by KPTYPE. KP02 is the questionnaire matrix identifier; it should not be mistaken for ten separate wide columns without checking the codebook. The actual response-variable name and KPTYPE category labels must still be confirmed from the released codebook and data. Do not assume variable names such as kp02a–kp02j.

## 3. IFLS4 status

RAND's IFLS5 overview states that the KP mental-health section was introduced in IFLS4 and retained in IFLS5. It also describes the change from the earlier eight questions in IFLS1/IFLS3 to the short CES-D 10-item instrument in IFLS4/IFLS5.

However, this review has not yet verified the IFLS4 questionnaire's exact item wording, response coding, file name, variable structure, eligible respondent universe, or codebook entries against the official IFLS4 files.

Therefore:
- IFLS4 remains a candidate wave.
- IFLS4–IFLS5 comparability is plausible at instrument-family level but is not yet certified at item/data level.
- Do not calculate a harmonized two-wave score until the IFLS4 questionnaire and codebook have been checked side by side with IFLS5.

## 4. Respondent universe and data layout

The IFLS5 User's Guide describes Book 3B as adult information (part 2), collected for each household member age 15 and older. This establishes the broad book-level universe, but the KP section's own CAPI routing and any exceptions must still be checked in the questionnaire and data.

The User's Guide explains that some IFLS modules use TYPE variables and can contain multiple records per individual. The actual KP file layout must therefore be established from the codebook and released data before choosing a merge key or reshaping strategy.

## 5. Scoring protocol — not yet authorized for production

A conventional CES-D-10 total generally requires positive-affect items to be reverse-coded before summation. In the IFLS5 item wording, E (hopeful) and H (happy) are positively phrased.

This is a provisional scoring hypothesis only. Before producing a score, verify:
1. The official IFLS4 and IFLS5 response coding.
2. Whether the released IFLS variables are raw item responses or already transformed.
3. The precise reverse-coding convention and score range.
4. The treatment of special codes, refusals, don't-know responses, and structural skips.
5. The permitted number of missing items, if any, and the rule for prorating or excluding incomplete scales.
6. Whether RAND provides an official derived score or an official scoring note.

Do not apply a diagnostic label. CES-D-10 is a self-report measure of depressive symptoms, not a clinical diagnosis.

## 6. Missing and special codes

The IFLS5 User's Guide explains that numeric variables may contain special codes, including codes ending in 5, 6, 7, 8, or 9, representing out-of-range, not applicable, refusal, don't know, or missing responses. It also explains that some modules have X indicator variables.

This general guide is not a substitute for the KP-specific codebook. KP item responses must be checked individually; do not indiscriminately recode all values above 4 without inspecting the codebook and file structure.

## 7. Evidence reviewed

1. Strauss, J., Witoelar, F., & Sikoki, B. (2016). *The Fifth Wave of the Indonesia Family Life Survey (IFLS5): Overview and Field Report*. RAND, WR-1143/1. https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z1/RAND_WR1143z1.pdf  
   Relevant statement: Section KP was added in IFLS4 and retained in IFLS5; the short CES-D replaced the earlier eight-question set in IFLS1 and IFLS3.

2. Strauss, J., Witoelar, F., & Sikoki, B. (2016). *Household Survey Questionnaire for the Indonesia Family Life Survey, Wave 5*. RAND, WR-1143/3. https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z3/RAND_WR1143z3.pdf  
   Relevant location: Book IIIB, Section KP, questionnaire page 12; item KP02 and field KPTYPE.

3. Strauss, J., Witoelar, F., & Sikoki, B. (2016). *User's Guide for the Indonesia Family Life Survey, Wave 5*. RAND, WR-1143/2. https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z2/RAND_WR1143z2.pdf  
   Relevant topics: Book 3B respondent universe; question-number/variable naming; TYPE variables; missing values and special codes; weights; longitudinal linkage.

## 8. Outstanding verification checklist

- [ ] Retrieve official IFLS4 Book IIIB questionnaire and inspect Section KP.
- [ ] Retrieve official IFLS4 Book IIIB codebook and identify exact KP variables and file.
- [ ] Retrieve official IFLS5 Book IIIB codebook and identify exact KP variables and file.
- [ ] Compare all ten item wordings and response categories across IFLS4 and IFLS5.
- [ ] Verify CAPI routing, respondent age rules, proxy exclusions, and item-level nonresponse.
- [x] Establish the IFLS5 KP file's documented observation keys and repeated-item structure from the User's Guide.
- [ ] Confirm the exact response-variable name and KPTYPE category labels from the released IFLS5 codebook.
- [ ] Confirm the corresponding IFLS4 file layout and exact identifiers from its codebook.
- [ ] Confirm unique respondent keys and cross-wave person linkage.
- [ ] Verify scoring, reverse coding, missing-item rule, and any official derived score.
- [ ] Only then create a reproducible scoring specification and test it against raw data.

## 9. Decision log

| Date | Decision | Rationale |
|---|---|---|
| 2026-11-26 | Treat IFLS5 KP02 as the documented 10-item short CES-D questionnaire | Confirmed in the official IFLS5 questionnaire and IFLS5 overview |
| 2026-11-26 | Treat B3B_KP as a question-level repeated-item file in IFLS5, keyed by HHID14, PID14, and KPTYPE | IFLS5 User's Guide lists this observation level and 314,530 records |
| 2026-11-26 | Keep IFLS4–IFLS5 harmonization provisional | Exact IFLS4 item and codebook comparison has not yet been completed |
| 2026-11-26 | Do not calculate scores or apply cut-offs at this stage | Scoring and missing-response rules require verification |

## 10. Additional data-layout finding (2026-11-26)

The IFLS5 User's Guide appendix lists **B3B_KP** as:
- Description: Book 3B CES-D
- Observation level: Question
- Unique observation identifiers: HHID14, PID14, KPTYPE
- Number of records: 314,530

This is a material clarification: IFLS5 KP is not documented as a simple one-row-per-person file. The file is a question-level grid. A valid analysis dataset will need a deliberate reshape or aggregation step after validating KPTYPE labels and the response variable. The individual identifier for cross-wave linkage is PIDLINK, not the wave-specific household/person ID pair.

The IFLS5 User's Guide explicitly advises using PIDLINK to link individual-level information across waves, because HHID and PID can change when people move between households. Do not merge IFLS4 and IFLS5 mental-health files using HHID07/PID07 against HHID14/PID14.

**Unresolved:** The precise IFLS5 response variable name and KPTYPE value-to-item mapping still require the codebook. The IFLS4 file and key structure must also be checked directly. The IFLS5 file layout must not be projected onto IFLS4 without evidence.

## 11. Additional sources

4. RAND, *User's Guide for the Indonesia Family Life Survey, Wave 5*, Appendix A (file structure and observation identifiers). https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z2/RAND_WR1143z2.pdf
5. Marvianto, R. D. (2023). *Psychometric properties of Mental Health Scale: An Item Response Theory Approach*. Gadjah Mada Journal of Psychology. https://doi.org/10.22146/gamajop.73878

---

**Next task:** Obtain the IFLS4 and IFLS5 released codebooks, confirm response-variable and KPTYPE mappings, then construct a validated cross-wave item map before scoring. Complete IFLS4/IFLS5 codebook comparison and confirm the released KP data layout before proceeding to socioeconomic variable mapping.
