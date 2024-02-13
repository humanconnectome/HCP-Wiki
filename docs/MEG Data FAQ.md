## MEG Data FAQ

This page contains useful information for using preprocessed, channel-level, and source-level processed HCP MEG data. If you do not see your question and/or answer here, be sure to check the current HCP Reference Manual and join the [HCP-Users email list](http://humanconnectome.org/contact/#subscribe) (post questions to [hcp-users@humanconnectome.org](mailto:hcp-users@humanconnectome.org)) where HCP MEG experts regularly answer user questions.

### *1. How is the MEG coregistered to the anatomical MRI and volume conduction model?*

Coregistration is performed using an unmasked 1mm resolution T1-weighted anatomical image (which, due to anonymity requirements, is not part of the release). The geometric information that is needed for source reconstruction (i.e. MEG sensor positions and information derived from the anatomical MRI) is expressed in the head coordinate system, which is defined as being relative to the participant's head and based on a set of landmarks on the head, and is thus subject-specific. This coordinate system is expressed in meters, with the principal (X, Y, Z) axes going through external anatomical landmarks on the head (i.e. fiducials). The details are:

* + the origin is exactly between the left and right pre-auricular points (LPA and RPA)
	+ the X-axis goes towards the nasion (NAS)
	+ the Y-axis goes approximately towards LPA, orthogonal to X and in the plane spanned by the fiducials
	+ the Z-axis goes approximately towards the vertex, orthogonal to X and Y

The magnetometer locations in the raw and processed channel level data are represented in this coordinate system. The "anatomy" pipeline performs the coregistration of the MEG with the MRI data and results in in a volume conduction model and various source models (cortical sheet and 3-D grids), which are all expressed in this head coordinate system. The "anatomy" pipeline also produces the 4x4 homogenous transformation matrices to convert between individual head coordinates, MNI coordinates and voxel coordinates. These transformation matrices are represented in the 012345\_MEG\_anatomy\_transform.txt files.

### *2. What is the interpretation of the different homogeneous transformation matrices?*

The transformation matrices represented in the 012345\_MEG\_anatomy\_transform.txt files represent the transformation between different coordinate systems. Each matrix is named [from]2[to] where it denotes the transformation from coordinate system [from] into coordinate system [to]. The matrices that have ‘vox’ or ‘vox07mm’ in their name transform from or to anatomical MRI voxels. The matrices that contain ‘vox’ are of limited use to external users, because the release does not contain the original anatomical images that were used to create these transformation matrices. The matrices with ‘vox07mm’ refer to transformations that relate the voxels in the T1w\_acpc\_dc\_restore.nii.gz image (part of the structural preprocessing pipeline output) to the other coordinate systems used.. The transformation matrices that are of most relevance are the bti2spm and spm2bti, which convert between the MEG-system based coordinate system (bti) and a coordinate system based on the ACPC-based RAS (spm).

### *3. How are the MEG source models defined?*

The 3-dimensional grids that can be used for (beamformer) source reconstruction are based on 3-dimensional grids with a regular spacing of the dipoles, defined in normalized MNI space. The spacing between the dipoles (in normalized space) is represented in the filename (i.e. SUBJECTID\_MEG\_anatomy\_sourcemodel\_3d4mm means that the dipoles are 4mm apart). For each participant, the template grid has been warped to individual head space in order to express the dipoles' coordinates in the head coordinate system that is used for source reconstruction (see above). This warp is a non-linear one, and is based on the inverse of the nonlinear volumetric spatial normalization from individual head space to normalized MNI space. Consequently, the dipoles' coordinates are not placed on a regular 3-dimensional grid in individual head space. Yet, the source models allow for easy averaging across subjects, without the need for an intermediate interpolation step, because individual grid points coincide in normalized space.

The cortical sheet-based source models allow for distributed source reconstruction, e.g. weighted minimum norm estimates. These models have been constructed from the individual 32k-node per hemisphere surface-registered cortical sheets which are output files of the MR structural preprocessing pipeline, and have ~4k nodes per hemisphere.

### *4. How are different conditions and contrasts between conditions of tMEG scans analyzed?*

Contrasts are used in the tMEG pipelines so that all different conditions and comparisons of conditions at different stages of analysis may be processed with the same pipelines.

A contrast is a MATLAB structure representing the settings for performing a specific type for a specific condition or between 2 different conditions of a single experiment.

The settings for the analysis of a single condition or comparison between 2 conditions can vary in terms of the time periods, the baseline or comparison operation and other settings. So in order to add the flexibility for varying such parameters for a single condition or for the comparison of different conditions, more than one contrast is used for each single condition or for the comparison of different conditions. 

The table below defines and describes the fields of the Contrast structure for the eravg and tfavg pipelines:



| Field Name | Print Mnemonic prefix | Description | Example | Possible Values | Defaultvalue |
| --- | --- | --- | --- | --- | --- |
| **.pipeline** |   | name of pipeline where contrast is to be run | 'eravg' | 'eravg','tfavg' | [ ] |
| **.lockmode** | LM- | describes data group from which trials for contrast have been selected | {'TIM'} | different datagroups within each task, currently: For Motort:  'TEMG','TFLA'.For Workmem: 'TIM', 'TRESP'. For StoryM: 'TEV','TRESP','BSENT', 'BU'     | { [ ] } |
| **.mnemtrl** | (The trial set mnemonics are appended after the lockmode mnemonic) | a mnemonic describing the specific sets of trials (conditions) in the contrast | {'0B' , '2B'} (i.e. 0-Back, 2-Back) | trial set mnemonics for each of the different conditions used in the contrastsA table presenting all the currently considered contrasts is presented further below in this page. Check there for all the available contrasts. | { [ ] } |
| **.operation** | OP- | describes how metrics from the 2 different conditions will be compared –only meaningful where 2 conditions are compared within a contrast | 'diff','rel', or 'relch' | 'diff'  (Difference),'rel' (relative:ratio),'relch' (relative change:ratio-1) | [ ] |
| **.timeperiods** | Not part of naming | describes time points or periods for which analysis will be performedIf a one column vector (one column, many rows), analysis will be performed for each of these time points.If two columns exist, this is interpreted as time windows (each row a time window). | [-0.5 00 0.50.5 1] | no specific constraintThis is only constrained by the data time information | { [ ] } |
| **.timedef** | TD- | used when time periods are defined in windows (see above)It defines how the individual time points within each window will be processed during the analysis.For example, when computing the coherence between brain areas in time window [0 0.5], coherence can computed by estimating on spectral value for the entire window for each trial.Or the spectral coefficients can be computed for all time points within the window and they can all be used in the computation of coherence. | 'concat' | 'concat' (compute metric by all time points in windows concatanated for all trials)'avg' (take the avg of all times within the window before computing the metric)'sing' ('Pick a single value at the center of the window for each trial to perform analysis') | [ ] |
| **.baseline** | Not part of naming | contains the time window to be used as baseline in the contrast -- mostly used in single condition contrasts | { [0 0.5] } | no specific constraintThis is only constrained by the data time information | { [ ] } |
| **.baselinetype** | BT- | defines by what operation the baseline will be applied | 'diff' | 'diff'  (Difference)'rel' (relative:ratio)'relch' (relative change:ratio-1) | [ ] |
| **.selection** | Not part of naming | contains indices of the trials for the specific contrast conditions from the pool of all trials for the specific data group | {‘[1:20]' ,...  [21:40]'} | trial indices for each contrast are selected by the contrast function of each experiment | { [ ] } |
| **.description** | Not part of naming | contains a very short description of the contrast in a form that can be used for printing in a report --automatically produced by the contrast function of each experiment | 'memberTypes: Left\_Hand\n' |   | [ ] |
| **.mnemprint** |  | Print Mnemonic constructed from all the above fields and used for the naming of the produced flies by the pipeline | 'tfavg\_[LM-TFLA-LH]\_[BT-diff]' |   | [ ] |

All the available conditions and contrasts between conditions for each Task paradigm are extracted using a dedicated MATLAB function named as:

contrast\_$SCANMNEMONIC.m

where $SCANMNEMONIC can be "Wrkmem", 'Motort' or 'StoryM'.

These functions extract the list of all contrasts for all pipelines.

### *5. How was the E-Prime trigger sequence reproduced for the tMEG scans in which no parallel port triggers were recorded?*

In the Working Memory and Motor task scans, the signal in the TRIGGER channel consists of 2 superimposed bit patterns. One from the stimulus presentation computer that is running the E-Prime protocol, the other is from a photodiode placed in a corner on the stimulus presentation screen.

The E-Prime triggers encode all the events that are of interest within a scan. The photodiode triggers contain a subset of these events, corresponding mainly to the onset of images on the screen. For the Working Memory scans, the photodiode is on when a stimulus image is presented and is off otherwise. For the Motor Task scans, the photodiode is on when the Cue Screen (e.g. Left Hand) or the pacing flashing cross screen for each movement are presented, and the photodiode is off otherwise.

The photodiode triggers provide more accurate timing than the E-Prime triggers, because they measure the instance of the actual stimulus onset on the screen and do not represent the time at which the display command was sent by the software. However, the value of the photodiode trigger can take only two values: 255 for ON and 0 for OFF. In contrast, the E-Prime triggers values are diverse and encode multiple aspects of the experimental sequence, such as stimulus content and task demands.

As a consequence of the two superimposed triggers, the event code sequence is extracted based on the E-Prime triggers, but its timing is extracted from the corresponding photodiode triggers.

### ***6. How can I visualize MEG data in Connectome Workbench?***

Visualization of MEG data in Connectome Workbench works similar to the visualization of (f)MRI data. For a general introduction to Workbench, see the [Connectome Workbench website](http://humanconnectome.org/software/connectome-workbench.html) for more extensive information. The MEG results-based Cifti files generated by the HCP MEG pipelines require the 8k vertex cortical sheet descriptions for visualization. These are available as hemisphere-specific Gifti files present in the individual subjects' anatomy packages as 123456.L.midthickness.4k\_fs\_LR.gii and 123456.R.midthickness.4k\_fs\_LR.gii. The coordinate system in which these cortical sheets are defined is subject-specific ACPC-aligned headcoordinate space.

### ***7. How can I compute a contrast between two conditions, perform a baseline correction, or average across subjects?***

For the task data, there are several Cifti files per task. These represent the average response in specific task conditions. In order to appreciate the difference between experimental conditions it is often useful to compute a direct contrast between two conditions (e.g. a difference wave for an event-related field). Moreover, interpretability might be improved if a specific type of baseline correction is applied (e.g. Z-scoring the event-related field with the standard deviation of the activity prior to stimulus onset). Finally, averaging results across subjects will be needed for group analysis.

All of these operations can be performed using wb\_command, the command-line utility of workbench. See the Connectome Workbench website for more extensive information. Below, some examples are provided to perform some basic operations.

#### **Compute a contrast between two files**

Suppose you want to do a subtraction of the event-related fields estimated in two experimental conditions, stored in $FILE1 and $FILE2 respectively. This is achieved by:

wb\_command -cifti-math 'x-y' $OUTPUTFILE -var x $FILE1 -var y $FILE2

The prerequisite here is that $FILE1 and $FILE2 should have the same number of time points represented. Some experimental conditions contain just a single time point (e.g. the Fixation condition in the Working memory task). If such a condition (in $FILE2) is to be compared with a condition that contains multiple time points (in $FILE1), it can be achieved by:

wb\_command -cifti-math 'x-y' $OUTPUTFILE -var x $FILE1 -var y $FILE2 -select 1 1 -repeat

#### **Compute a contrast with an estimate based on a subset of time points within a single file (e.g. baseline correction)**

Suppose you want to do a normalization of the event-related field timecourse with the standard deviation of the activity in the pre-stimulus time window. This can be achieved in a three-step procedure, where 1) a selection is made of the time points that are included in the 'baseline' (for this you need to know the indices to the time points of interest), 2) an operation is performed on this selection (e.g. computation of the standard deviation), and 3) the output of the previous operation is applied to the whole time course of activity. These three steps are achieved by three calls to wb\_command:

wb\_command -cifti-merge $TEMPFILE -cifti $FILE -column $INDEX1 -up-to $INDEX2

wb\_command -cifti-reduce $TEMPFILE STDDEV $TEMPFILE

wb\_command -cifti-math 'x/y' $OUTPUTFILE -var x $FILE -var y $TEMPFILE -select 1 1 -repeat 

#### **Compute an average across a selection of conditions (or subjects)**

Suppose you want to average the response across a set of conditions, or across a set of subjects. This can be achieved by:

wb\_command -cifti-average $OUTPUTFILE -cifti $FILE1 -cifti $FILE2

Where the list can be extended to contain more than 2 input files.

### ***8. What is the definition of the frequency bands used in the different pipelines?***



|  |  |  |
| --- | --- | --- |
| **Frequency band** |   | **Frequency range (Hz)** |
| delta | 1.5-4 |
| theta | 4-8 |
| alpha | 8-15 |
| beta low | 15-26 |
| beta high | 26-35 |
| gamma low | 35-50 |
| gamma mid | 50-76 |
| gamma high | 76-120 |
| wide band | 1.5-150 |

Both the rMEG and tMEG pipelines deal with cortical oscillatory activity. Specifically, Band Limited Power (BLP) timecourses, BLP correlation and band-specific Multivariate Interaction Measure on the source-level signals are estimated from rMEG data, whereas the average across trials of the BLP timecourse is estimated from the tMEG data. In all the tMEG and rMEG pipelines, consistent frequency intervals are used to define the oscillatory bands. The frequency intervals defining each oscillatory band, together with the names used in all the pipelines are listed above. 

 

