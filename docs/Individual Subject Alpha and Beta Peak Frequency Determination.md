## Individual Subject Alpha and Beta Peak Frequency Determination

### Overview

Alpha and beta frequency bands represent two of the strongest oscillations in the human brain. Alpha oscillations are believed to have an inhibitory role and to originate from the thalamus. Beta oscillations are mostly dominant in the sensorimotor cortex and are associated with a "status quo" signalling mechanism.

A single alpha and a single beta frequency value is extracted using the following pipelines for each subject.

This process involves 2 main steps, which are also translated into 2 different pipeline scripts.

In the first step,  the sensor array is divided in 4 quadrants. For each of the Tasks, the results of the [tfavg pipeline](../pages/13860931.md) (time-frequency spectra) are averaged within each sensor group and across time (more details below). The same happens for the results of the [powavg pipeline](../pages/33128590.md) for Resting state scans, which contain only spectral information (non time resolved).

In the second step,  these average spectra are loaded in a Graphical User Interface where spectral peaks in the alpha and beta band are at first automatically estimated, but most importantly can be manually set and then saved. This process gives the ability to the user to get an overview of the spectra in all different tasks and resting state so that the choice of alpha and beta is more informed. 

The first step is represented by pipeline hcp\_avgspecextract.m.

The second step is represented by pipeline hcp\_avgspecmanualalphabeta.m ( and uses the GUI function hcp\_avgspecmanualalphabetagui.m).

  


  


  


### Step 1 - Pipeline "hcp\_avgspecextract.m"

#### Details

The sensor array has been divided into 4 quadrants

 ![sensorsDivided1](https://github.com/jese11/HCP-wiki-public/assets/7256156/f5f04b8f-dcbb-49df-8d13-77559176b3c4)

Spectra are averaged for each group of sensors. In the resting state case the spectra that are already computed by the hcp\_powavg.m pipeline for EACH resting state session are averaged within sensor group. These averaged speactra from each of the 3 different resting state sessions are stored in the same matrix. So in this case there are 4 different sensor groups and 3 different resting state sessions.

For the Motor task things are more diverse. 2 different trial lock conditions , 4 different trial types and 3 different spectrum types are used. Namely, the 2 different trial lock conditions are TEMG (trials locked on EMG onset) and TFLA (trials locked on onset of Flashing Cross). The 4 different trial types are Left Hand, Right Hand, Left Foot, Right Foot. The 3 different spectrum types are RAW BASELINE, RAW POST STIM and  RELATIVE (poststim to baseline), The latter is especially usefull for determining the beta band with the event related desyncronization relative to the baseline.

For the Working Memory there are also  2 different trial lock conditions , 2 different trial types and 3 different spectrum types . Namely, the 2 different trial lock conditions are TIM (trials locked on Image onset) and TRESP (trials locked on subjetc's Response). The 2 different trial types are 0-Back and 2-Back. The 3 different spectrum types are RAW BASELINE, RAW POST STIM and  RELATIVE (poststim to baseline), 

For the Story Math task there are 2 data groups TEV and TRESP. From the TEV data group, 2 conditions are used, the onset of math senstences and the onset of story sentences. From the TRESP group all cases where the subejct responded are selected.

For all the above cases and for each of the sensor group the average spectrum is saved.

#### Input

 



| File naming patten | File name example | Description |
| --- | --- | --- |
| subjlistfile |  codedSubjList\_20140915.txt | The input variable "subjlistfile" should contain the name of an ASCII file, which has 5 columns. Each row corresponds to a single subject, The first column contains the subject ID. The rest of the columns are binary flags signifying if the subject has Resting state, Motor, Working Memory and Story Math scans. |
| $EXPERIMENTID\_$SCANID\_tfavg\_$CONTRASTID\_[MODE-$AVGMODE].mat  | 012345\_MEG\_Motort\_tfavg\_[LM-TFLA-LH]\_[MODE-mag].mat | This matlab *.mat contains a structure (typical Fieldtrip structure for TFR average) containing the trials average for the given contrast. In the last part of the naming convention the [MODE-$AVGMODE] part signifies if the TFR average is performed on the magnetic field ('mag') or in the planar gradient magnitude ('planar'). |
|  <ExpID>\_<ScanID>\_powavg.mat |  133019\_MEG\_3-Restin\_powavg.mat | MATLAB file with averaged power spectrum |

  


 

#### Output

  




| File naming patten | File name example | Description |
| --- | --- | --- |
| casespectra\_<ScanID>\_Motort.mat  casespectra\_<ScanID>\_Restin.mat  casespectra\_<ScanID>\_StoryM.mat  casespectra\_<ScanID>\_Wrkmem.mat  | casespectra\_177746\_Motort.mat  casespectra\_177746\_Restin.mat  casespectra\_177746\_StoryM.mat  casespectra\_177746\_Wrkmem.mat | This matlab\*.mat contains 3 variables.   casespectra: This matrix has 69 columns. The first 4 correspond to variables that define dataset, set of trials, sensor location and type of spectrum. The other 65 column contain the actual spectral power for 65 frequencies namely [1:30 31:2:99] Hz.   allfreqs: [1x65 double] contains the frequencies   columnDescr: cell variable describing the columns of variable "casespectra" above. It is important because each task has different condition parameters.   In the last part of the naming convention the [MODE-$AVGMODE] part signifies if the TFR average is performed on the magnetic field ('mag') or in the planar gradient magnitude ('planar'). |

  


  


### Step 2 - Pipeline "hcp\_avgspecmanualalphabeta.m"

#### Details

After the casespectra files have been created , they can be used in the Graphical Interface pipeline hcp\_avgspecmanualalphabeta.m  where the spectra across all tasks can be assessed for a given subject.

![Gui1](https://github.com/jese11/HCP-wiki-public/assets/7256156/13d6a023-488e-4100-991d-59f76c67b999)

 

In the GUI the first 2 columns of plots correspond to MOTOR task, the next 2 correspond to the WORKING MEMORY task, the next 2 to the STORY MATH task and the last column to the RESTING STATE.

**MOTOR TASK: Plot column 1 and 2:** 

Upper row: Posterior sensors

Lower Row: Anterior sensors

Column 1: Raw spectrum from Post-stim period

Column 2: spectrum from Post-stim period relateive to baseline period  


**WORKING MEMORY TASK: Plot column 3 and 4:** 

Upper row: Posterior sensors

Lower Row: Anterior sensors

Column 3: Raw spectrum from Post-stim period

Column 4: spectrum from Post-stim period relateive to baseline period  


**STORY MATH TASK: Plot column 5 and 6:** 

Upper row: Posterior sensors

Lower Row: Anterior sensors

Column 5: Raw spectrum from Post-stim period

Column 6: spectrum from Post-stim period relateive to baseline period  


**RESTING STATE: Plot column 7:** 

Upper row: Posterior sensors

Lower Row: Anterior sensors

Column 7: Raw spectrum from Post-stim period

  


  


In columns 1,3,5,7  the peaks are determining by looking for local maxima in the range of alpha and beta frequencies.

In columns 2,4,6  the peaks are determining by looking for local minima in the range of alpha and beta frequencies.

After finding an alpha and a beta peak for each of the 7 cases represented in the seven GUI columns the overall alpha and beta peaks are determined by taking the median of all the alpha peaks and all the beta peaks respectively.  


The alpha and beta peaks for each case can be manually set in the corresponding boxes and the pressing the "update" button.

Also they can also be taken directly from the plot by clicking somehere on the spectrum and clicking the "A get" or "B get" buttons. 

The overall alpha and beta peaks can be also manually set in the boxes "final A:" and "final B".

The alpha and beta peaks are saved and the GUI closes after the "EXIT" button is pressed.  


  


  


  


#### Input

  




| File naming patten | File name example | Description |
| --- | --- | --- |
| subjlistfile |  codedSubjList\_20140915.txt | The input variable "subjlistfile"shoudlcontain the name of an ASCII file, which has 5 columns. Each row corresponds to a single subject, The first column contains the subject ID. The rest of the columns are binary flags signifying if the subject has Resting state, Motor, Working Memory and Story Math scans. |
| casespectra\_<ScanID>\_Motort.mat  casespectra\_<ScanID>\_Restin.mat  casespectra\_<ScanID>\_StoryM.mat  casespectra\_<ScanID>\_Wrkmem.mat  | casespectra\_177746\_Motort.mat  casespectra\_177746\_Restin.mat  casespectra\_177746\_StoryM.mat  casespectra\_177746\_Wrkmem.mat | These are the mat files created in Step 1 by pipeline hcp\_avgspecextract.m  This matlab*.mat contains 3 variables.  casespectra: This matrix has 69 columns. The first 4 correspond to variables that define dataset, set of trials, sensor location and type of spectrum.   The other 65 column contain the actual spectral power for 65 frequencies namely [1:30 31:2:99] Hz.  allfreqs: [1x65 double] contains the frequenciescolumnDescr: cell variable describing the columns of variable "casespectra" above. It is important because each task has different condition parameters.   |

  


#### Output

  




| File naming patten | File name example | Description |
| --- | --- | --- |
| <subjID>\_ABpeakfile.mat | 123456\_ABpeakfile.mat | This mat file contains the variables:'alphapeak','betapeak':  |

