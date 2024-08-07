## Lifespan HCP Data Release Updates Known Issues and Planned fixes

The Lifespan Human Connectome Project (HCP) HCP-Aging and HCP-Development projects release imaging data collected on subjects on a regular basis. Details on what data is included in each release are available in the Reference Manual for that release on the [Lifespan documentation page](https://www.humanconnectome.org/study/hcp-lifespan-aging/documentation).  On this wiki page, we document known updates, data issues, bugs, and known missing files in the data distributed with each release and plans to fix or patch each bug. Date added is listed at the beginning of entries.

### LS 2.0 Release (February 26, 2021)

#### **Major Issues**

* **7/29/2024: **Missing NIH Toolbox Sadness ages 8-17 fixed form self-report data****

**A bug in the code transferring to NDA structures was found that overwrote NIH Toolbox Sadness ages 8-17 fixed form self-report data with parent data causing the self-report data to be omitted from the 2.0 release.**

Planned fix: We have removed the bug and the NIH Toolbox Sadness ages 8-17 fixed form self-report data will be included in the 3.0 release. 

* **11/13/2023: **Testosterone units change across HCA subjects****

**The lab used to determine blood testrosterone levels for HCA changed reported units between batches of subjects across the study causing a 100x difference in values for subjects on the different scales. Due to the typical differences in testosterone levels between males and females the scale difference causes ambiguity in the data.**

Planned fix:Using the raw data we are having the lab recalculate testosterone levels across HCA. New values will be included in the LS 3.0 release.

* **11/10/2023: **Missing components/Miscalculated summary scores for PSQI, IPAQ, and MOCA****

**Summary scores for Pittsburg Sleep Quality Index (PSQI, both HCA and HCD subjects 18+), International Physical Activity Questionnaires (IPAQ, HCA only), and Montreal Cognitive Assessment (MoCA, HCA only), were miscalulated for some subjects with component scores of values not specified correctly and deemed missing by the RedCAP scoring algorithm.**

Planned fix:The missing component scores will be restored and summary scores recalculated to be included in the LS 3.0 release.

* **3/27/2023: **Subject HCD0026119 missing one resting state run in the unprocessed data****

**The rfMRI\_REST2\_PA run is missing in the unprocessed dataset on NDA, but is present in the preprocessed dataset on NDA. The missing run was dropped from the unprocessed data upload unintentionally.**

Planned fix:The missing unprocessed run will be included in the LS 3.0 release. We will incorporate extra checks for missing folders in the next round of uploads to NDA.

  


#### **Minor Issues & Updates**

* *8/29/23: **Incorrect values for tmta\_raw & tmtb\_raw for subject HCA9323978***

*The values for tmta\_raw & tmtb\_raw for subject HCA9323978 are too low to be reasonable for the Trails instrument. In the data cleaning between the LS2.0 and LS3.0 releases this was caught and corrected.*

Planned fix:The correct data for this subject will be included in the LS 3.0 release.  


  


  


  


  




#### Attachments

- [prepare_level2_feat_analysis.sh](./assets/prepare_level2_feat_analysis.sh)
