## HCP fMRI slice-timing acquisition parameters

The HCP has received requests for slice-timing parameters for the HCP fMRI data and, therefore, we are providing this information with some background as to why the HCP does not apply slice-timing correction as part of its functional preprocessing (see [Smith et al. "Resting-state fMRI in the Human Connectome Project" NeuroImage, vol. 80, pp. 144-168, Oct. 2013](http://www.sciencedirect.com/science/article/pii/S1053811913005338) and  [Glasser et al. “The minimal preprocessing pipelines for the Human Connectome Project” Neuroimage, vol. 80, pp. 105–124, Oct. 2013](http://www.sciencedirect.com/science/article/pii/S1053811913005053)).

Note that beyond just the issue of whether STC is even necessary or beneficial, the issue of *when* to apply STC in a processing stream is complicated and the subject of some debate, since from a theoretical perspective, motion correction and STC should really be applied jointly, rather than separately/serially in a processing stream ([Roche, 2011](https://ieeexplore.ieee.org/document/5737791/authors#authors)).

See:

<http://imaging.mrc-cbu.cam.ac.uk/imaging/SliceTiming>

<http://mindhive.mit.edu/node/109>

AFNI and SPM apply STC before motion correction, whereas FSL applies it after.  The FSL rationale is that applying STC after motion correction (and relatedly, gradient distortion correction) is preferable because you don't want to "bake in" errors related to spatial misalignment as part of STC, since spatial intensity differences between voxels can be much larger (e.g., CSF vs. gray matter) than temporal intensity changes over a TR.

This would be even more true for the short TR data of the HCP.  So, if STC is applied to HCP fMRI data, it is likely best to apply it to the minimally preprocessed data (i.e., after gradient nonlinearity correct, motion correction, and B0 distortion correction).

### **3T**

The slice timing of the HCP fMRI is non-trivial due to the multi-band nature of the acquisition (MB=8 was used on rfMRI and tfMRI). Examples of the timing for both an even or odd number of total slices, and differing MB factors are provided in the following file:    

The current version of the MB sequence is available here: <https://www.cmrr.umn.edu/multiband/>

The TR for HCP fMRI is quite short at 0.72 sec. Because of the short TR, HCP consortium members felt the value of slice timing correction (STC) for HCP fMRI data is limited.  Therefore we have opted not to slice-time correct the task or resting state data in our HCP processing.

If you still feel it is necessary to do slice timing correction, you will need to account for the non-trivial nature of slice acquisition in the MB acquisitions. Although we aren't distributing DICOMs (due to their size and the presence of privileged information in them), we do have slice time order/acquisition information available in the original DICOM headers.

In the following text file, we have extracted the slice timing order info for an exemplar subject. Note that these values are only accurate to 2.5 ms:

BOLD acquisition times (in ms) extracted from {Subject\_ID}/REST1\_RL, 2nd DICOM: 

### **7T**

Assuming that the sequence at the time of the HCP-YA 7T data collection encoded the slice-time information correctly, this should be the slice timing info for the 7T fMRI data [obtained from the sidecar json by running a modern version of dcm2niix (“v1.0.20220720”) on a set of fMRI DICOMS from the 7T data]:

Note that these values should only be considered accurate to 0.0025 sec. (2.5 ms)  



```
        "SliceTiming": [  
                0,  
                0.5325,  
                0.06,  
                0.59,  
                0.12,  
                0.65,  
                0.1775,  
                0.71,  
                0.2375,  
                0.7675,  
                0.295,  
                0.8275,  
                0.355,  
                0.8875,  
                0.415,  
                0.945,  
                0.4725,  
                0,  
                0.5325,  
                0.06,  
                0.59,  
                0.12,  
                0.65,  
                0.1775,  
                0.71,  
                0.2375,  
                0.7675,  
                0.295,  
                0.8275,  
                0.355,  
                0.8875,  
                0.415,  
                0.945,  
                0.4725,  
                0,  
                0.5325,  
                0.06,  
                0.59,  
                0.12,  
                0.65,  
                0.1775,  
                0.71,  
                0.2375,  
                0.7675,  
                0.295,  
                0.8275,  
                0.355,  
                0.8875,  
                0.415,  
                0.945,  
                0.4725,  
                0,  
                0.5325,  
                0.06,  
                0.59,  
                0.12,  
                0.65,  
                0.1775,  
                0.71,  
                0.2375,  
                0.7675,  
                0.295,  
                0.8275,  
                0.355,  
                0.8875,  
                0.415,  
                0.945,  
                0.4725,  
                0,  
                0.5325,  
                0.06,  
                0.59,  
                0.12,  
                0.65,  
                0.1775,  
                0.71,  
                0.2375,  
                0.7675,  
                0.295,  
                0.8275,  
                0.355,  
                0.8875,  
                0.415,  
                0.945,  
                0.4725  ]
```


### Attachments

- [CMRR_MB_Slice_Order.pdf](./assets/CMRR_MB_Slice_Order.pdf)
- [MosaicRefAcqTimes.txt](./assets/MosaicRefAcqTimes.txt)
