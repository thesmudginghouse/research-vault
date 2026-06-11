# PRESIGNAL VAULT — DOCUMENT COMPRESSION SCHEMA
**Version:** 1.0 — June 2026
**Purpose:** Every document entering the vault is compressed to this standard. This is the quality gate.

---

## COMPRESSION PHILOSOPHY

The goal is 5–10% of original size while preserving 90%+ of reasoning utility.

**What gets preserved verbatim:**
- All numbers, thresholds, measurements, dates
- Legal or regulatory language (paraphrase changes meaning)
- Methodology descriptions (how the finding was reached)
- DOIs and citation chains

**What gets stripped:**
- Narrative framing and introduction
- Repetitive explanation
- Acknowledgments and institutional boilerplate
- Abstract (replace with CORE_CLAIMS)
- Conclusion sections (capture in RESIDUAL_FINDING)

**Format:** Markdown only. No binary. No PDFs in the vault — convert first.

---

## STANDARD COMPRESSION TEMPLATE

```markdown
# [DOCUMENT TITLE — COMPRESSED]

SOURCE: [Full citation: Author(s), Year, Title, Journal/Preprint, DOI/URL]
DOMAIN: [Primary field] | [Secondary field if cross-domain]
KEYWORDS: [8-12 terms, comma-separated]
DATE_INGESTED: [YYYY-MM-DD]
COMPRESSED_BY: [Claude / John / Both]
CONFIDENCE_IN_SOURCE: [High / Medium / Low + one-line rationale]

---

## CORE_CLAIMS
- [Claim 1 — one sentence, exact]
- [Claim 2]
- [Claim 3]
[Maximum 10 claims. If more, this document needs to be split.]

---

## METHODOLOGY
[How the finding was reached. 3-8 sentences. Exact enough that a researcher could evaluate it.]

---

## KEY_DATA
[Tables, numbers, thresholds, measurements — PRESERVED EXACTLY as they appear in the source]
[If a number matters, it goes here verbatim. No rounding, no paraphrase.]

---

## DEFINITIONS
[Technical terms used in this document that are non-standard or domain-specific]
[Format: TERM: definition]

---

## GAPS_FLAGGED
[What this document explicitly does not explain]
[What questions it raises without answering]
[This is where cross-domain signals often hide]

---

## CONTRADICTIONS
[Where this document conflicts with other known sources in the vault]
[Format: "This document claims X; [other document] claims Y; unresolved"]

---

## CATEGORY_ASSESSMENT
[Apply Subtraction Methodology categories if applicable]
[Flag institutional incentives, funding sources, industry relationships]
[Note if primary vs. secondary source]

---

## RAW_EXCERPTS
[Only passages where exact wording legally or technically matters]
[Keep to absolute minimum — this section defeats compression if overused]
[Each excerpt: "[verbatim text]" — Page/Section reference]

---

## CROSS_REFERENCES
[Other vault documents this should be read alongside]
[External sources not yet in vault that would strengthen/challenge this]
```

---

## CATEGORY INDEX FILES (_index.md)

Each vault category folder contains an `_index.md` with:

```markdown
# VAULT-[CATEGORY] INDEX

LAST_UPDATED: [date]
DOCUMENT_COUNT: [n]
PRIMARY_KEYWORDS: [10-15 terms covering this category]
ACTIVE_RESEARCH_QUESTIONS: [what we're currently trying to find]

---

## DOCUMENTS

| Filename | Source | Year | Core Claim (1 sentence) | Confidence | Cross-refs |
|----------|--------|------|------------------------|------------|------------|
| [file.md] | [author] | [year] | [claim] | H/M/L | [other files] |

---

## KNOWN_GAPS
[What primary sources are missing from this category]
[What data streams have not yet been loaded]
[What regulatory or institutional documents should be sought]

---

## CONTRADICTION_MAP
[Summary of active contradictions between documents in this category]
[Unresolved tensions that represent research opportunities]
```

---

## MASTER INDEX (README.md at vault root)

```markdown
# PRESIGNAL RESEARCH VAULT
**Maintained by:** John Ernest Carter, Presignal Inc.
**Methodology:** Carter Subtraction Methodology (Carter, J.E., Presignal Inc.)
**ORCID:** 0009-0004-1363-304X
**Last updated:** [date]
**Total documents:** [n]

## LOAD ORDER FOR RESEARCH SESSIONS
1. `_LENS/subtraction-methodology-compressed.md`
2. `_LENS/carter-protocol.md`
3. Target category `_index.md`
4. Relevant compressed documents
5. Raw data if available

## CATEGORIES

| Folder | Topic | Documents | Status |
|--------|-------|-----------|--------|
| `_LENS/` | Methodology core | 2 | Locked |
| `Vault-UAP/` | UAP / Geological Plasma | n | Active |
| `Vault-Water/` | Water Intelligence | n | Active |
| [etc] | | | |

## SCHEMA VERSION
Current: 1.0 — See `_schema.md` for compression standards.
```

---

## FILE NAMING CONVENTION

`[category]-[author-surname]-[year]-[2-3-word-slug].md`

Examples:
- `water-ontario-mecp-2023-pwqmn-baseline.md`
- `uap-fravor-2020-nimitz-testimony.md`
- `plasma-pyragius-2024-st40-npa-dataset.md`
- `law-ontario-2021-safe-drinking-water-act.md`

**Rules:**
- All lowercase
- Hyphens only, no spaces or underscores
- Year = publication year, not ingestion year
- Slug = most distinctive 2-3 words from the document

---

## COMPRESSION QUALITY CHECK

Before committing a compressed document, verify:
- [ ] All numbers preserved exactly
- [ ] Methodology reproducible from description
- [ ] Gaps section populated (not empty)
- [ ] Source citation complete with DOI or URL
- [ ] File size is ≤10% of source document
- [ ] Cross-references populated where known
- [ ] Category assessment applied

---

*Vault Schema v1.0*
*Presignal Inc. — Niagara Region, Ontario*
*Vault file: _schema.md*
