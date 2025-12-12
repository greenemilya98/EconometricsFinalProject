# EconometricsFinalProject

# Replicating Acemoglu, Johnson, and Robinson (2001)  
**“The Colonial Origins of Comparative Development”**

This repository contains an empirical replication of Acemoglu, Johnson, and Robinson (2001), 
*The Colonial Origins of Comparative Development: An Empirical Investigation*, using R and Quarto.

The goal is to (i) reproduce the main tables and core empirical claims of the paper using publicly available data, 
and (ii) provide a clean, fully reproducible workflow that makes the identification strategy and robustness checks transparent.

---

## Data and Original Code

All data used in this replication come from the public materials provided by
Acemoglu, Johnson, and Robinson (2001). 

The original archive includes separate data and Stata do-files for:

- Table 1: Summary statistics  
- Table 2: OLS regressions  
- Table 3: Determinants of institutions  
- Table 4: IV regressions of log GDP per capita  
- Table 5: IV regressions of log GDP per capita with additional controls  
- Table 6: Robustness checks for IV regressions  
- Table 7: Geography and health variables  
- Table 8: Overidentification tests  

---

## 1. Overview

Acemoglu, Johnson, and Robinson (AJR) argue that:

1. Historical settler mortality shaped the type of colonial institutions (inclusive vs. extractive).
2. These early institutions persisted and strongly influenced modern institutional quality.
3. Institutional quality, in turn, has a large causal effect on long-run economic performance.

This replication reproduces the main OLS and 2SLS estimates of the impact of institutions on income.

---

## 2. Repository Structure

- `replicating_acemoglu_2001.qmd`  
  Main Quarto document that loads data, runs all regressions, produces tables and figures, and explains the identification strategy.

- **Data**  
  The replication uses AJR’s public `.dta` files hosted online, including:
  - `maketable1.dta` – descriptive statistics  
  - `maketable2.dta` – OLS regressions  
  - `maketable3.dta` – determinants of institutions  
  - `maketable4.dta` – 2SLS estimates  
  - `maketable5.dta` – controls for colonial origin, legal origin, religion  
  - `maketable6.dta` – geography & resources robustness  
  - `maketable7.dta` – health robustness  
  - `maketable8.dta` – alternative instruments & overidentification tests  

---

## 3. Software and Packages

This project uses **R** and **Quarto**. Required packages:

- `tidyverse`
- `janitor`
- `broom`
- `sandwich`
- `lmtest`
- `clubSandwich`
- `knitr`
- `kableExtra`
- `haven`
- `fixest`
- `gt`
- `modelsummary`
- `purrr`

---

## 4. What is Replicated?

The replication follows AJR closely:

### **5.1 Descriptive Statistics (Table 1)**  
- Means and SDs for income, institutions, and settler mortality.  
- Quartiles of mortality.  
- Scatterplots showing instrument relevance.

### **5.2 OLS Regressions (Table 2)**  
- Baseline income–institutions correlations.  
- Latitude & continent controls.

### **5.3 Determinants of Institutions (Table 3)**  
Tests the causal chain:  
Settler mortality → settlements → early institutions → modern institutions.

### **5.4 2SLS Estimates (Table 4)**  
Main causal estimate of institutional quality on income.  
Includes first stages and OLS comparisons.

### **5.5 Additional Controls (Table 5)**  
Includes controls for:
- Colonial origin  
- Legal origin  
- Religion  

### **5.6 Geography & Resources Robustness (Table 6)**  
Controls for:
- Temperature  
- Humidity  
- Soil quality  
- Natural resources  
- Ethnolinguistic fractionalization  

### **5.7 Health Robustness (Table 7)**  
Controls for:
- Malaria  
- Life expectancy  
- Infant mortality  

Also instruments health variables jointly with institutions.

### **5.8 Overidentification Tests (Table 8)**  
Uses multiple instruments and reports Sargan test p-values.

---

## 5. Contributions of This Replication

This project contributes:

### **1. A fully reproducible workflow**  
Everything—from data download to final tables—is reproducible in one Quarto file.

### **2. Clean modern implementation**  
Using `fixest`, `modelsummary`, and `gt` gives good readability and transparency.

### **3. Additional visualizations**  
Scatterplots help illustrate instrument relevance beyond numerical tables.

---

## 7. Limitations

- Coefficients may differ slightly from the original paper because the publicly available `.dta` files are not identical to AJR’s internal dataset.
- Some country coding and missingness issues vary between versions.
- Replication assumes GitHub-hosted data remains available.

---

## 8. References

Acemoglu, Daron, Simon Johnson, and James A. Robinson.  
*The Colonial Origins of Comparative Development: An Empirical Investigation.*  
American Economic Review, 2001.

Acemoglu, Daron, Simon Johnson, and James A. Robinson.  
*The Colonial Origins of Comparative Development: Reply.*  
American Economic Review, 2012.

Ghosh, Agniva. “Replication of Econometrics in R.” RPubs, 2024–2025.
