Submission process
========

Note: Before you begin the submission, we strongly recommend you use the PDC submission template to collect the information required for a successful submission.

Now you are ready to begin the submission process. You need to follow the steps in the order given in the Submission Overview (image) at the top of this document to avoid duplicating steps

The submission process involves the following major activities,

Creating an instrument to upload raw data
Create a project under which to group the raw data into a Study that was generated using a specific experimental protocol
Upload biospecimen and clinical metadata for the samples used in the Studies
Upload any additional supplementary files

Create an instrument
----------------  

An instrument is a representation of the mass spectrometer from your lab. Go to create, click instrument, and enter the relevant information about the mass spectrometer used to collect the data. If you are a program member, you will receive an email once approved by the PDC admin or the program lead (PI).

Note: You must be added as an assigned instrument operator to upload data to an instrument unless you are the creator of that instrument.

Upload raw files
---------------  

Click upload, and in the dialog requesting information, select the instrument you previously created. You can upload directly from your local computer or from the cloud (AWS S3 is supported) if your files are on S3 already.

PDC accepts various proprietary data formats developed by different manufacturers of mass spectrometers such as “.raw”, “.d”; “.wiff”; “.wiff.scan”; “.wiff.mtd”; “.dat”; “.mis”. If you encounter a data format that is not currently supported while uploading to the submission portal, please reach out to the PDC helpdesk for assistance.

Note:

For AB Sciex (formerly Applied Biosystems) series of mass spectrometers, such as the AB Sciex TripleTOF and QTRAP, which produce WIFF format data, it's important to note that multiple files may represent one raw file. In such cases, users are required to upload all associated files together in the same upload.

For Bruker instruments like the Bruker Tims Tof series, where a folder represents one raw file, users should compress individual .d folders corresponding to a single raw file into a single zip file. The compressed file should be named in the format "file.d.zip" to correspond to the original file name.

Tip: You may create a separate instrument for each study that you would like to create, even if all those files are generated from the same mass spectrometer. This is not required, but may help to organize and separate your files, facilitating study creation.


Validate file metadata
--------------  

To use these files to create your studies, you must first validate the file metadata. This ensures that the upload was successful, and no file corruption or truncation has occurred. To do this, you will need the "File_Metadata" sheet from your PDC Data Submission Template saved as a TSV file.

Once you have the TSV file, return to the workspace and look for your program under the "My Programs" section in the left panel. From there, click on the "Instruments" link under your program name.

Locate the name of the instrument you uploaded your files to and select the 3 vertical dots in front of your instrument name.

Click "Validate File Metadata." In the pop-up window, click "browse files" and select the TSV file that you created from the "File_Metadata" worksheet, and click Upload.

A verification log will appear listing which files:

Were successfully validated.
Were not present in your instrument but are present in the TSV file.
Were present in the instrument but missing from your TSV file.
Have failed verification.

If you have files that failed verification, click on the 3 vertical dots in front of your instrument name and select “Show Files”. Within the metadata verification column, click on the “Failed Verification” text to open a window showing the metadata differences.

These differences may be the result of corruption or truncation of the file when uploading to Workspace. Check your metadata worksheet and make sure the values are correct; if they are, then you will need to delete, re-upload and validate the failed files. Once all files have successfully validated, they may be used in the creation of your studies.

Create a Project
-------------  

Before you can create a Study or add your Protocol, you first need to create a Project.

Click Create->Project to open the wizard. Next, give your Project a name, select a Program and area of Research. You may also add collaborators to your project using the Sharing tab.

Create a Protocol
--------------
  
Next, you will add the protocol metadata used in your Study. Click Create->Protocol to open the wizard. Required fields are marked with *. If you are unable to complete your protocol, you can ‘Save as Draft’ and resume later.

You can locate your protocol draft using the left navigation panel. Under “View Type” Click “My” and under “Data Type” click “Protocol drafts.” Locate your protocol name and click the vertical dots in front of your protocol name for a menu to appear.

Click "Edit" and proceed with entering your protocol data.

If you feel that the wizard does not adequately meet your annotation needs for your particular Protocol, please contact the PDC by email for help resolving any issues.


Create a Study
--------------  

In the PDC workspace, a study is a group of instrument raw files that are generated using a specific experimental protocol, with a well-annotated experimental design (sample to file mapping) that can be analyzed through a single bioinformatics pipeline.

To create the study, click Create->Study to launch the wizard. In the wizard, for steps requiring you to enter data in tabular form for the sample/aliquot to file mapping, you may copy and paste from the Experimental Run Metadata sheet from the PDC submission template you prepared. If you are unable to complete your study, you can click ‘Save as Draft’ to resume later.


You can locate your study draft using the left navigation panel. Under “View Type” Click “My” and under “Data Type” click “Study drafts.” Locate your study name and click the vertical dots in front of your study name for a menu to appear.

Click "Edit" and proceed with entering your study data.

Upload Clinical & Biospecimen Metadata
-----------

To load the Clinical and Biospecimen data, save the Case Matrix, Case, Demographics, Diagnosis, Exposure, Family History, Treatment, Follow-Up, Sample, and Aliquot worksheets as TSV files from the PDC Submission template you prepared.

Note: Clinical and biospecimen metadata should be submitted for all the aliquots (their parent samples and cases) that are entered in the Study creation step.

All 10 files are required for upload, but if you have no data for the Exposure, Family History, Treatment, and Follow-Up entities you may include empty files containing only the column headers. 
Place all 10 TSV files in a new folder on your local computer. In the workspace click “Upload” then under Metadata click “Direct Upload.”

A popup wizard to upload the metadata will appear. Click “Select a File Type” and select “All Clinical & Biospecimen.” Next, click “Select Program” to select the program the metadata belongs to and “Select Project” to choose the project your metadata is associated with. An icon will appear in the wizard giving you the option to upload your files. You can either drag and drop your files or select a folder the files belong to. 
A notification will appear requesting you to confirm the upload of all files from that folder. Click “Upload” to confirm.

When all 10 TSV files are present, click "Upload" and you will have successfully uploaded your files.

The clinical and biospecimen data you uploaded can be viewed by locating the navigation panel on your left and under the “File Management” section select “Metadata Files.” 
Select the vertical dots in front of the metadata file name and select “Show Content.”


To view all the metadata you have uploaded, select “My” under the “View Type” section and select Case, Sample, Aliquot, Diagnosis, or Demographic under the “Data Type” section. 
As seen below, by selecting View Type “My” and Data Type “Case” you would see the metadata you uploaded for Case.

If you need to make changes to your clinical and biospecimen metadata, you will need to either reupload or update your data. 
To reupload, you first need to delete all your metadata files. Locate the navigation panel on your left and under File Management select “Metadata Files.” 
Select the files to delete and click the delete icon at the top.

To update your metadata. Click 'Upload', then select 'Direct Upload' under 'Metadata'. Within the 'Upload Metadata' window, select 'Update Existing Metadata'.

Select the metadata upload set you wish to update; the name of the set contains the prefix or suffix of your TSV files and a timestamp of the original upload. Once you have selected a set to update, upload the set of 10 TSVs for the cases, samples, and aliquots you wish to update. 
You may choose to include only a subset of the cases, samples, and aliquots included in the original upload, but cannot include those that were not included in the original set.

Upload additional supplementary files
--------------

You may also upload additional supplementary files (non-raw files), such as processed outputs from your own data analysis pipeline, SOPs, clinical data, etc. You can select the appropriate data category for the files you wish upload - ‘Alternative Processing Pipeline’, ‘Other Metadata’ and ‘Supplementary Data’.

Once you complete the Study creation, you may proceed to upload the supplementary files associated with the study. We recommend you contact the PDC team to validate your study on Workspace before you begin uploading the non-raw files.

To begin uploading any of these types of files, select “Direct Upload” under the ‘Non-Raw Files’ tab in the ‘Upload’ dropdown.

In the upload interface, first you must select the study you wish to associate the files with, and the type of file. 
You may choose to directly select a study, and the ‘Program’ and ‘Project’ options will be automatically filled.

The Data Source ‘Submitter’ will be automatically filled in. The other option, CDAP, is used by the PDC team to handle the upload of files produced by the “Common Data Analysis Pipeline.” 
Choose the data category you wish to upload from the ‘Data Category’ dropdown. Note that you will only be able to upload files with extensions belonging to that category. You may choose to upload a directory of files simultaneously, and file extensions that do not match the selected category will be automatically removed. However, note that some data categories have overlapping file extensions. You may wish to organize your files by data category prior to uploading.

This completes the process of submission of a dataset for release through the PDC data portal. If you have any questions about this process, please contact the PDC by email for help PDCHelpDesk@mail.nih.gov.


