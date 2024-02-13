## List of CIFTI-compliant tools

Here we keep a current list of software packages/tools that are [CIFTI](http://www.nitrc.org/projects/cifti/) file format compliant:

**[Connectome Workbench](http://www.humanconnectome.org/software/get-connectome-workbench)**

One platform containing **wb\_view** for surface and volume brain visualization and **wb\_command** command line tools (particularly for CIFTI manipulation)

**[FSL](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/)**

The FMRIB team has released FSL version 5.0.10, which includes beta versions of melodic, film, and flameo that are CIFTI-compliant. Additional CIFTI-compliant tools are planned for upcoming release of the FSL 6.0 major update.

**[PALM](http://fsl.fmrib.ox.ac.uk/fsl/fslwiki/PALM)**

PALM — Permutation Analysis of Linear Models — is a tool that allows inference using permutation methods. It runs in matlab, octave, or from the command-line, and is capable of some processing on CIFTI files.

**[FieldTrip](http://www.fieldtriptoolbox.org/)**

specific commands: ft\_sourceparcellate, ft\_sourceplot, ft\_volumewrite, ft\_read\_cifti, ft\_write\_cifti

FieldTrip allows MEG/EEG source reconstruction on source models that represent the full brain as a volumetric grid, and/or on the cortical sheet as a triangulated surface. After estimating the activity on the dense (volumetric or surface) source model, FieldTrip allows for averaging of the activity within parcels. Alternatively, FieldTrip allows for specifying the parcels prior to source estimation. The parcellated representation of MEG/EEG source activity is represented in a format similar to channel-level data, i.e. each parcel is represented as channel in the MATLAB data structure. This allows all channel-level analysis tools to be applied on the parcellated source reconstruction.

[**AFNI****/SUMA**](https://afni.nimh.nih.gov/)

specific commands: suma, cifti\_tool

SUMA supports displaying cifti data.



     


**[Reading HCP data into MATLAB](./HCP%20Users%20FAQ.md)**
see FAQ #2

**[cifti-matlab](https://github.com/Washington-University/cifti-matlab) v2**

specific commands: cifti\_read, cifti\_write (plus drop-in compatibility for ciftiopen, ciftisave, ciftisavereset)

Version 2 of the cifti-matlab toolbox was mostly rewritten, with a new design that more closely represents the internals of the file format, exposing nearly all of the information in the XML, and providing some helper functions to simplify some common operations.  This is the recommended option for MRI-derived data, as it provides drop-in compatibility with ciftiopen and related functions, and should be faster, with less disk IO.  


**[Workbench v1.0 (or greater) + GIFTI toolbox code](./HCP%20Users%20FAQ.md)**
see FAQ #2

specific commands: ciftiopen, ciftisave, ciftisavereset

These functions allow the use of CIFTI files in MATLAB by using wb\_command to convert to pseudo-GIFTI format and the GIFTI toolbox matlab library to read them. ciftiopen does not parse the XML within the file, meaning that additional external commands are necessary to determine what the CIFTI indices represent (which vertex or voxel, etc).

**[cifti-matlab v1](https://github.com/Washington-University/cifti-matlab/releases/tag/v1-final) (previous version)**

specific commands: ft\_read\_cifti, ft\_write\_cifti

The cifti-matlab toolbox contains a subset of functions from the FieldTrip toolbox to facilitate the use of CIFTI files and MATLAB without having to install the entire FieldTrip toolbox. The FieldTrip-based cifti-matlab toolbox does some translation of the CIFTI file to match what FieldTrip can take as input, resulting in some changes to the indices of the data matrix.

  


  


  


