# IFLS4–IFLS5 KP Primary Documentation Review

**Stage:** 01.7  
**Status:** External documentation review completed; exact IFLS4 item-label discrepancy remains unresolved.  
**Decision:** Do not calculate a cross-wave KP score yet.

## 1. Question under review

The project needs to establish whether the ten KP item codes (A–J) in IFLS4 and IFLS5 refer to the same questions in the same order, and whether the IFLS4 screening-plus-frequency design can be harmonized with IFLS5's direct frequency response.

## 2. Primary RAND documentation found

### 2.1 IFLS5 overview and field report

RAND's *The Fifth Wave of the Indonesia Family Life Survey: Overview and Field Report*, WR-1143/1-NIA/NICHD (March 2016), describes Section KP as a new section introduced in IFLS4 and retained in IFLS5. It states that the section asks about depressive symptoms and that IFLS replaced the earlier eight questions used in IFLS1 and IFLS3 with a ten-question short CES-D scale to improve comparability with international surveys.

Source: https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z1/RAND_WR1143z1.pdf  
Relevant text: pages 33–34 of the PDF (document lines 2007–2010 in the searchable text).

This supports continuity of the KP section and its broad short-CES-D purpose across IFLS4 and IFLS5. It does not enumerate the exact ten item wordings in IFLS4 or explain the conflicting IFLS4 codebook labels.

### 2.2 IFLS5 household questionnaire

RAND's *Household Survey Questionnaire for the Indonesia Family Life Survey, Wave 5*, WR-1143/3-NIA/NICHD (March 2016), lists these ten Section KP items in A–J order:

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

The response options are frequency categories for the past week: rarely or none (≤1 day), some days (1–2 days), occasionally (3–4 days), and most of the time (5–7 days).

Source: https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z3/RAND_WR1143z3.pdf  
Relevant text: Section KP, PDF pages around Book IIIB–12 (document lines 15303–15320 in searchable text).

### 2.3 IFLS4 codebook

The IFLS4 B3B codebook file supplied with the project lists KPTYPE A–J using a different ten-item sequence. In particular, it includes poor appetite, inability to shake off the blues, feeling as good as others, life failure, and talking less than usual. It does not list trouble concentrating, feeling depressed, restless sleep, loneliness, or inability to get going in the corresponding A–J positions.

This is directly observed in the supplied IFLS4 codebook `ifls2007_hhd_B3B.txt`. The delivered IFLS4 Stata file stores KPTYPE as A–J strings and has no embedded value labels to independently settle the issue.

## 3. Evidence assessment

| Evidence | What it supports | What it does not establish |
|---|---|---|
| RAND IFLS5 overview (WR-1143/1) | KP introduced in IFLS4, retained in IFLS5; ten-item short CES-D purpose | Exact IFLS4 item wording and order |
| RAND IFLS5 questionnaire (WR-1143/3) | Exact IFLS5 item wording and A–J order | Exact IFLS4 item wording |
| Supplied IFLS4 codebook | IFLS4 KPTYPE A–J labels as distributed in this codebook | Whether these labels are stale, erroneous, or reflect the administered IFLS4 questionnaire |
| Supplied IFLS4 questionnaire copies previously inspected | Questionnaire wording as represented in those copies | Whether all fielded versions and the released data correspond exactly to those copies |
| Raw IFLS4 Stata extract | KPTYPE values A–J and observed KP01/KP02 response structure | Semantic meaning of A–J, because no value labels are embedded |

The IFLS5 overview's statement that KP was retained from IFLS4 is useful but not sufficient to override the IFLS4 codebook. Likewise, the questionnaire copy cannot automatically override the codebook without confirmation that it is the exact fielded version associated with the public-use data release.

## 4. Finding

The discrepancy is **not resolved** by the currently available primary documentation.

The most defensible conclusion is:

- Both waves contain a ten-item KP section concerned with depressive symptoms.
- RAND describes the section as a short CES-D scale introduced in IFLS4 and retained in IFLS5.
- The exact IFLS4 KPTYPE A–J descriptions in the supplied codebook differ from the IFLS5 questionnaire's ten items.
- The released IFLS4 Stata file does not contain embedded labels that resolve the conflict.
- No authoritative IFLS4 correction note or data-update notice resolving this specific discrepancy was located in this review.

Do not infer that identical letter codes imply identical items. Do not silently substitute IFLS5 wording for IFLS4 labels.

## 5. Recommended clarification from RAND / IFLS team

The IFLS documentation identifies the study team contact as `ifls-supp@rand.org`. A targeted request should ask:

1. For the public-use IFLS4 release 1.0 `B3B_KP` file, what exact item wording corresponds to KPTYPE A, B, …, J?
2. Is the IFLS4 `ifls2007_hhd_B3B.txt` KPTYPE value-label sequence correct, or is it a stale/mismatched codebook entry?
3. Which questionnaire version and revision should analysts use to interpret the IFLS4 KP records?
4. Was the ten-item KP instrument changed between IFLS4 and IFLS5 despite the overview's description of the section as retained?
5. In IFLS4, does KP01=3 (No) represent a frequency equivalent to IFLS5 KP02=1 (Rarely or none, ≤1 day), or should it remain a distinct screening outcome?

Official IFLS4 metadata hosted by the World Bank lists RAND as a producer and gives the RAND IFLS study contact as `ifls-supp@rand.org`. See: https://microdata.worldbank.org/catalog/1044

## 6. Analysis restrictions pending clarification

Until the IFLS team or a definitive primary data note resolves the issue:

- Keep IFLS4 and IFLS5 item distributions separate.
- Preserve raw `KPTYPE`, `KP01`, and `KP02` values.
- Do not map IFLS4 KPTYPE letters to IFLS5 labels.
- Do not convert IFLS4 KP01=3 into IFLS5 KP02=1.
- Do not reverse-code, sum, standardize, or threshold a ten-item score across waves.
- Do not claim longitudinal measurement invariance.
- A separate-wave descriptive analysis may be considered after wave-specific item interpretation is settled, but it must not imply cross-wave equivalence.

## 7. Next step

Obtain a written clarification from the IFLS team or a definitive IFLS4 release note. If no clarification is obtainable, revise the research design so that the primary outcome does not rely on an unsupported cross-wave item mapping. Potential alternatives should be evaluated only after the documentation issue is formally recorded as unresolved.

---

**Conclusion:** RAND's overview confirms that the KP section was introduced in IFLS4 and retained in IFLS5 as a ten-item short CES-D measure. However, the exact IFLS4 item labels remain inconsistent between the distributed codebook and the questionnaire evidence. The discrepancy is unresolved, so cross-wave score construction remains blocked.
