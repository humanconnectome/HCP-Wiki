## DIY fix for zeroes near medial wall in rfMRI dtseries data

A DIY fix of rfMRI time series data with empty vertices (timeseries = 0s) very near the medial wall is available using the command "-cifti-dilate" in **wb\_command**. wb\_command is a suite of command line utilities distributed as part of **Connectome Workbench**, our HCP visualization and analysis platform. The current distribution of Connectome Workbench is available for download at: <http://humanconnectome.org/connectome/get-connectome-workbench.html> .

Once you have Workbench installed, to get help/syntax for running this command, open a terminal window and type: 

wb\_command -cifti-dilate 

 

Use the following settings to fully cover the missing vertices around the medial wall: 

 <direction> : COLUMN  


<surface-distance> : 4  


<volume-distance> : 4  


 

Assuming you are in the directory with the affected .dtseries.nii file in it,  run the command using the syntax:     


wb\_command -cifti-dilate <cifti-in> <direction> <surface-distance> <volume-distance> <cifti-out> -nearest

Example: 

wb\_command -cifti-dilate rfMRI\_REST2\_LR\_Atlas.dtseries.nii COLUMN 4 4 rfMRI\_REST2\_LR\_Atlas\_FIXED.dtseries.nii -nearest

 

 

