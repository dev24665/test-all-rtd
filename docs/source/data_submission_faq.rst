Data Submission
=======

How do I submit data to PDC?
-----------
Detailed instructions for submitting data into the PDC are available here.

How do I register my program with PDC?
-------------  
PDC currently accepts Mass Spectrometry data from proteomic experiments specifically for data dependent and data independent acquisitions. You may contact PDCHelpDesk@mail.nih.gov to request a program for your lab.

How do I configure my AWS account to upload data from my S3 bucket to PDC?
--------------  
In order to use the S3 transfer feature, you need to configure your AWS account and S3 bucket to allow us to copy.
First you will need to have an AWS Access Key and AWS Secret Key from an IAM user that has access to your bucket. The IAM policy should look something like this:

How do I register my program with PDC?
-----------
PDC currently accepts Mass Spectrometry data from proteomic experiments specifically for data dependent and data independent acquisitions. You may contact PDCHelpDesk@mail.nih.gov to request a program for your lab.

How do I configure my AWS account to upload data from my S3 bucket to PDC?
------------
In order to use the S3 transfer feature, you need to configure your AWS account and S3 bucket to allow us to copy.
  
First you will need to have an AWS Access Key and AWS Secret Key from an IAM user that has access to your bucket. The IAM policy should look something like this:  


Then you will need to update your bucket policy to allow us to copy by adding our ARN with get object permission. The source bucket policy should look something like this:  

What types of raw data does PDC accept?
-------------  
PDC accepts various proprietary data formats developed by different manufacturers of mass spectrometers such as “.raw”, “.d”; “.wiff”; “.wiff.scan”; “.wiff.mtd”; “.dat”; “.mis”. If you encounter a data format that is not currently supported while uploading to the submission portal, please reach out to the PDC helpdesk for assistance.

Note:

For AB Sciex (formerly Applied Biosystems) series of mass spectrometers, such as the AB Sciex TripleTOF and QTRAP, which produce WIFF format data, it's important to note that multiple files may represent one raw file. In such cases, users are required to upload all associated files together in the same upload.

For Bruker instruments like the Bruker Tims Tof series, where a folder represents one raw file, users should compress individual .d folders corresponding to a single raw file into a single zip file. The compressed file should be named in the format "file.d.zip" to correspond to the original file name.  
