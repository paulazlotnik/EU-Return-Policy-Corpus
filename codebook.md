# Corpus Codebook

## Variables

| Variable | Type | Description | Notes |
|----------|------|-------------|-------|
| `id` | character | Document identifier | CELEX number for Eur-Lex docs, ipnum for press releases. Unique identifier. |
| `corpus` | character | Source corpus | "EurLex" = Eur-Lex policy documents, "Press" = Commission press releases |
| `type` | character | Document type | Coded types extracted from document titles and source corpus: Commission Staff Working Document, Communication, Legislative Decision, Legislative Proposal, Report, Press Release, Other | 
| `date` | character | Publication date | Range: 09.04.1985 - 23.12.2020  |
| `year` | integer | Publication year | Range: 1985-2020 |
| `title` | character | Document title | **Not unique**: 9 duplicate titles exist (14 documents total) representing different versions, revisions, or parts of related policy initiatives |
| `text` | character | Document text | Document text (cleaning steps see below). |


## Data Cleaning

The following artifacts were systematically removed from document texts after scraping:
- HTML elements: `@import`, `url()`, `css`, `xml`, `EUR-Lex` branding
- CELEX identifiers embedded in text: `L_\d+EN` patterns
- Encoding errors: `ð`, `ï`, `Ö`, `Õ`, `ê`, `ò`
- Placeholder text: `aaaa`, `pppp`, `xxx`, `xx`, `oj`, `gt`
- Language code artifacts: Standalone `en`, `fr`, `de`, etc. when not part of words
- Letter-number combinations: CELEX numbers and date ranges in tokenized form

**Note**: This cleaning focuses on removing scraping/encoding artifacts. Standard NLP preprocessing (stopword removal, stemming, lowercasing) is NOT applied, allowing users to apply their own preprocessing pipelines.

## Source Attribution

**Eur-Lex documents** (corpus = EurLex):  
- Queried metadata via `eurlex` R package (Ovádek 2021)
- Directories 11 (External Relations) and 19 (AFSJ)
- Filtered by Eurovoc descriptors and title keywords. For used descriptors see below

**Press releases** (corpus = Press):  
- Source: Christian Rauh's Commission communication corpus (Rauh 2022)
- Manually coded for migration and return relevance
- Reference: Rauh, Christian, 2022, "Replication Data for: 'Clear messages to the European public? The 
language of European Commission press releases 1985-2020', Journal of European Integration 45(4): 683-701”, https://doi.org/10.7910/DVN/UGGXUF, Harvard Dataverse, V1


## Corpus Statistics

- **Total documents**: 701
- **Time range**: 1999 - 2020
- **Eur-Lex documents**: 252
- **Press releases**: 449
- **Average word count**: 5610 words
- **Document types**:
  - Press Release: 449
  - Legislative Proposal: 69
  - Report: 57
  - Communication: 51
  - Commission Staff Working Document: 45
  - Legislative Decision: 17
  - Other: 13

## Citation

Hoffmeyer-Zlotnik, Paula and Philipp Stutz. (2025). EU Migration and Return Policy Corpus (1985-2020). Zenodo. [DOI placeholder].

For press releases, additionally cite:  
Rauh, Christian. Clear Messages to the European Public? The Language of European Commission Press Releases 1985–2020. Journal of European Integration, 15 octobre 2022, 1‑19. https://doi.org/10.1080/07036337.2022.2134860.


## Eurovoc Filtering Concepts

This corpus was filtered using 90 migration-related Eurovoc concepts. A subset of these (marked below) is specifically flagged for return focus.

For the full list of eurovoc terms see https://op.europa.eu/en/web/eu-vocabularies/dataset/-/resource?uri=http://publications.europa.eu/resource/dataset/eurovoc 

| Code | Concept Label | Return Focus |
|------|---------------|--------------|
| 185 | migration control | ✓ |
| 259 | migratory movement |  |
| 488 | identity document |  |
| 552 | rights of aliens |  |
| 553 | rights of minorities |  |
| 564 | international human rights law |  |
| 724 | emigration |  |
| 760 | child of migrant |  |
| 934 | brain drain |  |
| 950 | removal | ✓ |
| 953 | extradition |  |
| 977 | female migrant |  |
| 1114 | frontier |  |
| 1213 | border war |  |
| 1302 | immigration |  |
| 1462 | integration of migrants |  |
| 1909 | migration |  |
| 1910 | commuting |  |
| 1911 | return migration | ✓ |
| 1912 | family migration |  |
| 1913 | forced migration |  |
| 1914 | frontier migration |  |
| 1915 | illegal migration | ✓ |
| 1916 | internal migration |  |
| 1917 | interurban migration |  |
| 1920 | intraurban commuting |  |
| 1921 | Community migration |  |
| 1922 | occupational migration |  |
| 1923 | rural migration |  |
| 1925 | seasonal migration |  |
| 1948 | geographical mobility |  |
| 2036 | naturalisation |  |
| 2065 | nomadism |  |
| 2096 | stateless person |  |
| 2509 | migration policy |  |
| 2834 | protection of minorities |  |
| 2867 | political asylum |  |
| 2986 | refugee |  |
| 2991 | political refugee |  |
| 3053 | forced disappearance |  |
| 3055 | police checks |  |
| 3075 | aid to refugees |  |
| 3320 | migrant |  |
| 3322 | migration for settlement purposes |  |
| 3323 | repatriation grant |  |
| 3710 | UNHCR |  |
| 3906 | freedom of movement |  |
| 3912 | xenophobia |  |
| 4003 | foreign national |  |
| 4004 | residence permit |  |
| 4005 | admission of aliens |  |
| 4045 | public safety |  |
| 4495 | transfer of population |  |
| 4562 | migrant worker |  |
| 4614 | UNRWA |  |
| 4696 | civilian victim |  |
| 5121 | colonialism |  |
| 5405 | Schengen Agreement |  |
| 5528 | ethnic conflict |  |
| 5540 | border control |  |
| 5551 | police cooperation |  |
| 5552 | EU police cooperation |  |
| 5592 | discrimination on the basis of nationality |  |
| 5597 | right of asylum |  |
| 5649 | external border of the EU |  |
| 5796 | EU visa policy |  |
| 5933 | trafficking in human beings |  |
| 5991 | International Organisation for Migration |  |
| 6222 | area of freedom, security and justice |  |
| 6540 | diaspora |  |
| 6541 | EU migration policy |  |
| 6626 | Schengen Information System |  |
| 8439 | Frontex |  |
| 8481 | EU police mission |  |
| 39362 | non-EU national |  |
| 52595 | citizenship |  |
| 58876 | recognised non-citizen |  |
| 447958 | European Union Agency for Asylum |  |
| c_0894af6b | internally displaced person |  |
| c_2c8a75b1 | family reunification |  |
| c_63446d6e | unaccompanied child |  |
| c_90dfa6c7 | cash and voucher assistance |  |
| c_977a9fe5 | circular migration |  |
| c_a2a3268e | refugee facility |  |
| c_b0536152 | economic migration |  |
| c_b0c14f45 | resettlement of persons |  |
| c_c825b20c | migration statistics |  |
| c_d867a3b5 | urban migration |  |
| c_f7430876 | search and rescue |  |
| c_ff638149 | asylum seeker |  |

**Total concepts**: 90  
**Return focus concepts**: 4 (codes: 185, 950, 1911, 1915)

A machine-readable version of this table is also available in `eurovoc_migration_concepts.csv`.