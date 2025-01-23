Data Download 
============

What type of files are available for download from PDC?
------------------
PDC distributes several types of files: those submitted by the original data submitters and those generated through the PDC Common Data Analysis Pipeline (CDAP).

How do I download data?
------------------
There are a few different ways to identify and download the files of interest:

1. Downloading Files from a Specific Study:

a. On the Explore page, click on the specific study of interest, either by the study identifier or study name.
This opens the study summary overlay. Click on the number corresponding to the data category of your interest.
An overlay will appear with a list of files.
Click on the download button next to each file to download them individually.
For information on downloading multiple files at once, see ‘How do I download multiple files at once?’.
b. On the Explore page, studies are listed under the Study tab. Click on the number corresponding to the data category of your interest. This will take you to the ‘Files’ tab.
Click on the download button next to each file to download them individually.
For information on downloading multiple files at once, see ‘How do I download multiple files at once?’.
2. Using Filters to Identify Files:

For example, if you are interested in protein assembly files for all breast cancer studies from the CPTAC program, apply appropriate filters on the 'Explore' page to narrow down the data of interest.
Once you have identified the files, move to the ‘Files’ tab on the Explore page.
Click on the download button next to each file to download them individually.
For information on downloading multiple files at once, see ‘How do I download multiple files at once?’.

How do I download multiple files at once?
------------------
1. Select Files:

Follow the steps in ‘How do I download data?’.
Once you are on the file overlay of the study summary page or the ‘Files’ tab on the Explore page, select one or all files.
Click ‘Export File Manifest’. This manifest will contain a download URL for each selected file on a separate row.
Note: The URLs will expire 7 days (168 hours) after the manifest is generated. You can revisit the PDC portal to generate a new file manifest if needed.

2. Download Methods:

PDC Data Download Client:
Use the PDC Data Download Client, a command-line tool that provides an alternative method for downloading data from PDC and enables resumption of interrupted transfers.
Click here for documentation of PDC Data Download Client.
Sample Scripts:
Use sample scripts (in bash and Python) available on the PDC GitHub to download and reorganize or simply reorganize previously downloaded files into the desired folder structure. You can modify these scripts to suit your needs.
See the FAQ ‘How do I organize the data into a folder structure?’ for more details.
Access the scripts here.
Download Managers:
Use download managers (special programs or browser extensions) that help manage large and multiple downloads.

How do I organize the data into a folder structure?
------------------

By default, all downloaded files will be placed in the same folder without any particular folder structure. The PDC manifest file provides all relevant metadata if you wish to organize them into a folder structure. This is especially useful when analyzing large datasets with labelling experiments.

The following metadata data available in PDC file manifest can be used to organize the files:
PDC Study ID, e.g., PDC000319
PDC Study Version, e.g., 1
Data Category, e.g., Processed Mass Spectra
Run Metadata ID, e.g., AML Gilteritinib TimeCourse - Phosphoproteome-1
File Type, e.g., Open Standard
File, e.g., PTRC_exp12_plex_01_P_f06.mzML.gz

You may use this information to create a folder structure and move the downloaded files into the desired location.
e.g.
PDC Study ID/ PDC Study Version/Data category/Run Metadata ID/File Type/File
PDC000319/1/Processed Mass Spectra/ AML Gilteritinib TimeCourse - Phosphoproteome-1/Open Standard/ PTRC_exp12_plex_01_P_f06.mzML.gz

You may use the following sample scripts (in bash and python) available on PDC github to either download and reorganize or simply reorganize the previously downloaded files into this folder structure. Feel free to modify it to suit your needs.
https://github.com/esacinc/PDC-Public/tree/master/tools/downloadPDCData


Why does the file download URLs throw an error or exception?
------------------

PDC is hosted on AWS cloud and is under active development. To reduce egress costs from unintended downloads, the URLs will expire after 7 days (168 hours). You may revisit the PDC portal to generate a new file manifest. We also limit downloads of the same file from the same IP Address to only 10 times per 24 hour period. So if you have downloaded the file several times already you may get an error message indicating that you have exceeded your download attempts for the 24 hour period.

How do I download clinical and biospecimen data?
------------------
PDC portal allows users to build cohorts by applying various clinical, biospecimen, experimental and file features as filters and export the selections as manifest files.

To download biospecimen (case, sample, aliquot) related data, once you identify the data of your interest by applying filters, move to the 'Biospecimens' tab on the 'Explore' page. Select the checkbox to select a specific row, all rows on the page or all pages and click export biospecimen manifest button in CSV or TSV format.

To download clinical data, once you identify the data of your interest by applying filters, move to the 'Clinical' tab on the 'Explore' page. Select the checkbox to select a specific row, all rows on the page or all pages and click the export clinical manifest button in CSV or TSV format. Clinical data are organized into multiple files and are exported as one zip archive. The archive contains:
Clinical manifest that includes data for demographic and diagnosis.
Exposure manifest that includes exposure related data.
Follow-up manifest that includes follow-up related data.
Treatment manifest that includes treatment related data.
