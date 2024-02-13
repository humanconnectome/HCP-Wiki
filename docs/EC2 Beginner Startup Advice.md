## EC2 Beginner Startup Advice

If you are interested in developing tools or analyzing S3-stored HCP data in the cloud, you will want to set up an **EC2 (Amazon Elastic Compute Cloud) instance**. We recommend reading about EC2 details, instances, pricing, etc. at these links:

<http://aws.amazon.com/ec2/details/>

<http://aws.amazon.com/ec2/instance-types/>

NITRC Enhanced Services also provides the NITRC-Computational Environment (CE), a cloud based computational virtual machine pre-installed with popular neuroimaging tools, distributed via NeuroDebian. Click here for a listing of current NITRC-CE packages: <http://www.nitrc.org/ce-packages> . NITRC-CE is available to use on your own infrastructure or via commercial cloud providers including Amazon and Microsoft. 

 

Since the HCP data is hosted on S3 in an uncompressed format, participants can download data in parallel using tools like [s3cmd-modification](https://github.com/pcorliss/s3cmd-modification).

You can use tools like [s3cmd](https://github.com/pcorliss/s3cmd-modification) to list the contents of a directory on S3, get individual files or sync full directories. You will also be able to download directly to your personal/work computer or to a machine on the EC2 Cloud like the [NITRC Computational Environment](https://aws.amazon.com/marketplace/pp/B00AW0MBLO).

 

To access the data you might want to install [s3cmd-modification](https://github.com/pcorliss/s3cmd-modification), which will enable you to explore the [HCP Data Directory](http://humanconnectome.org/documentation/S1200/HCP_S1200_Release_Appendix_III.pdf) on Amazon and will allow rapid parallel downloading ([s3cmd-modification install instructions](https://github.com/pcorliss/s3cmd-modification/blob/master/INSTALL)).

After you install s3cmd, you need to configure it with your AWS public and secret keys that you set up with the instructions on [How To Connect to Connectome Data via AWS](./How%20To%20Connect%20to%20Connectome%20Data%20via%20AWS.md).


```
:~ s3cmd --configure
Enter new values or accept defaults in brackets with Enter.
Refer to user manual for detailed description of all options.

Access key and Secret key are your identifiers for Amazon S3
Access Key []: <your-access-key>
Secret Key []: <your-secret-key>
... 

```
Take s3cmd out for a test drive…

List subject directories:


```
:~ s3cmd ls s3://hcp.aws.amazon.com/`hcp`/

DIR   s3://hcp.aws.amazon.com/hcp/100307/
DIR   s3://hcp.aws.amazon.com/hcp/103515/
DIR   s3://hcp.aws.amazon.com/hcp/111312/
...
DIR   s3://hcp.aws.amazon.com/`hcp`/937160/
2013-04-17 06:57         0   s3://hcp.aws.amazon.com/`hcp`/

```
Get a directory in parallel:


```
:~ s3cmd --parallel --workers=16 get --recursive s3://hcp.aws.amazon.com/`hcp`/100307/T1w T1w

File s3://hcp.aws.amazon.com/`hcp`/100307/T1w/BiasField_acpc_dc.nii.gz started [2 of 52]
File s3://hcp.aws.amazon.com/`hcp`/100307/T1w/Native/100307.L.MyelinMap.native.func.gii started [3 of 52]
...
File s3://hcp.aws.amazon.com/`hcp`/100307/T1w/T2w_acpc_dc_restore.nii.gz saved as 'T1w/T1w/T2w_acpc_dc_restore.nii.gz' (67855816 bytes in 143.3 seconds, 462.31 kB/s)
File s3://hcp.aws.amazon.com/`hcp`/100307/T1w/BiasField_acpc_dc.nii.gz saved as 'T1w/T1w/BiasField_acpc_dc.nii.gz' (65076318 bytes in 180.3 seconds, 352.50 kB/s)

```
 

