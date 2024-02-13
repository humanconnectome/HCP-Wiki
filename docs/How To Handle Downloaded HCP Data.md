## How To Handle Downloaded HCP Data

Now that you have downloaded the data you want, here’s some tips for handling the data:

* Each download package consists of a .zip archive, and an md5 checksum. After you download the data you want, you can use the md5 file to verify the integrity of your downloaded file. [See this tutorial on codejacked.com for MD5 verification instructions](http://www.codejacked.com/using-md5sum-to-validate-the-integrity-of-downloaded-files/).
* To unzip the downloaded .zip archives, for Windows users we recommend using a utility such as [7-zip](http://www.7-zip.org/) (available free) so that the directory structure of the unzipped files remains intact. The built-in unzip capabilities of Linux and MacOSX can be used, as they do not affect the directory structure of the unzipped files.
* Once the archives are downloaded and unzipped, many of the component files are gzipped (.gz files). You will need to unzip all.gz files in order to use them. For this, you need an application that is compatible with gzip. For Windows users, we again recommend 7-zip. Linux has support for gzip built in, and Mac users can use the Mac Gzip utility.
* Downloaded HCP data unzips to a set directory structure that is detailed below in Directory structure for unprocessed MR data, Directory structure for preprocessed MR data, and in [Appendix 3: File Names and Directory Structure for 1200 Subjects Data](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_III.pdf). The directory structure for downloaded HCP data is identical to what is provided in Connectome in a Box.
* If you have downloaded a large amount of HCP data, we recommend sharing the data locally at your research institution. This will save download and organization time for your colleagues and relieve some of the burden on the ConnectomeDB download bandwidth available to other HCP users.

> [!warning] 
> If you distribute HCP data in any way, all users must register via ConnectomeDB and sign the Open Access Data Use Terms in order to comply with regulations on human subjects research.
  


### Directory Structure for Unprocessed MR Data

Unprocessed datasets downloaded from ConnectomeDB are organized into subject-specific and modality-specific archives. When unpacked, they are moved into a <subject\_id>/unprocessed/3T/ subdirectory (by creating it if not present, or placing into existing directories if present). If you have ordered Connectome in a Box, the directory structure is the same as the unpacked downloaded data. A full list of file names in each directory and subdirectory is provided in [Appendix 3: File Names and Directory Structure for 1200 Subjects Data](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_III.pdf), Section A.

Unprocessed data for exemplar subject 100307 unpacks to the following directory structure:

```
100307/unprocessed/3T/
	100307_3T.csv
	Diffusion/
	rfMRI_REST1_LR/
	rfMRI_REST1_RL/
	rfMRI_REST2_LR/
	rfMRI_REST2_RL/
	T1w_MPR1/
	T2w_SPC1/
	tfMRI_EMOTION_LR/
	tfMRI_EMOTION_RL/
	tfMRI_GAMBLING_LR/
	tfMRI_GAMBLING_RL/
	tfMRI_LANGUAGE_LR/
	tfMRI_LANGUAGE_RL/
	tfMRI_MOTOR_LR/
	tfMRI_MOTOR_RL/
	tfMRI_RELATIONAL_LR/
	tfMRI_RELATIONAL_RL/
	tfMRI_SOCIAL_LR/
	tfMRI_SOCIAL_RL/
	tfMRI_WM_LR/
	tfMRI_WM_RL/
```

The 3T/ subdirectory signifies that these data were acquired on the 3T Connectome Skyra at Wash U.

For the subjects that are scanned at 7T (184 of the 1206), the 7T data unpack to a 7T/ subdirectory. The .csv file contains the subject-specific spreadsheet of scan session data, which provides useful metadata about the scans acquired for this particular subject. An example of the spreadsheet is available as [Appendix 5: MR Data Acquisition Information for an Exemplar Subject](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_V.pdf).  
Within each subdirectory, files are named as indicated by the exemplars below for several scan types.

```
T1w_MPR1/
	100307_3T_AFI.nii.gz
	100307_3T_BIAS_32CH.nii.gz
	100307_3T_BIAS_BC.nii.gz
	100307_3T_FieldMap_Magnitude.nii.gz
	100307_3T_FieldMap_Phase.nii.gz
	100307_3T_T1w_MPR1.nii.gz
T2w_SPC1/
	100307_3T_AFI.nii.gz
	100307_3T_BIAS_32CH.nii.gz
	100307_3T_BIAS_BC.nii.gz
	100307_3T_FieldMap_Magnitude.nii.gz
	100307_3T_FieldMap_Phase.nii.gz
	100307_3T_T2w_SPC1.nii.gz
```

The FieldMap, BIAS, and AFI scans are ancillary files copied into multiple structural subdirectories, in order to facilitate using standardized scripts and pipelines.

If multiple structural scans for a given subject passed the QC criteria and are included in ConnectomeDB, they will be in separate subdirectories T1w\_MPR2/ and/or T2w\_SPC2, with uniquely named structural files (e.g. 100307\_3T\_T1w\_MPR2.nii.gz and/or 100307\_3T\_T2w\_SPC2.nii.gz). Each subdirectory will include copies of relevant ancillary files needed for preprocessing.

The four 15-min rfMRI scans for each subject are downloaded into separate subdirectories, because the initial preprocessing is carried out separately for each scan.

```
rfMRI_REST1_LR
	100307_3T_BIAS_32CH.nii.gz
	100307_3T_BIAS_BC.nii.gz
	100307_3T_rfMRI_REST1_LR_SBRef.nii.gz
	100307_3T_rfMRI_REST1_LR.nii.gz
	100307_3T_rfMRI_REST1_LR_Physio_log.txt
	100307_3T_SpinEchoFieldMap_LR.nii.gz
	100307_3T_SpinEchoFieldMap_RL.nii.gz
rfMRI_REST1_RL
	100307_3T_BIAS_32CH.nii.gz
	100307_3T_BIAS_BC.nii.gz
	100307_3T_rfMRI_REST1_RL_SBRef.nii.gz
	100307_3T_rfMRI_REST1_RL.nii.gz
	100307_3T_rfMRI_REST1_RL_Physio_log.txt
	100307_3T_SpinEchoFieldMap_LR.nii.gz
	100307_3T_SpinEchoFieldMap_RL.nii.gz
```

Here, the ancillary files are SpinEchoFieldMap and BIAS scans acquired at the beginning of the rfMRI session and copied into both the rfMRI\_REST1\_LR/ and rfMRI\_REST1\_RL/ directories to simplify preprocessing scripts.

For tfMRI scans, the 14 scans (7 tasks x two phase encoding directions) are downloaded into separate subdirectories, because the initial preprocessing is carried out separately for each scan. For example, the working memory (WM) LR phase encoding imaging data:

```
tfMRI_WM_LR
	100307_3T_BIAS_32CH.nii.gz
	100307_3T_BIAS_BC.nii.gz
	100307_3T_SpinEchoFieldMap_LR.nii.gz
	100307_3T_SpinEchoFieldMap_RL.nii.gz
	100307_3T_tfMRI_WM_LR.nii.gz
	100307_3T_tfMRI_WM_LR_SBRef.nii.gz
```

and the relevant E-Prime data are in appropriate subdirectories:

```
tfMRI_WM_LR/LINKED_DATA/EPRIME
	100307_3T_REC_run2_TAB.txt
	100307_3T_WM_run2_TAB.txt
tfMRI_WM_LR/LINKED_DATA/EPRIME/EVs
	0bk_body.txt
	0bk_cor.txt
	0bk_err.txt
	0bk_faces.txt
	0bk_nlr.txt
	etc…
```

and the relevant Physiological data are in the PHYSIO subdirectory:

```
tfMRI_WM_LR/LINKED_DATA/PHYSIO/
	100307_3T_tfMRI_WM_LR_Physio_log.txt
```

  


> [!note] Note
> Note that inclusion of an ancillary file in any given directory does not necessarily mean that it is used as part of the current HCP preprocessing pipelines. For example, the BIAS and AFI scans are not used currently (for any modality) for the preprocessed data.
The 6 dMRI scans (3 b-values x two phase encoding directions) are in a single Diffusion/ subdirectory:

```
Diffusion/
	100307_3T_BIAS_32CH.nii.gz
	100307_3T_BIAS_BC.nii.gz
	100307_3T_DWI_dir95_LR.bval
	100307_3T_DWI_dir95_LR.bvec
	100307_3T_DWI_dir95_LR.nii.gz
	100307_3T_DWI_dir95_LR_SBRef.nii.gz
	100307_3T_DWI_dir95_RL.bval
	100307_3T_DWI_dir95_RL.bvec
	100307_3T_DWI_dir95_RL.nii.gz
	100307_3T_DWI_dir95_RL_SBRef.nii.gz
	100307_3T_DWI_dir96_LR.bval
	100307_3T_DWI_dir96_LR.bvec
	100307_3T_DWI_dir96_LR.nii.gz
	100307_3T_DWI_dir96_LR_SBRef.nii.gz
	100307_3T_DWI_dir96_RL.bval
	100307_3T_DWI_dir96_RL.bvec
	100307_3T_DWI_dir96_RL.nii.gz
	100307_3T_DWI_dir96_RL_SBRef.nii.gz
	100307_3T_DWI_dir97_LR.bval
	100307_3T_DWI_dir97_LR.bvec
	100307_3T_DWI_dir97_LR.nii.gz
	100307_3T_DWI_dir97_LR_SBRef.nii.gz
	100307_3T_DWI_dir97_RL.bval
	100307_3T_DWI_dir97_RL.bvec
	100307_3T_DWI_dir97_RL.nii.gz
	100307_3T_DWI_dir97_RL_SBRef.nii.gz
```

  


### Directory Structure for Preprocessed MR data

Preprocessed datasets downloaded from ConnectomeDB unpack into subdirectories under the <subject\_id>/ parent directory (by creating them if not present, or placing into existing directories if present). If you have ordered Connectome in a Box or are using HCP data in the AWS S3 bucket, the directory structure is the same as the unpacked downloaded data.

Preprocessing generates thousands of files, many of which are of little or no use. Therefore, in the preprocessed dataset package for each subject HCP only releases a subset of files that are likely to be of general use to investigators. A list of file names in each directory and subdirectory is provided in [Appendix 3B](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_III.pdf).

#### Structural data (both MSM-Sulc and MSM-All registered)

* **T1w/** contains T1w and T2w volume data
* **T1w/Native/** contains FreeSurfer surfaces in their native mesh and original dimensions after rigid-body rotation to AC-PC alignment.
* **MNINonLinear/** contains cortical surfaces and other data volumetrically registered to MNI152 space (using nonlinear FNIRT) followed by surface registration to Conte69 ‘164k\_fs\_LR’ mesh (Van Essen et al. 2012b) (via FreeSurfer fsaverage as an intermediate). A Connectome Workbench-readable \*164k\_fs\_LR.wb.spec file is included for quickly reading and visualizing many of these files in Workbench.
* **MNINonLinear/Native/** replicates some of the files in T1w/Native/ but contains additional files used during surface-based registration.
* **MNINonLinear/xfms/** contains files encoding the transformation between acpc and MNINonLinear volumetric space.
* **MNINonLinear/fsaverage\_LR32k/** contains files spatially downsampled to a 32k mesh (average vertex spacing of ~2 mm), which is useful for analyses of rfMRI and dMRI connectivity data. As above, a Connectome Workbench-readable \*32k\_fs\_LR.wb.spec file is included for quickly reading and visualizing many of these files in Workbench.

#### fMRI data

* **MNINonLinear/Results/** contains volumetric and CIFTI grayordinates data for rfMRI scans (15 min each), motion parameters, and physiological data in four subdirectories,
	+ rfMRI\_REST1\_RL
	+ rfMRI\_REST1\_LR
	+ rfMRI\_REST2\_RL
	+ rfMRI\_REST2\_LR

plus volumetric and CIFTI grayordinates data and physiological data for 7 pairs of tfMRI scans (each task run once with right-to-left and once with left-to-right phase encoding).

* + tfMRI\_EMOTION\_RL
	+ tfMRI\_EMOTION\_LR
	+ tfMRI\_GAMBLING\_RL
	+ tfMRI\_GAMBLING\_LR
	+ tfMRI\_LANGUAGE\_RL
	+ tfMRI\_LANGUAGE\_LR
	+ tfMRI\_MOTOR\_RL
	+ tfMRI\_MOTOR\_LR
	+ tfMRI\_RELATIONAL\_RL
	+ tfMRI\_RELATIONAL\_LR
	+ tfMRI\_SOCIAL\_RL
	+ tfMRI\_SOCIAL\_LR
	+ tfMRI\_WM\_RL
	+ tfMRI\_WM\_LR

The \*.d[type].nii files in these directories are in CIFTI format (based on NIFTI-2, hence the .nii extension), which can be directly read by the Connectome Workbench software, in which results from other modalities (structural-MR , fMRI, dMRI, MEG) can be also read and overlaid.

Each of the directories above contain an .fsf file and a “EVs” directory containing explanatory variables. These files can be used to run first-level analyses in the FSL 5 program FEAT. The directories above also contain a \*TAB.txt file containing the timing of events, so that researchers might create their own explanatory variables of interest.

#### Motion parameters

Estimates of motion parameters are saved into two different files: Movement\_Regressors.txt and Movement\_Regressors\_dt.txt. The first file (Movement\_Regressors.txt) contains 12 variables. The first six variables are the motion parameters estimates from a rigid-body transformation to the SBRef image acquired at the start of each fMRI scan.

* trans\_x (mm)
* trans\_y (mm)
* trans\_z (mm)
* rot\_x (deg)
* rot\_y (deg)
* rot\_z (deg)

The second six variables are temporal derivatives of those motion parameters

* trans\_dx
* trans\_dy
* trans\_dz
* rot\_dx
* rot\_dy
* rot\_dz

The second file (Movement\_Regressors\_dt.txt) contains 12 variables derived by removing the mean and linear trend from each variable in Movement\_Regressors.txt

The **MNINonLinear/Results/** directory also contains seven other directories, one for each task:

* tfMRI\_EMOTION
* tfMRI\_GAMBLING
* tfMRI\_LANGUAGE
* tfMRI\_MOTOR
* tfMRI\_RELATIONAL
* tfMRI\_SOCIAL
* tfMRI\_WM

In the preprocessed data, these directories contain an .fsf file that can be used to run analysis across the two runs of each task.

> [!note]
> HCP’s results of individual (within-subject) tfMRI analysis are available in “analysis” download packages separate from the preprocessed datasets. When unpackaged, these data will integrate into these task-specific directories (MNINonLinear/Results/…). See Individual (within-subject) tfMRI analysis results data and Appendix 3D for more details.
  


#### Diffusion Data

Diffusion data includes diffusion weighting, direction, time series, brain mask, and gradient nonlinearity data, with the following files and directory structure:

* **T1w/** contains T1w\_acpc\_dc\_restore\_1.25.nii.gz (structural volume sampled at the same resolution as the diffusion data)
* **T1w/Diffusion** contains the following subdirectories and files:
	+ bvals (contains the diffusion weighting (b-value) for each volume)
	+ bvecs (contains the diffusion direction (b-vector) for each volume)
	+ data.nii.gz (preprocessed diffusion time series file)
	+ nodif\_brain\_mask.nii.gz (brain mask in diffusion space)
	+ grad\_dev.nii.gz (contains the effects of gradient nonlinearities on the bvals and bvecs for each voxel)
  



  


