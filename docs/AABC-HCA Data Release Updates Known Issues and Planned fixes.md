## Aging Adult Brain Connectome (AABC) Data Release Updates Known Issues and Planned fixes
On this wiki page, we document known updates, data issues, bugs, and known missing files in the data distributed with each release and plans to fix or patch each bug. Date added is listed at the beginning of entries.

### AABC Release 1 (October 23, 2025)

The Aging Adult Brain Connectome (AABC) is a longitudinal extension of the HCP-Aging (HCA) project and is releasing imaging data collected on subjects recruited for one or both projects. Details on what data are included in each release are available from the [HCP-Aging/AABC documentation page](https://www.humanconnectome.org/study/hcp-lifespan-aging/documentation).  
### **Major Issues fixed from HCA 2.0 Release**

* **11/13/2023: **Testosterone units change across HCA subjects****

*The lab used to determine blood testrosterone levels for HCA changed reported units between batches of subjects across the study causing a 100x difference in values for subjects on the different scales. Due to the typical differences in testosterone levels between males and females the scale difference causes ambiguity in the data.*

Planned fix:Using the raw data we had the lab recalculate testosterone levels across HCA. New values are included in AABC Release 1.

* **11/10/2023: **Missing components/Miscalculated summary scores for PSQI, IPAQ, and MOCA****

*Summary scores for Pittsburg Sleep Quality Index (PSQI), International Physical Activity Questionnaires (IPAQ), and Montreal Cognitive Assessment (MoCA), were miscalulated for some subjects with component scores of values not specified correctly and deemed missing by the RedCAP scoring algorithm.*

Planned fix:The missing component scores have been restored and summary scores recalculated and both are included in AABC Release 1.

* **3/27/2023: **Subject HCD0026119 missing one resting state run in the unprocessed data****

*The rfMRI\_REST2\_PA run is missing in the unprocessed dataset on NDA, but is present in the preprocessed dataset on NDA. The missing run was dropped from the unprocessed data upload unintentionally.*

Planned fix:The missing unprocessed run is included in AABC Release 1. 

  


### **Minor Issues & Updates from HCA 2.0 Release**

* *8/29/23: **Incorrect values for tmta\_raw & tmtb\_raw for subject HCA9323978***

*The values for tmta\_raw & tmtb\_raw for subject HCA9323978 are too low to be reasonable for the Trails instrument. In the data cleaning between the LS2.0 release and AABC Release 1 this was caught and corrected.*

Planned fix:The correct data for this subject is included in AABC Release 1.  


  


  


  


  




