## How to Access Data on ConnectomeDB

### How to Register an Account and Agree to the HCP Open Access Data Use Terms

The first time you visit [**https://db.humanconnectome.org**,](https://db.humanconnectome.org,) you will need to register a new account. You can do this from the login / registration page

**Activating your account**

After you create your ConnectomeDB account, a confirmation email will be automatically sent to the email address that you specified for your account. You must click the confirmation link in that email in order to activate your account. If you did not receive that email, or you need to reactivate your account, you can request a new activation email by clicking the "Resend Verification Email" link on the login page.

Once your account is activated, you will be able to log in and see the list of studies and datasets in ConnectomeDB.

**Data access and data use terms**

Each study in ConnectomeDB can provide a set of data use terms which must be reviewed and accepted before a user can get access to that study's data. You can quickly review and accept these data use terms by clicking the "Data Use Terms Required" button related to the study you are interested in.

Once the terms are accepted, buttons and selectors will appear in that study overview box that will allow you to explore and download HCP data by selecting options for groups of subjects.

> [!note] 
> Your login to ConnectomeDB times out every 30 minutes. Click the “renew” link in the top navigation bar to reset the timer as needed.
  

  


  


  


### How to Explore HCP Data in ConnectomeDB

Once your ConnectomeDB account is set up and you have signed the HCP data use agreement, the header for the 1200 Subjects release will appear blue and on the right an “**Open Dataset**” button and two pulldowns for “**Explore Subjects**” and “**Download Image Data**” will be active.

* “**Open Dataset**” takes you to the HCP 1200 Subjects project page, which has links to documentation processing pipeline software, group average data, stimulus resources for tfMRI, the Netmats Megatrawl dataset and Connectome Workbench datasets.
* “**Explore Subjects**” takes you to the ConnectomeDB Subject Dashboard for viewing behavioral and individual difference measures for groups of subjects or exploring the scan level data for  individual subjects. You may choose to browse all subjects or groups of subjects, including all 7T, Retest, or MEG subjects.
* “**Download Image Data**” takes you straight to the Download Packages page to queue downloads for the group of subjects that you select.

#### Creating Custom Groups of Subjects Defined by Search Criteria

1. **Click on “Explore Subjects”** and select “Subjects with 7T MR Session Data” from the list. The Subject Dashboard will load the 184 subjects for which 7T data are available. In the Subject Information section, all 7T subjects are listed by ID with a scroll bar at the right.
2. The “Add Tab” pulldown at the far right allows selection of categories of individual/behavioral data for viewing. **Click on “Study Completion”** in the pulldown to open a tab that lists which scan and behavioral data in the HCP protocol were collected for each subject. Use the scroll bar at the bottom to find completeness measures for 7T, starting with 7T\_Full\_MR\_Compl.
3. To search or filter the 184 7T subjects for those with certain modalities of 7T data available, use the Data Filters. **Click the “Add a New Filter” button**.
4. **Select:**   

	1. Category “Study Completion”,
	2. Assessment “Study Completion: 7T MR”,
	3. Attribute “Full Protocol Complete”,
	4. Operator “=”,
	5. Value “True”.
5. **Click “Apply”**. The list below will now show only the 175 7T Subjects that have data released for all 7T modalities (4 rfMRI runs, retinotopy, movie watching, and diffusion).
6. **Click the “Save Group” button** at the top and set a Group Name (e.g. 7T Complete) so that you can return to this set of filters in future ConnectomeDB sessions.

If you click the “Download Images” or “Download CSV” buttons, only the subjects for which you filtered will be part of the data queued for download (see below).

You can also explore all the scan details and behavioral/individual difference data for any subject individually by clicking a Subject ID link from the list.

#### Accessing Group Average Data and Other Resources

Now click the “Dataset Resources” button at the top right. This takes you to the WU-Minn HCP Dataset page (also accessible through the “Open Dataset” button on the Public Connectome Data splash page that you see when you first log in).

Here you see:

* Overview description of the 1200 Subjects dataset
* Buttons to Browse all Subjects, Open a set Group of Subjects in the dashboard (including any a user saves themselves), or Download Image data for the same set groups of subjects.
* Links to Data Reference documents, online FAQs and individual difference/behavioral Data Dictionary.
* Downloads of individual difference/behavioral data and expanded FreeSurfer anatomical measures
* Links to HCP data processing software for MEG and MRI
* Link to Order the complete dataset via “Connectome in a Box”
* Downloads of 3T, 7T, and MEG tfMRI protocol E-Prime scripts
* Links to Group Average rfMRI and tfMRI datasets
* Link to the Netmats MegaTrawl analysis of correlations between imaging and non-imaging measures in the HCP data
* Datasets designed for viewing in Connectome Workbench

#### Toggling Views of Restricted Access Data

If you have Restricted data access, you will see at the top left of the page is a pulldown to the right of “Current Project” that allows you to choose the level of data you want to view: Open Access, Restricted (contains fields that are potentially identifying), or Sensitive (contains fields potentially harmful or embarrassing to subjects). This pulldown persists throughout ConnectomeDB and, therefore, can be set from the Dashboard where data fields are viewed as well. More information on Access Levels is available at <http://humanconnectome.org/study/hcp-young-adult/data-use-terms>.

The default setting is Open Access. Restricted data view contains restricted data (Dashboard column headers in red) and all open access data. Sensitive data view contains sensitive data (Dashboard column headers in black) and restricted and open access data. When you select Restricted or Sensitive the area around the Current Project box is colored red to remind you that you are set to view restricted data.

The HCP built this access level setting into the user interface to allow investigators to control what kinds of data appear for different use case scenarios. For example, one can show only Open Access data when giving a lecture to a class, but view Sensitive data when filtering subjects by positive drug test results for a research study on drug use.

  


  


### How to Download Data

> [!note] 
> All downloads on ConnectomeDB require the Aspera browser plugin. If this plugin is not installed, ConnectomeDB will provide a link to install the latest version. There is no cost for using the Aspera browser plugin.Installing the Aspera plugin to your browser requires you to restart your browser. Therefore, we recommend installing the plugin before you explore/select HCP data in ConnectomeDB.
In order to facilitate access to the very large data files generated on every subject, we have prepackaged data into convenient group data packages. Datasets can be downloaded from ConnectomeDB in set packages or users may order all the image data to be sent to them on hard drives.

#### Installing the Aspera Browser Plugin

Due to the large file sizes of the data, the HCP uses an Aspera server to dramatically boost data transfer speeds. Therefore, downloading data from the HCP requires you to have the Aspera plugin installed on your browser.

If you have not installed the plugin yet, a warning message will appear at the top of the browser window reminding you that you must Install the Aspera plugin before using any of ConnectomeDB's services, including downloading.

An Aspera install help guide is available here: [How To Install the Aspera Browser Plugin](How%20To%20Install%20the%20Aspera%20Browser%20Plugin.md) 

> [!note] 
> One common problem with installing Aspera on the Mac platform for non-US users is that you must add US English to the Languages list (using the checkbox) to your System Preferences>Personal>Language & Text settings.

#### First-time Aspera Download Setup

If this is your first time downloading data from ConnectomeDB, before you start selecting packages to download, we highly recommend setting up the preferences in your Aspera Connect plugin to download to the appropriate place on your local or network hard drive. See [First time Aspera Setup Instructions](First%20time%20Aspera%20Setup%20Instructions.md)

#### Selecting Data Packages To Download

Upon login to ConnectomeDB, you are brought to the Public Connectome Data splash page. If you choose one of the “Download Image Data” options (e.g. 7T Subjects) in the pulldown at the top right of the WU-Minn HCP Data-1200 Subjects section, you will launch the Download Packages page.

Using the menus in the left column, select the following attributes of the data you want to download.

1. Choose the Session Type:   

	1. 3T MRI
	2. 7T MRI, or
	3. MEG
2. Choose the Processing Level:
	1. unprocessed,
	2. preprocessed (includes channel-level processed MEG),
	3. Analysis (tfMRI and bedpostX diffusion only), or
	4. Source-level processed (MEG only)


To make selections for download, click the “**add to queue**” icon to the left of each dataset package. 

The total size of the data you have queued for download is at the upper and bottom right. Use this calculation to check against your available hard drive space. 

When you are done making your selections, click the Download Packages button at the upper or lower right. A popup will remind you again what packages you selected and the total size of the files. Clicking “Download Now” will automatically open Aspera Connect and launch the download. 

> [!note] 
> If you have not setup Aspera Connect, as described above, by default the data will start downloading to your Desktop (!!).You can stop any download by clicking the “X” button to the right of the download progress bar.
If the download does not start automatically, use the link on the Download Package Launcher page in your browser to restart. Once started, the blue bar in the Aspera Connect: Transfers window will show your download progress (per subject file, not overall progress). 

Of course, the more subjects and packages you selected for download, the longer your download will take (remember, this is big data!). This is why we offer the “Connectome in a Box” and Amazon S3 options for those who want data on many subjects. 

#### Troubleshooting Aspera Downloads

If you have trouble with getting Aspera downloads to work on your network, please consult these troubleshooting steps: [Aspera Plugin Help and FAQ](Aspera%20Plugin%20Help%20and%20FAQ.md)

  


  


### Handling Downloaded HCP Data

Now that you have downloaded the data you want, here’s some tips for handling the data:

* Each download package consists of a .zip archive, and an md5 checksum. After you download the data you want, you can use the md5 file to verify the integrity of your downloaded file.
* To unzip the downloaded .zip archives, for Windows users we recommend using a utility such as 7-zip (available free) so that the directory structure of the unzipped files remains intact. The built-in unzip capabilities of Linux and MacOSX can be used, as they do not affect the directory structure of the unzipped files.
* Once the archives are downloaded and unzipped, many of the component files are gzipped (.gz files). You will need to unzip all.gz files in order to use them. For this, you need an application that is compatible with gzip. For Windows users, we again recommend 7-zip. Linux has support for gzip built in, and Mac users can use the Mac Gzip utility.
* Downloaded HCP data unzips to a set directory structure that is detailed below in Directory structure for unprocessed MR data, Directory structure for preprocessed MR data, and in **[Appendix 3: File Names and Directory Structure for 1200 Subjects Data](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_III.pdf)**. The directory structure for downloaded HCP data is identical to what is provided in Connectome in a Box.
* If you have downloaded a large amount of HCP data, we recommend sharing the data locally at your research institution. This will save download and organization time for your colleagues and relieve some of the burden on the ConnectomeDB download bandwidth available to other HCP users.

> [!tip] 
> If you distribute HCP data in any way, all users (those who access HCP data) must register at ConnectomeDB and sign the Open Access Data Use Terms in order to comply with regulations on human subjects research.
  


  


