# EU Return Policy Corpus (1999-2020)

This archive contains a comprehensive corpus of European Union policy documents related to return policy, spanning from 1999 to 2020.
The corpus is the basis of the analysis reported in Hoffmeyer-Zlotnik, Paula, and Philipp Stutz. "Changing Norms in EU Return Policy? A longitudinal analysis of Commission documents on return". Forthcoming in Journal of Ethnic and Migration Studies


## Contents

- **Return_Corpus_EurLex_PR_clean.csv** - Main corpus file containing 701 documents with standardized metadata
- **Replication_Script_EU_Return.qmd** - Quarto document with full replication code for the analysis reported in the paper
- **Replication_Script_EU_Return.html** - Rendered HTML version of the replication script
- **codebook.md** - Data dictionary with variable definitions, cleaning methodology, and source attribution
- **eurovoc_migration_concepts.csv** - Machine-readable list of 90 Eurovoc migration concepts used for corpus filtering

## Quick Start

To replicate the analysis:

1. Download all files to the same directory on your computer
2. Open `Replication_Script_EU_Return.qmd` in RStudio or your preferred editor
3. Ensure required R packages are installed (see Dependencies section below)
4. Render the document or run code chunks interactively

The script uses relative file paths and will automatically load `Return_Corpus_EurLex_PR_clean.csv` from the same directory.

## Dependencies

Required R packages:
- tidyverse
- quanteda
- quanteda.textplots
- quanteda.textstats
- stm
- tidytext
- scales
- patchwork


## Data Sources

**Eur-Lex Documents** 
- Sourced via the `eurlex` R package (Ovádek 2021)
- EU Directories 11 (External Relations) and 19 (Area of Freedom, Security and Justice)
- Filtered by 90 migration-related Eurovoc descriptors

**Press Releases** 
- Source: Christian Rauh's Commission communication corpus (Rauh 2022)
- Manually coded for migration and return policy relevance

## Document Types

The corpus contains 701 documents classified into the following types:

- Press Release (449)
- Legislative Proposal (69)
- Report (57)
- Communication (51)
- Commission Staff Working Document (45)
- Legislative Decision (17)
- Other (13)


## Text Cleaning

Document texts have been cleaned to remove:
- HTML/JavaScript artifacts from web scraping
- CELEX identifiers and file paths
- Encoding errors and placeholder text
- Language code artifacts

Standard NLP preprocessing (stopwords, stemming, lowercasing) has NOT been applied before publication of the corpus, allowing users to apply their own pipelines for future applications. The replication script contains the pre-processing steps done for the analysis.

## Corpus Construction

For a detailed description of the corpus construction, see the Appendix of 
Hoffmeyer-Zlotnik, Paula, and Philipp Stutz. "Changing Norms in EU Return Policy? A longitudinal analysis of Commission documents on return". Forthcoming in Journal of Ethnic and Migration Studies

## Citation

Hoffmeyer-Zlotnik, Paula, and Philipp Stutz. 2026. Replication Material for: Changing Norms in EU Return Policy? A longitudinal analysis of Commission documents on return. Journal of Ethnic and Migration Studies. Zenodo. https://doi.org/10.5281/zenodo.18630085

Additionally, when using press releases, please cite:

Rauh, Christian. 2022. "Clear Messages to the European Public? The Language of European Commission Press Releases 1985–2020." *Journal of European Integration* 45(4): 683–701. https://doi.org/10.1080/07036337.2022.2134860

## References

Ovádek, Marek. 2021. "The R Package Eurlex: Accessing European Union Law." *Journal of Open Source Software*, 6(63), 3130. https://doi.org/10.21105/joss.03130

Rauh, Christian. 2022. Replication Data for: Clear Messages to the European Public? The Language of European Commission Press Releases 1985-2020. Harvard Dataverse. https://doi.org/10.7910/DVN/UGGXUF



## Contact

paula.hoffmeyerzlotnik@sciencespo.fr
