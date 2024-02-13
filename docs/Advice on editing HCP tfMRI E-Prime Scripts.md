## Advice on editing HCP tfMRI E-Prime Scripts

HCP provides a [link for downloading the E-Prime scripts](https://db.humanconnectome.org/app/action/ChooseDownloadResources?project=HCP_Resources&resource=Scripts&filePath=HCP_TFMRI_scripts.zip) that we use for the 7 tfMRI tasks in the HCP protocol on the [HCP project page](https://db.humanconnectome.org/data/projects/HCP_1200) in ConnectomeDB.The HCP E-Prime scripts were created with E-Prime 2.0 Professional (2.0.10.242).

If you would like to modify these scripts for your own use, here are some guidelines for changing the key assignments or input device:

 

============================================================

### Modifying scripts for single monitor system:

Due to the nature of the E-Prime computer setup for the HCP, the scanner LCD projector is the secondary monitor in E-Prime and the experimenter display in the control room is the primary monitor in E-Prime. Consequently, in order to modify the E-Prime script to display to a single monitor, you will need to:  
A) delete experimenter feedback events (which display to the primary monitor - display index = 1),  
B) change subject display events from the secondary monitor (display index = 2) to the primary monitor (display index = 1),  
C) delete the primary monitor display (called "Laptop") from E-Prime "Experiment Object Properties" window  
D) change the remaining monitor display (called "LCD" or "ScannerD2") from display index of "2" to index of "1".  
  
### Be aware that many HCP E-Prime scripts contain inline code that addresses objects linked to both display devices. It is therefore critical that you check the timing and functionality of the script after modifying events or displays within the E-Prime code.  
============================================================

### Changing input devices and key assignments:

**To continue to use the SRBOX as an input device, but change key assignments**

***See ##NOTE## Below***

Change corresponding values in the "InitializeParameters" inline code:

--triggercode = "7"

-- Allowed = "xy"    

--Target = "x"           

--Nontarget = "y"

-regenerate script and save, and try to run to make sure settings took effect.

 

**To Remove the SRBOX as an input device but retain current input configuration**

(This will require you to press "7" on the keyboard, or whatever you change the triggercode to, to begin the script)

-Doubleclick on the "experiment" icon in the structure window in E-studio

-Click the "Devices" tab -either uncheck, or remove "SRBOX" entirely, as an input devices from this list.

-regenerate script and save, and try to run to make sure settings took effect.

 

**To Both Remove SRBOX AND change key configuration**

(This will require you to press "7" on the keyboard, or whatever you change the triggercode to, to begin the script)

#### ***See ##NOTE## Below***

-Doubleclick on the "experiment" icon in the structure window in E-studio

-Click the "Devices" tab -either uncheck, or remove "SRBOX" entirely, as an input devices from this list.

-Change corresponding values in the "InitializeParameters" inline code --triggercode = "7"

-- Allowed = "xy"    

--Target = "x"           

--Nontarget = "y"

-regenerate script and save, and try to run to make sure settings took effect.

 

#### **##NOTE##**

Additionally, if you change the input key configuration (only, or in addition to removing the SRBOX), one line of inline code within the "ExperimenterWindowInline" script must be edited to allow for this.

On the line that has:

----

'TotalRespGreater200-keep counter

Select Case PrevResponse

                Case "2", "3"'a valid response

----

The "2" and "3" on the third line above need to be changed to reflect whatever the 2 valid keys are for the user's new input configuration.

For example, if your new response buttons are "y" and "b", change "2" and "3" to those new values, respectively.

  
