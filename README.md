# How do we assess body size in insects?  
### A study using native Australian bees

---

## Overview

This repository contains the analytical code and outputs for the manuscript:  
**"How do we assess body size in insects? A study using native Australian bees"**  

Our work evaluates morphological trait variation in native bee species and explores how these traits change through time, align with phylogenetic structure, and contribute to overall morphospace dynamics. Using long-term specimen data, we quantify temporal trends in body size, assess phylogenetic signal, and visualise trait-based evolutionary patterns.  

---

## Repository Structure

- **01_trait_phylogenetic_signal.R**  
  Calculates species-level mean trait values, prunes the phylogenetic tree, and tests for phylogenetic signal using **Blomberg’s K** and **Pagel’s λ**.  
  *Outputs:*  
  - Table of trait-specific phylogenetic signal results (`phylo_signal_updated_traits.csv`)

- **02_trait_slopes_and_forestplots.R**  
  Fits temporal regressions of morphological traits against year, estimates slopes (percent change per year), and visualises species–trait changes using forest plots.  
  *Outputs:*  
  - Species–trait slope estimates  
  - Forest plots of temporal trait trends  
  - Integrated summary tables (`final_trait_phylo_summary.csv`)  

- **03_morphospace_distances.R**  
  Runs global PCA on seven focal traits across decades, calculates Euclidean distances in trait space, and quantifies cumulative morphospace displacement for each species.  
  *Outputs:*  
  - Barplots of decade-to-decade morphospace shifts  
  - Cumulative displacement plots per species  

- **04_phylogenetic_pPCA.R**  
  Performs **phylogenetic PCA (pPCA)** to account for evolutionary relatedness when analysing multivariate trait structure. Produces biplots of species in morphospace and trait loadings.  
  *Outputs:*  
  - Species scatterplot in pPCA space (`pPCA_species.png`)  
  - Trait loading plot on pPCA axes (`pPCA_traits.png`)  

---

## Key Analyses

### Temporal trait trends
We modelled log-transformed morphological traits as a function of year for each species. Significant slopes indicate consistent directional changes in body size traits over time. Forest plots summarise both the effect sizes and confidence intervals.

### Phylogenetic signal
We quantified evolutionary conservatism in traits using **Blomberg’s K** and **Pagel’s λ**. These complementary statistics test whether closely related species resemble each other more than expected under random trait evolution.

### Morphospace displacement
By projecting species–decade trait means into PCA space, we estimated **Euclidean distances** between decades, providing a metric of how much species shifted through morphospace over the 20th century.

### Phylogenetic PCA
To visualise the combined influence of traits while incorporating shared ancestry, we used phylogenetic PCA. Species positions in morphospace highlight clustering and divergence, while trait loadings identify which traits drive variation along principal axes.

---

## Figures

- **Forest plots:** Temporal changes in focal morphological traits per species.  
- **Morphospace distances:** Decadal displacement in PCA space and cumulative species-level displacement.  
- **pPCA plots:** Species scatter in phylogenetic morphospace and trait loadings on pPCA axes.  

---

## Requirements

This analysis was conducted in **R (≥ 4.2.0)** using the following packages:  

```r
library(dplyr)
library(ggplot2)
library(ape)
library(phytools)
library(vegan)
library(tidyr)
library(caper)
library(purrr)
library(pheatmap)
library(reshape2)
library(corrplot)
library(ggrepel)
