## How To Access HCP-YA Subject Data via REST

For the [HCP 1200 Release](http://humanconnectome.org/study/hcp-young-adult/document/1200-subjects-data-release), unprocessed and processed data for a subject can be accessed via REST calls apart from using other modes such as Connectome In a Box, Aspera, Amazon AWS. 

In order to access data for a subject, you will need to register at [https://db.humanconnectome.org](https://db.humanconnectome.org.)

To get data via REST, in a script, you could use tools like curl. 

**Data organization**

Details about file and folder organization are available**[here](http://humanconnectome.org/storage/app/media/documentation/s1200/HCP_S1200_Release_Appendix_III.pdf).**

**USAGE**

To download a particular file, say the minimally processed file, **T1w\_acpc\_dc\_restore\_1.25.nii.gz**, for a subject, say 100307, you could invoke curl as:

```
curl -u DB_LOGIN_ID_HERE:DB_PASSWORD_HERE -O
https://db.humanconnectome.org/data/archive/projects/HCP_1200/subjects/100307/experiments/100307_CREST/resources/100307_CREST/files/T1w/T1w_acpc_dc_restore_1.25.nii.gz
```

 

The URI to get any file, for the subject 100307 in the HCP 1200 Release, would begin with:

```
https://db.humanconnectome.org/data/archive/projects/HCP_1200/subjects/100307/experiments/100307_CREST/resources/100307_CREST/files
```

 

add the path to the file after this prefix to get a file. For example, if you want the file MNINonLinear/Results/rfMRI\_REST1\_LR/rfMRI\_REST1\_LR\_Atlas.dtseries.nii, the URL would be:

```
https://db.humanconnectome.org/data/archive/projects/HCP_1200/subjects/100307/experiments/100307_CREST/resources/100307_CREST/files/MNINonLinear/Results/rfMRI_REST1_LR/rfMRI_REST1_LR_Atlas.dtseries.nii
```

 

### **Bash Script snippet for getting files for a batch of subjects**

```bash
DBHOST=https://db.humanconnectome.org
PROJECT=HCP_1200
REST_URL_PREFIX=$DBHOST/data/archive/projects/$PROJECT/subjects
##################################################################################################################
#
# GET a jsession
#
#
# Set 
#
# MY_CURL_OPTIONS: Options that you may want to pass to curl such as --connect-timeout, --retry etc
# db_user: ConnectomeDB login id
# db_password: ConnectomeDB password
#
#
# subject_list_file: A File containing list of subject IDs
#
##################################################################################################################

jsession=`curl $MY_CURL_OPTIONS -u $db_user:$db_password $DBHOST`

while read line
do
      subject=$line
      subject_url_prefix=$REST_URL_PREFIX/$subject/experiments/${subject}_CREST/resources/${subject}_CREST/files
      file_relative_path=MNINonLinear/Results/rfMRI_REST1_LR/rfMRI_REST1_LR_Atlas.dtseries.nii
      curl $MY_CURL_OPTIONS -b "JSESSIONID=$jsession" -O $subject_url_prefix/$file_relative_path 
done < $subject_list_file
```

 

 



### Attachments

- [jstree.min.js](./assets/jstree.min.js)
- [jstree.js](./assets/jstree.js)
