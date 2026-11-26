# Mental Health Instrument Audit — IFLS4 and IFLS5

**Project:** Indonesia Socioeconomic Factors & Mental Health  
**Stage:** 01.2 — Mental-health variable audit  
**Status:** Partial audit. IFLS5 questionnaire reviewed; IFLS4 item-level questionnaire/codebook comparison remains pending.  
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

**Important data-structure caveat:** The questionnaire prints KPTYPE and KP02 within the B3B_KP section. The final released variable names, whether observations are stored in a long or wide structure, the item-to-code mapping, and any associated type variables must be confirmed from the actual IFLS5 codebook and data files. Do not assume variable names such as kp02a–kp02j.

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
- [ ] Confirm whether KP is stored as one record per respondent-item or as separate item columns.
- [ ] Confirm unique respondent keys and cross-wave person linkage.
- [ ] Verify scoring, reverse coding, missing-item rule, and any official derived score.
- [ ] Only then create a reproducible scoring specification and test it against raw data.

## 9. Decision log

| Date | Decision | Rationale |
|---|---|---|
| 2026-11-26 | Treat IFLS5 KP02 as the documented 10-item short CES-D questionnaire | Confirmed in the official IFLS5 questionnaire and IFLS5 overview |
| 2026-11-26 | Record KPTYPE and KP02 as questionnaire identifiers, not yet final dataset variable names | Released codebook and data layout still need direct inspection |
| 2026-11-26 | Keep IFLS4–IFLS5 harmonization provisional | Exact IFLS4 item and codebook comparison has not yet been completed |
| 2026-11-26 | Do not calculate scores or apply cut-offs at this stage | Scoring and missing-response rules require verification |

---

**Next task:** Complete IFLS4/IFLS5 codebook comparison and confirm the released KP data layout before proceeding to socioeconomic variable mapping.
