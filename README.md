# Telomere and structural-variation analyses

This is my fork of the collaborative [Barthel Lab project](https://github.com/barthel-lab/telomere-SV-analysis). It contains Jupyter notebooks and scripts for telomere metrics, structural variation, clinical integration, extrachromosomal DNA, copy-number changes, and spatial analyses across TCGA and GLASS cohorts. I contributed analysis notebooks and figure workflows; the upstream repository preserves the lab-wide project history.

## Data

Processed genomics data are hosted on [Synapse](https://www.synapse.org/Synapse:syn72016012/datasets/) and are not included in this repository. Download the required data and update input paths in each notebook before running. Notebooks are grouped by figure and analysis topic; there is no guaranteed sequential run order.

## Analyses

**Figure 1 — Cohort overview and telomere metrics**
- `TCGA_GLASS_paired_samples_only_updated.ipynb` — paired TCGA and GLASS cohorts
- `TCGA_GLASS_unpaired_samples.ipynb` — unpaired cohort analysis
- `TCGA_telomere_associationplots_clean.ipynb` — TCGA telomere association plots
- `long-reads_cov_n50.ipynb` — long-read coverage and N50 metrics

**Figure 2 — Structural variants and clinical data**
- `clinical_data_heatmap.ipynb`
- `severus/`, `sniffles/`, and `CNVs/` — caller-specific structural-variant and copy-number analyses

**Figure 3 — Extrachromosomal DNA and genomic repeats**
- `decoil.ipynb` — ecDNA reconstruction with Decoil
- `HGs_extraction.ipynb` — copy-number gain extraction

**Figure 4 — Telomeres and genomic instability**
- `telomers_analysis_v2.ipynb` — telomere-length analysis
- `generate_figures.py` — figure generation and statistical modeling

**Figure 5 — Distance and spatial analyses**
- `TCGA_GLASS_distance_analysis.ipynb`
- `severus/` and `sniffles/` — spatial analyses for SV calls

**Additional analyses**
- `aneuploidy_plot.ipynb`
- `survival_analysis.ipynb`

## Environment

The following setup is for `generate_figures.py` only. It is not a complete environment for every notebook; check each notebook for additional dependencies and tools.

```bash
conda create -n telomere_env python=3.12 -y
conda activate telomere_env
pip install pandas numpy matplotlib seaborn scipy statsmodels
```

The notebooks have not been documented as a clean-install, end-to-end reproduction from this fork alone. See the upstream repository and the project data on Synapse for shared context and inputs.
