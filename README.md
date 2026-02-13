# Reproducibility Package — Health Literacy among Older Adults (WoS & Scopus)

This repository contains the datasets, screening logs, and bibliometric/network analysis outputs supporting the manuscript:

**“Health Literacy among Older Adults Before and After COVID-19 Outbreak: A Bibliometric and In-depth Analysis”**

The materials are organized to help editors and reviewers verify the search strategy, screening decisions, deduplication procedure, and VOSviewer-based visualisations.

---

## Repository structure
health_literacy_data/
├─ Bib_Raw_Data/
│  ├─ WoS/Scopus exports after database-level filters (before Excel post-processing)
├─ Bib_Cleaned_Data/
│  ├─ Final cleaned datasets used in analysis (after Excel deduplication and year re-check)
├─ Citation_Raw_and_Cleaned_Data/
│  ├─ Citation-derived tables/files used for bibliometric indicators (if applicable)
├─ DataBase_Screening_Result/
│  ├─ PRISMA materials, exclusion/deduplication logs, and verification screenshots
├─ Search_Strategies/
│  ├─ Exact query strings, field definitions, and search screenshots
└─ VosViewer_Result/
├─ Scopus/
└─ Web_of_Science/
Exported VOSviewer files (nodes/links/maps) used to generate network maps and figures

---

## 1) Databases and search fields

### Databases
- **Web of Science (WoS) Core Collection**
- **Scopus**

### Search fields (metadata scope)
- **WoS**: `TS` (Topic) — searches *Title, Abstract, Author Keywords, and Keywords Plus*.
- **Scopus**: `TITLE-ABS-KEY` — searches *Title, Abstract, and Author Keywords*.

### Query logic
The search strategy combines three concept blocks with **AND**:
1) Health-related terms  
2) Literacy  
3) Older-adult terms  

Exact query strings (as executed) and screenshots are provided in:
- `Search_Strategies/`

---

## 2) Database-level filters (applied before export)

Database filters were applied prior to export to restrict:
- **Publication years**: 2014–2023  
- **Language**: English  
- **Document types retained**
  - **WoS**: article, early access, review article, book chapter, data paper  
  - **Scopus**: article, review article, book chapter, data paper  
    - *Note: Scopus does not provide “early access” as a separate document type.*

### Export exception (Scopus)
- **2 records were inaccessible at export time** and could not be downloaded (logged in PRISMA).

Supporting screenshots and PRISMA documentation are available in:
- `DataBase_Screening_Result/`

---

## 3) Post-export cleaning (Excel) and deduplication

After export, post-processing was performed in **Microsoft Excel** using the built-in **Remove Duplicates** function and simple matching keys. Deduplication/exclusion logs are provided in:
- `DataBase_Screening_Result/`

### Summary of post-export exclusions

**Scopus**
- Exact title duplicates removed: **19**
- Additional duplicates removed using **Source title + DOI**: **100**
- Inaccessible export (excluded): **2**

**WoS**
- Exact title duplicates removed: **6**
- Additional duplicates removed using **DOI + Author**: **1**
- Records outside 2014–2023 after metadata year verification removed: **44**

### Final retained datasets
- **WoS**: **5,122** records  
- **Scopus**: **9,888** records  

Cleaned datasets used for all analyses are available in:
- `Bib_Cleaned_Data/`

---

## 4) PRISMA documentation and screenshots

PRISMA flowchart materials, screening step counts, and supporting screenshots (database filters, export pages, and Excel steps) are provided in:
- `DataBase_Screening_Result/`

---

## 5) VOSviewer outputs (network analysis and visualisation)

VOSviewer is a GUI-based tool and does not generate executable scripts by default. Reproducibility is supported by providing:
- exported **node tables** (items, weights, clusters),
- exported **edge/link tables** (networks),
- exported **map/coordinate files** (positions used in figures).

All exported files used to generate maps/figures are available under:
- `VosViewer_Result/Scopus/`
- `VosViewer_Result/Web_of_Science/`

(If a thesaurus/term-cleaning file was used, it is stored under `VosViewer_Result/` or `Search_Strategies/`.)

---

## 6) How to verify / reproduce

Reviewers can verify the workflow by:
1) Re-running the exact queries (see `Search_Strategies/`)  
2) Confirming database-level filters (screenshots in `DataBase_Screening_Result/`)  
3) Comparing `Bib_Raw_Data/` → `Bib_Cleaned_Data/` using the deduplication/exclusion logs  
4) Recreating VOSviewer maps from `VosViewer_Result/` exports (using the same thresholds and settings as reported in the manuscript)

---

## Notes
- Database exports may be subject to database terms of use.
