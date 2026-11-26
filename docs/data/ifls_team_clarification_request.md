# IFLS Team Clarification Request — Section KP

**Stage:** 01.8  
**Status:** Draft prepared; not sent.  
**Recipient:** ifls-supp@rand.org  
**Subject:** Clarification Request: IFLS4 B3B_KP KPTYPE Labels and KP01/KP02 Response Structure

## Purpose

Request an authoritative interpretation of the IFLS4 Section KP item codes and the relationship between the IFLS4 and IFLS5 response formats before constructing any cross-wave psychological distress score.

## Questions for the IFLS team

1. In the public-use IFLS4 release 1.0 file `b3b_kp.dta`, what exact item wording corresponds to `KPTYPE=A` through `KPTYPE=J`?
2. The IFLS4 B3B codebook (`ifls2007_hhd_B3B.txt`) lists KPTYPE labels that differ from the ten items in the IFLS4 questionnaire copies available to us and from the IFLS5 questionnaire. Is the IFLS4 codebook's KPTYPE value-label sequence correct, or is it a stale/mismatched documentation entry?
3. If the codebook labels are incorrect, is there an official corrected codebook, erratum, data update, or recommended mapping for IFLS4 `KPTYPE`?
4. Which IFLS4 questionnaire version/revision should analysts treat as the definitive fielded instrument corresponding to the public-use release 1.0 `b3b_kp.dta` file?
5. In IFLS4, does `KP01=3` (No) imply the same response meaning as IFLS5 `KP02=1` (Rarely or none, ≤1 day), or should the IFLS4 screening response remain a distinct category?
6. Is there an official scoring instruction for the ten Section KP items across IFLS4 and IFLS5, including any reverse coding, handling of KP01 screening skips, missing values, or cutoffs? If so, please point us to the authoritative documentation.

## Information to include with the request

- Dataset: Indonesia Family Life Survey (IFLS).
- Waves: IFLS4 (2007–2008) and IFLS5 (2014–2015).
- IFLS4 file: `b3b_kp.dta`, release version 1.0.
- IFLS5 file: `b3b_kp.dta`, release version 1.3.
- IFLS4 codebook: `ifls2007_hhd_B3B.txt`.
- IFLS5 codebook: `ifls2014_hhd_B3B.txt`.
- Variables: `KPTYPE`, `KP01`, and `KP02`.

Do not attach respondent-level records, PIDLINK values, household identifiers, or raw data. If a minimal reproducible example is requested, provide only non-identifying codebook excerpts and aggregate frequency tables.

## Follow-up protocol

1. Send the email to `ifls-supp@rand.org`.
2. Save the sent date and message copy in the project's research log.
3. If a reply is received, archive the response (with personal contact details removed if appropriate) and update the audit with a clear distinction between the team's clarification and the project's interpretation.
4. If no response is received, follow up once after a reasonable interval and continue to treat the discrepancy as unresolved.
5. Do not construct a cross-wave KP score until the issue is resolved or the research design is explicitly changed to avoid unsupported equivalence.

## Source for contact address

The World Bank IFLS4 study description lists RAND Family Life Surveys as the access authority and `ifls-supp@rand.org` as its contact email: https://microdata.worldbank.org/catalog/1044/study-description

The IFLS dataset access guidance also directs data users to contact the study team at this address and to include the relevant wave, data files, and variables in questions: https://atlaslongitudinaldatasets.ac.uk/datasets/ifls

---

**Current status:** Draft only. No email has been sent and no response from the IFLS team has been received.
