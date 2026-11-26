# IFLS4–IFLS5 Codebook Access and Variable-Mapping Status

**Project:** Indonesia Socioeconomic Factors & Mental Health  
**Stage:** 01.2 — Codebook verification  
**Review date:** 2026-11-26  
**Status:** Documentation inventory completed; released codebook variable-level verification blocked pending registered public-use data access.

## 1. Why codebook access is required

The IFLS5 User's Guide identifies the KP data file and its observation structure, but it does not provide the full item-level codebook information needed to certify the response-variable name, value labels, special codes, and KPTYPE mapping. RAND explicitly advises users to consult the documentation for all waves and inspect actual data-file records because questionnaire and data structures can differ across waves.

## 2. Confirmed IFLS5 file-level information

From the official IFLS5 User's Guide, Appendix A:

| Field | Confirmed information |
|---|---|
| File | B3B_KP |
| Description | Book 3B CES-D |
| Observation level | Question |
| Unique record identifiers | HHID14, PID14, KPTYPE |
| Number of records listed | 314,530 |

The guide's file-level table does not establish the response-variable name or the mapping of each KPTYPE value to CES-D item A–J. These must be read from the official IFLS5 Household Survey Codebook and checked against the actual data.

## 3. Official documentation inventory

### IFLS5
- User's Guide, WR-1143/2: https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z2/RAND_WR1143z2.pdf
- Household Survey Questionnaire, WR-1143/3: https://www.rand.org/content/dam/rand/pubs/working_papers/WR1100/WR1143z3/RAND_WR1143z3.pdf
- Household Survey Codebook, WR-1143/5: RAND lists this as the volume containing descriptions of all IFLS5 household-survey variables and their locations in data files. The direct public PDF was not verified during this review.

### IFLS4
- Overview and Field Report, WR-675/1: https://www.rand.org/content/dam/rand/pubs/working_papers/WR600/WR675z1/RAND_WR675z1.pdf
- User's Guide, WR-675/2: RAND lists this as the volume describing IFLS4 file structure and data formats. Direct public PDF access was not verified during this review.
- Household Survey Questionnaire, WR-675/3: RAND lists this as the English translation of IFLS4 household and individual questionnaires. Direct public PDF access was not verified during this review.
- Household Survey Codebook, WR-675/5: RAND lists this as the source for descriptions and locations of IFLS4 household-survey variables. Direct public PDF access was not verified during this review.

## 4. Public-use data registration

RAND requires registration to access IFLS Public Use Data. After submitting the registration form, RAND emails instructions for accessing the data.

Official registration page:
https://www.rand.org/health/surveys/FLS/IFLS/access.html

RAND's stated public-use conditions include:
- Preserve respondent anonymity; do not attempt to identify individuals, households, families, service providers, or communities.
- Do not redistribute the data files to other people.
- Cite IFLS as the data source in reports and publications.
- Send RAND citations and URLs for publications based on IFLS data.

Restricted-use data (community coordinates and BPS desa codes) require a separate application. This project does not need restricted-use data for the current KP item-level audit.

## 5. Required codebook extraction after access

Once the public-use package is available, extract and record:

| Required field | IFLS4 | IFLS5 |
|---|---|---|
| Exact file name | Pending | B3B_KP (guide-confirmed) |
| Response variable name | Pending | Pending |
| KPTYPE variable and label | Pending | KPTYPE (guide-confirmed) |
| KPTYPE value-to-item mapping | Pending | Pending |
| Response value labels | Pending | Pending |
| Special/missing codes | Pending | Pending |
| Unique record keys | Pending | HHID14, PID14, KPTYPE (guide-confirmed) |
| Individual longitudinal key | Verify in wave guide/codebook | PIDLINK is documented for cross-wave linkage |
| Number of records | Pending | 314,530 (guide table) |
| Respondent eligibility / routing | Pending | Book-level universe and KP routing to verify |

Do not infer missing fields from another wave or from the questionnaire alone.

## 6. Next operational step

The researcher must complete RAND's public-use data registration and obtain the official IFLS4 and IFLS5 data packages, including household survey codebooks and relevant data files. Do not upload or publish restricted or respondent-level data in the public GitHub repository.

After access:
1. Keep original data locally in the ignored data/raw/ directory.
2. Do not commit raw IFLS files to GitHub.
3. Share only codebook excerpts needed for variable mapping, with no respondent-level records or identifying information.
4. Inspect the KP codebooks and a small, non-identifying structural summary of the KP data.
5. Update the item map only after codebook and data checks agree.

## 7. Decision log

| Date | Decision | Rationale |
|---|---|---|
| 2026-11-26 | Do not guess the IFLS5 response-variable name or KPTYPE labels | File-level guide does not establish these item-level mappings |
| 2026-11-26 | Require both IFLS4 and IFLS5 official codebooks before certifying harmonization | Wave-specific codebooks are necessary to verify item names, labels, and coding |
| 2026-11-26 | Use RAND public-use registration rather than unofficial mirrors | Preserves provenance, licensing, data integrity, and access compliance |
| 2026-11-26 | Do not place IFLS microdata in the public GitHub repository | RAND prohibits redistribution and requires respondent anonymity |

---

**Stage gate:** Stage 01.2 remains open until official IFLS4 and IFLS5 KP codebooks have been inspected and the response variable and item-type mappings are verified.
