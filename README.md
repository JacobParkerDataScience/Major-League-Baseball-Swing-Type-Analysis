# Major League Baseball Swing Type Analysis ⚾

### Author: Jacob Parker  
**Date:** July 28, 2025  

---

## 📌 Project Overview
This project analyzes **Major League Baseball swing types** using advanced metrics to identify natural groupings of hitters.  
The goal is to investigate how swing mechanics relate to offensive performance, measured primarily by **Weighted On-Base Average (wOBA)**.

---

## 🎯 Objectives
- Perform **k-means clustering** on swing characteristics.  
- Identify **natural groupings** of hitters based on swing type.  
- Compare clusters using **ANOVA** and **Tukey’s Post Hoc** tests.  
- Investigate which swing traits are associated with better outcomes such as:
  - Launch angle  
  - Contact rate  
  - Exit velocity  
  - Barrel % / Hard Hit %  
- Test differences in correlation strength using **Fisher’s Z transformation**.

---

## 📊 Data Sources
- [FanGraphs Leaderboards](https://www.fangraphs.com/)  
- [Baseball Savant](https://baseballsavant.mlb.com/)  

**Data Requirements:**
- Time Frame: *03/01/2023 – 07/18/2025*  
- Players with **300+ competitive swings** (fastest 90% of swings + all swings with 90+ mph exit velocity).  
- Final dataset: ~500 instances.  

---

## 🧪 Methodology
1. **Data Preprocessing**  
   - Standardization applied.  
   - Multicollinearity check (all VIF < 5).  

2. **K-Means Clustering**  
   - Optimal k = 3 (based on elbow method & silhouette score).  
   - PCA used to reduce noise (PCA1 + PCA2 captured ~50% variance).  

3. **Cluster Analysis**  
   - ANOVA + Tukey’s Post Hoc to compare variables.  
   - Correlation analysis per cluster.  
   - Fisher’s Z transformation to test correlation differences.  

---

## 🔎 Key Findings
- **Three distinct swing types (clusters) emerged:**
  1. **Contact Hitters** (e.g., Otto Lopez)  
     - Low launch angle (groundballs)  
     - High contact %, low strikeouts  
     - Lower Barrel % and Hard Hit %  
  2. **Balanced Hitters** (e.g., Pavin Smith)  
     - High Barrel % & Hard Hit %  
     - Lower contact % (more strikeouts)  
     - Strongest relationship between **bat speed and wOBA**  
  3. **Power Hitters** (e.g., Max Muncy)  
     - High Launch Angle (flyballs)  
     - High Pull Air %  
     - Moderate Hard Hit % & Barrel %  

- **Fisher’s Test Results:**  
  - Bat speed has a **significantly stronger impact** on wOBA for Cluster 2 compared to the population and other clusters.  

---

## 📈 Conclusions
- Hitters can be separated into **three swing types** with different batted-ball profiles.  
- Only **Clusters 1 and 2** show significant differences in **wOBA**.  
- Players in **Cluster 2 (Balanced Hitters)** are the most successful when paired with high bat speed.  

---

## 🚀 Future Scope
- Expand analysis to **pitch-level data**.  
- Explore **time-series trends** (swing evolution over seasons).  
- Integrate **machine learning models** to predict player outcomes.  

---

## 📂 Repository Structure
- `data/` → Collected datasets  
- `notebooks/` → R scripts for clustering & analysis.  
- `presentation/` → Final project slides.  
- `README.md` → Project summary (this file).   

---

## 🙏 Acknowledgments
- **Data:** Baseball Savant, FanGraphs  
- **Resources:**  
  - *K-Means Clustering in R: Step-by-Step Example*  
  - *The R Graph Gallery*  
  - ISLR & course resources  

---
