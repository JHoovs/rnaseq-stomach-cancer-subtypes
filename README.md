# Stomach Cancer RNA-Seq Analysis  

This repository contains an exploratory RNA-seq analysis of **stomach cancer cell lines** from the Cancer Cell Line Encyclopedia (CCLE).  
The project applies a full RNA-seq workflow in **R** using Bioconductor packages to identify biologically distinct subtypes, visualize expression patterns, and highlight differentially expressed genes and lncRNAs.  

---

## 📖 Overview  

The analysis addresses the question:  

**How many biologically distinct subtypes exist among stomach cancer cell lines in CCLE, and what do their gene expression profiles reveal?**  

Key steps include:  
- **Preprocessing & QC** of RNA-seq counts and cell line annotations  
- **Normalization** using variance-stabilizing transformation (VST)  
- **Exploratory Analysis** with PCA and hierarchical clustering  
- **Differential Expression Analysis** with DESeq2  
- **Subtype Characterization** highlighting both protein-coding genes and lncRNAs  

---

## 🧰 Methods & Tools  

- **R / Bioconductor packages**:  
  - `DESeq2` (differential expression & normalization)  
  - `ComplexHeatmap` (clustering & heatmaps)  
  - `biomaRt` (gene biotype annotation)  
  - `EnhancedVolcano`, `ggplot2`, `patchwork` (visualization)  

- **Analyses performed**:  
  - Variance–stabilizing normalization (VST)  
  - Principal Component Analysis (PCA)  
  - Hierarchical clustering of expression profiles  
  - Identification of subtype-defining genes & lncRNAs  

---

## 📊 Data  

- **`data/stomach_cell_line_subset.csv`**: Subset of CCLE RNA-seq counts for stomach cancer cell lines (genes × samples)  
- **`data/stomach_cell_line_ann.csv`**: Sample annotations (metadata for stomach cancer cell lines)  

Raw RNA-seq counts were obtained from the **CCLE 2018 release** via the Broad Institute’s DepMap portal:  
👉 [CCLE_RNAseq_genes_counts_20180929.gct.gz](https://depmap.org/portal/download/)  

To keep this repository lightweight, only the stomach cancer subset is included.  

---

## 📈 Results  

Key findings and outputs are stored in the `results/` folder, including:  
- **Normalization diagnostics** (mean–variance, coefficient of variation before/after VST)  
- **PCA plots** showing major axes of variation  
- **Hierarchical clustering** identifying subgroups of stomach cancer cell lines  
- **Top differentially expressed genes (DEGs)** driving subtype separation  
- **Top lncRNAs** with significant expression differences between clusters  

### Biological Insights  
- **Subtype 1**: Epithelial–intestinal program (↑ *MUC17, MUC5AC, REG4*) → Maintains epithelial differentiation  
- **Subtype 2**: Dedifferentiated, mesenchymal-like program (↑ *MAGEA4/10, ADAMTS12, WNT5A-AS1*) → EMT, immune evasion, invasive potential  

These findings suggest opportunities for **biomarker discovery** and **therapeutic targeting** (e.g., WNT/EMT signaling, cancer-testis antigens).  

---

## 📂 Repository Structure  

```bash
.
├── data/
│   ├── stomach_cell_line_ann.csv       # Metadata for stomach cell lines
│   └── stomach_cell_line_subset.csv    # Stomach subset of RNA-seq counts
│
├── results/                            # Output plots and figures
│   ├── vst_normalization_plots.png
│   ├── pca_plots.png
│   ├── clustering_heatmaps.png
│   ├── top_genes_deg.png
│   └── top_lncrna_deg.png
│
├── stomach-cancer-analysis.pdf         # Full RMarkdown report (code + figures)
└── README.md
'''

## 🚀 How to Run  

1. Clone the repository:  
   ```bash
   git clone https://github.com/JHoovs/stomach-cancer-rnaseq-analysis.git
   cd stomach-cancer-rnaseq-analysis

2. Open R and install required packages:
  install.packages(c("tidyverse", "ggplot2", "patchwork"))
  BiocManager::install(c("DESeq2", "ComplexHeatmap", "biomaRt", "EnhancedVolcano"))

3. Knit the RMarkdown (.Rmd) file or run the provided code chunks to reproduce results.

## 📌 Citation

Barretina J, et al. (2012). The Cancer Cell Line Encyclopedia enables predictive modelling of anticancer drug sensitivity. Nature 483, 603–607.

Data accessed from the Broad Institute DepMap portal (2018 release).

## Author

Jacob Hoover
**Bioinformatics & Computational Biology**
