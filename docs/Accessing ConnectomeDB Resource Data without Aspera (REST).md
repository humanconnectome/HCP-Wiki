## Accessing ConnectomeDB Resource Data without Aspera (REST)

With the increasing frequency and duration of outages of the ConnectomeDB Aspera server as both the server and licensed software ages, it is sometimes necessary to get resource page data via REST.  It's a fairly straightforward process to convert Resource page Aspera URLs to REST URLs that can be used for downloading resource data.  
Here are the steps:



Right click on resource link to copy the URL into a clipboard:
![image2022-5-27_11-26-2](https://github.com/jese11/HCP-wiki-public/assets/7256156/ba9caf73-4d5d-42d5-9bb7-6c4301edc396)



Paste the resulting link in your usual text editor and edit:

Copied link:

https://db.humanconnectome.org/app/action/ChooseDownloadResources?project=HCP_Resources&resource=Scripts&filePath=HCP_TFMRI_scripts.zip 

Replace BOLD sections:

https://db.humanconnectome.org/ **app/action/ChooseDownloadResources?project=** HCP_Resources **&resource=** Scripts **&filePath=** HCP_TFMRI_scripts.zip 

With:

https://db.humanconnectome.org/ **data/projects/** HCP_Resources **/resources/** Scripts **/files/** HCP_TFMRI_scripts.zip

Becomes:

https://db.humanconnectome.org/data/projects/HCP_Resources/resources/Scripts/files/HCP_TFMRI_scripts.zip




Copy and paste new URL from your editor into your browser OR use curl:

![image2022-5-27_11-41-7](https://github.com/jese11/HCP-wiki-public/assets/7256156/b3848ebe-2077-44a6-862b-38021f07ae73)


OR

    curl -u [USERNAME]:[PASSWORD] -O https://db.humanconnectome.org/data/projects/HCP_Resources/resources/Scripts/files/HCP_TFMRI_scripts.zip


