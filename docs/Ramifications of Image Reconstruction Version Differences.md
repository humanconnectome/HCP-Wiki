## Ramifications of Image Reconstruction Version Differences

In the spring of 2013, several months after the commencement of HCP Phase II scanning, an improved reconstruction algorithm was developed that reduced spatial blurring in fMRI and dMRI acquisitions. In brief, the original reconstruction algorithm performed the separation of the multi-band multi-slice images after transforming the acquired fully sampled data to frequency space along the read-out direction, and now the multi-band multi-slice separation is performed in k-space. See [S500+MEG2 Reference Manual](http://humanconnectome.org/documentation/S500/HCP_S500+MEG2_Release_Reference_Manual.pdf), p. 35: Image Reconstruction and DICOM to NIFTI conversion, for more details.

Therefore, the reconstruction algorithm was upgraded in late April 2013. In addition, the new reconstruction method was applied retrospectively to dMRI scans acquired prior to the April 2013 transition that were saved in a compact but unreconstructed data format. For fMRI scans prior to April 2013, unreconstructed scans were not preserved owing to technical considerations related to the time required to complete reconstruction at the scanner. Therefore, some of the HCP fMRI data being distributed has been reconstructed with the original r177 ICE version and some with the r227 upgraded ICE version.

The reconstruction version makes a notable signature on the data that can make a large difference in fMRI data analysis. Users wanting to use only data with the same reconstruction algorithm applied in their analyses can filter data on the ConnectomeDB dashboard by fMRI reconstruction version (in the Study Completion category), see below. Alternatively, the same information (i.e., reconstruction version) could be used to create "confound regressors" for certain cross-subject analyses, although the extent to which this potential confound can be fully accounted for by additive modelling has not been fully characterized.

Network matrices (a.k.a. "netmats") derived from the resting state fMRI data of Q1, Q2, Q3, and Q6 (Q4-Q6 data included in the S500 release) can predict the reconstruction version of the fMRI data of subjects at an accuracy of >99%. The following scatter plot shows the predicted recon version vs. measured recon version for all 468 S500 subjects from Q1-Q6 that had 4 complete rfMRI scans. For all but one of the subjects, the reconstruction algorithm version of the rfMRI scans was accurately predicted by netmats. For the 6 subjects with unknown recon version, we can make a good prediction that the 3 in the top middle had scans reconstructed with the r227 version and the 3 in the bottom middle had scans reconstructed with the r177 version. 

 ![](./assets/Recon_scatterplot_labels.png) 

For both dMRI and fMRI, the image reconstruction version is noted in ConnectomeDB and can be filtered against in the Study Completion category on the dashboard (see [S500+MEG2 Reference Manual](http://humanconnectome.org/documentation/S500/HCP_S500+MEG2_Release_Reference_Manual.pdf), p. 21: How to explore HCP data in ConnectomeDB).



### Attachments

- ![](./assets/Recon_scatterplot_labels.png)
- ![](./assets/image2015-3-12 15:50:6.png)
