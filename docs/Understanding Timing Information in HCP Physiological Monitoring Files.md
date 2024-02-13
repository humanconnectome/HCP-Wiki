## Understanding Timing Information in HCP Physiological Monitoring Files

The goal of this document is to lay out our understanding of the timing information contained in HCP-YA physiological monitoring logs.

* Recording raw physiological log files
	+ Logging of physiological signals is automatically enabled within the CMRR multiband sequences utilized by HCP.
	+ The Siemens PMU saves out four files for each fMRI and dMRI scan.
		- .ext: log of external TTL trigger pulse
		- .puls: log of pulse oximetry
		- .resp: log of respiratory bellows
		- .ecg: log of electrocardiogram; this is not used, so it is discarded
	+ The CMRR multiband sequences utilized by HCP write these files with filenames that contain a Universal Unique Identifier (UUID) that matches the UUID written to the DICOM header for the matching scan. This ensures that the log files are consistently and accurately matched with the scan during which they were collected. Date and time stamps are also written to the filenames. However, these are removed from the filename before the files are made publicly available.
* Time stamp information contained in each file
	+ The "footer" at the end of each physio log file contains several "LogStart" and "LogStop" flags. The MDH version of these flags (i.e., LogStartMDHTime and LogStopMDHTime) reflect the millisecond time stamp (since midnight) according to the same clock that is written in the DICOM header. Therefore, this clock is preferable to use to synchronize the onset of each physio log file with the onset of the DICOM collection.
	+ There is roughly 500ms between the onset of each log file. The exact delay between the onset of each file can be determined using the LogStartMDHTime value.
	+ The DICOM header time stamp (0008,0032) has a different format, but corresponds to the LogStartMDHTime flag for the last PMU log file to begin recording.
* Relating timing of physiological monitoring information to fMRI volume timeseries
	+ The onset of the last file should occur at the same time as the onset of SBRef DICOM
	+ There is a window of time between the onset of the SBRef collection and the onset of the multiband fMRI timeseries. This window of time corresponds to the collection of preparatory scans used by the fMRI multiband sequence.
		- For the fMRI scans, this window is a total of 9360ms, which corresponds to the collection of one single-band reference (8 \* 720ms) plus five discarded MB volumes (5 \* 720ms).
	+ The .ext external TTL pulse has its first onset at the beginning of the multiband fMRI timeseries scan. The .puls file contains Siemens "Trig" flags that correspond to the onset of the SBRef (i.e., 13TRs before beginning of timeseries).
* Relating timing of physiological monitoring information to dMRI diffusion weighted images
	+ The onset of the last file should occur at the same time as the onset of SBRef DICOM
	+ There is a window of time between the onset of the SBRef collection and the onset of the diffusion weighted images. This window of time corresponds to the collection of preparatory scans used by the dMRI multiband sequences.
		- For the dMRI scans, this window is roughly 55.2 seconds, which corresponds to 5520ms \* 10 TRs: 1 dummy scan for SBRef  (3 TR) + 1 scan for SBRef (3 TR) + 4 dummy scans before MB images.
	+ The .ext external TTL pulse has its first onset at the beginning of the first diffusion weighted image. The .puls file contains Siemens "Trig" flags that correspond to the onset of the SBRef (i.e., 10 TRs earlier).
* Other Siemens flags
	+ '5002 ... 6002': These values mark the start (5002) and end (6002) of non-monitoring information written to the file. The information written between these two flags does not contain physiological monitoring information, and should be removed from the vector of voltage values reflecting the physio data.
	+ 'Trig': Flag written for each volume in fMRI and dMRI *sequence*. These are written for each volume in the preparatory scans at the beginning of the multiband sequence, as well as the volumes in the MB scan of interest.
	+ '5000': peak in voltage change has been detected in signal
	+ 'ACQ FINISHED'
	+ '5003':
* Other known issues  

	+ TTL pulses in .ext files do not align with onset of every volume in dMRI scans
		- An optical pulse is sent for every volume in the fMRI scan (i.e., once every 720 ms). However, the optical pulse is sent every 149.19 ms, once for each of the 37 multiband "shots" per dMRI volume (37 shots x MB3 = 111 slices per dMRI volume).
		- The optical pulse created by the Siemens scanner is only 0.05ms in duration. It needs to be converted to an electronic TTL pulse, and "stretched" to a longer duration to ensure that it will be detected by other hardware (e.g., E-Prime button box). Consequently, the duration of our TTL trigger pulse in the .ext files is 500ms in duration.
		- In the case of dMRI physio logging, this results in a new TTL pulse written to the .ext file for every fourth multiband shot. This doesn't divide evenly into 37 shots per volume, meaning that the new volume may onset at some point during the "stretched" TTL signal.
	+ The .resp file does not contain any 'TRIG' flags.
		- We take what is known about aligning the timing of the .ext and .puls files and apply it to the .resp file even though it cannot be verified there. In the .ext and .resp files, it can be verified by the alignment of the TRIG flags and .ext TTL pulses.

 

