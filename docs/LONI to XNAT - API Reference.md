## LONI to XNAT - API Reference

Overview and examples of the XNAT REST API to aid in getting MR session data from LONI sites. 

The {SERVER-URL} for production will be <https://intradb.humanconnectome.org>, and an example of {SERVER-URL} for testing purposes will likely be <https://hcpi-demo.humanconnectome.org.> You will need to have an account on the site you are pushing data to and will also require project owner access. Please contact Michael Hileman (mhileman@wustl.edu) for any help regarding site setup and access.

### DICOM send example

You can use the REST interface to push a zip archive of DICOMs, e.g., 

```
curl -u user:pass https://{SERVER-URL}/REST/services/import?inbody=true&import-handler=DICOM-zip&dest=/prearchive/projects/CCF_TEST -X POST --data-binary @dicoms.zip
```

See [https://wiki.xnat.org/pages/viewpage.action?pageId=6226268](../pages/6226268.md) for complete documentation on this.

 

You can also use the DicomRemap tool found in the Dicom Browser suite of tools (<http://nrg.wustl.edu/software/dicom-browser/instructions/batch-anonymizations/>). Even without remapping or anonymizing anything, you can make a call to the DicomRemap program and push a directory of DICOMs to a DICOM receiver, e.g.,

```
DicomRemap -o SERVER-URL /path/to/dicom
```

Either of the above methods will create a subject and experiment from the DICOM headers during the XNAT archive process.


### Setting XNAT Parameters via REST

Sessions will be built and parameters set from the DICOM headers in the above examples. However, it is likely that you will need to change some things that either weren't in the DICOM headers or not where XNAT expected them to be. To make any of these REST calls below, the subject or experiment that you are setting paramaters for must exist. For testing purposes, you can create these through the top menu in XNAT for any project that you have appropriate access for.

##### Subject Level Param

Setting gender and age:

```
curl -u user:pass https://{SERVER-URL}/REST/projects/CCF_TEST/subjects/sub1?xsiType=xnat:subjectData&gender=female -X PUT
curl -u user:pass https://{SERVER-URL}/REST/projects/CCF_TEST/subjects/sub1?xsiType=xnat:subjectData&age=25 -X PUT
```

 

##### Experiment Level Param

Setting the scanner name:

```
curl -u user:pass https://{SERVER-URL}/REST/projects/CCF_TEST/subjects/sub1/experiments/session1?xsiType=xnat:mrSessionData&scanner=SIEMENS -X PUT
```

 

##### Scan Level Param

Setting scan type and series description:

```
curl -u user:pass https://{SERVER-URL}/REST/projects/CCF_TEST/subjects/sub1/experiments/session1/scans/1?xsiType=xnat:mrScanData&xnat:mrScanData/type=T1w -X PUT
curl -u user:pass https://{SERVER-URL}/REST/projects/CCF_TEST/subjects/sub1/experiments/session1/scans/1?xsiType=xnat:mrScanData&xnat:mrScanData/series_description=Structural -X PUT
```

