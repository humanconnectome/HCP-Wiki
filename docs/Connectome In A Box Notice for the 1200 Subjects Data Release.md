## Connectome In A Box Notice for the 1200 Subjects Data Release

Unlike previous data releases that we have shipped on "Connectome In A Box" hard drives, **we are distributing image session data as .zip packages for the 1200 Subjects data release**. This was done to reduce file I/O during the drive duplication process, which radically reduces the number of errors and failed drives that we encounter. It also reduces the number of 8-TB hard drives necessary to ship this data release from 13 to 12. 

### Warning: Connectome In A Box hard drives are meant to be used as data transport vehicles

Because we are distributing zipped packages of image session data, **purchasers will need to have ~100 TB of readily available disk space to unzip these packages into**. It will not be possible to merely take these hard drives, plug them into a storage array, and start accessing image session data directly. 

### Unpacking zipped image sessions

These packages unpack into the same directory structure as the unzipped image sessions that we previously distributed. For example, an unprocessed 3T MR session zip archive will unpack into the following directory structure: 

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

For further reference, see . A full list of file names in each directory and subdirectory is provided in Appendix 3 of the S1200 documentation: **[File Names and Directory Structure for 1200 Subjects Data](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_III.pdf)**. 

