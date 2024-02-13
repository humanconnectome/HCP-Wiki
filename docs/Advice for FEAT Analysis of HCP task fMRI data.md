## Advice for FEAT Analysis of HCP task fMRI data.

For users who would like to run their own group analyses on task fMRI data, the simplest way currently is to begin with the "Level 2" analyses that are included as part of the 500 Subject Release. The precomputed second-level analyses are Fixed Effects analyses which effectively combine the two first-level analyses. Thus, the output is basically equivalent to combining the two lower-level datasets and doing a single timeseries (lower-level FEAT) analysis. The 500 Subject Release included subject-level ("Level 2") analyses in both volume and grayordinate spaces (at various smoothing levels), and is the preferable set of data to use because it features some improvements to registration.

### Higher-level Analysis

When setting up Higher-level analysis of volume data in the FEAT GUI, choose that "Inputs are lower-level FEAT directories". Under "Select FEAT directories", for each participant in your group analysis, enter the paths to the .feat directories for the specific lower-level cope of interest (e.g., /myCinaB/100307/MNINonLinear/Results/tfMRI\_WM/tfMRI\_WM\_hp200\_s4\_level2vol.feat/cope11.feat). See  if you need to find the names of the contrasts. The contrast names are also stored in the lower-level fsf file (e.g., grep name\_orig /myCinaB/100307/MNINonLinear/Results/tfMRI\_WM\_RL/tfMRI\_WM\_RL\_hp200\_s4\_level1.fsf) for grayordinates task packages.

### Scan or Individual Level Analysis (Levels 1 and 2)

The level1.fsf and **[prepare\_level2\_feat\_analysis.sh](./assets/prepare_level2_feat_analysis.sh)** 

**[prepare\_level2\_feat\_analysis.sh](./assets/prepare_level2_feat_analysis.sh)**

files are "legacy" files that were provided during previous releases which did not include the Level 2 feat directories. Nonetheless, you may have reasons to run your own scan-level ("lower-level" or "Level 1") analyses, such as using previous data releases, using different preprocessing options, or creating new custom EVs. The level1.fsf files will serve as a template for running those analyses using FEAT.

Because the minimal preprocessing pipelines perform registration to the MNI152 template, you should not run registration in the Level 1 analysis when using those data. In order to include those Level 1 .feat directories in subsequent higher-level analyses, however, FEAT expects certain registration files to be present which are typically created during the Level 1 analysis. The prepare\_level2\_feat\_analysis.sh script was intended to create those files in the Level 1 .feat directories prior to running a new Level 2 analysis. That script expects the precise naming convention and directory structure created by running the Level 1 .fsf without modification. If the prepare\_level2\_feat\_analysis.sh will not run, it might require modification for your analyses. It might also be easier to use this script as a template for writing your own script to suit your own needs.

### CIFTI compatibility

It is finally worth mentioning that only volume analyses in NIFTI format are supported by the current version of FEAT. If you would like to run group analyses of grayordinate data in CIFTI format, you will need to write your own custom scripts (e.g., using matlab or wb\_command). Our version here at HCP essentially converts the CIFTI data to NIFTI file format using wb\_command, runs feat on the NIFTI files, and then converts the NIFTI results back to CIFTI again using wb\_command. (Cluster post-stats are not appropriate when analyzing CIFTI data in this way.) In the future, the FMRIB expects to provide CIFTI-compliant versions of melodic, randomise, and several other necessary tools to run group-level analyses using ICA or permutation testing methods. When those tools arrive, we will work with the FMRIB group to provide a manual for running group analyses on HCP CIFTI data.

