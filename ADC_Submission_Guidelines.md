---
title: "Arctic Data Submission Guidelines"
date: May 8, 2018
output:
  html_document: default
---

## Introduction

With few exceptions, the NSF Office of Polar Programs requires that metadata, full datasets, and derived data products be deposited in a long-lived and publicly accessible archive. Specific requirements for various Office of Polar Programs programs can be found [here](https://www.nsf.gov/pubs/2016/nsf16055/nsf16055.jsp). The Arctic Data Center at http://arcticdata.io was created with funding from NSF to assist with compliance of these requirements by providing a long-lived and publicly accessible archive for Arctic Sciences Section (ARC) data and metadata. At a minimum, metadata describing ARC-supported data packages must be submitted to the Arctic Data Center. 

The following documentation provides guidelines to assist with submission of [data packages](#what-is-a-data-package) to the Arctic Data Center. If you have additional questions please see the [Q and A](https://arcticdata.io/q-and-a/) section of the Center's website, or contact support@arcticdata.io and a member of the Arctic Data Center support team will respond promptly.

## What is a Data Package?

The Arctic Data Center primarily archives data packages. Data packages on the Arctic Data Center are simply defined as a collection of related data and metadata files. On the Arctic Data Center, each data package should contain, when possible, all of the relevant data and metadata from a specific research project (or sub-project/project component).

Depending on the size of a research project, multiple data packages may be associated with a single research project. For example, if a research project consists of field sampling at several distinct sites or over several distinct sampling seasons, each site/season may have its own unique data package. When submitting to the Arctic Data Center, it is up to the best judgement of the submitting researcher how his/her research should be grouped. If it is determined that multiple data packages are desirable for a research project, multiple data packages can be made by separately going through the [Arctic Data Center website submission tool](https://arcticdata.io/catalog/#share) for each subset. Furthermore, after submitting multiple data packages, the support team (support@arcticdata.io) can help nest related data packages together. See [here](https://arcticdata.io/catalog/#view/urn:uuid:46789d94-7c12-4d9f-9e62-7f90f7918219) for an example of how nested data packages render on the website.

## File Organization Guidelines

In order to optimally document and share a project's output, quality data file management is necessary. Some resources for best practices for managing data files can be found [here](https://www.dataone.org/best-practices) and [here](https://esajournals.onlinelibrary.wiley.com/doi/full/10.1890/0012-9623-90.2.205). The following are a few guidelines that are encouraged for file organization for projects that plan to submit to the Arctic Data Center. Following these guidelines should help ensure a project's outputs are easy to access and understand.

- All files should have short, descriptive names.
- Only letters, numbers, hyphens (“-“), and underscores (“_”)
should be used in file names. Always avoid using spaces and specialized ASCII characters when naming files.
- All files should be stored in open-source, ubiquitous, and easy-to-read file formats (see [File Format Guidelines](#file-format-guidelines)).
- Tabular data should be submitted in a long (versus wide) format if possible. Long file formats will make documentation of attributes (variables), as well as access to the data, much easier.
- For models/scripts, all files necessary to run the code should be included and organized in a manner that makes running the code as accessible as possible. If outside dependencies (software, hardware, or otherwise) are needed to run code which cannot be submitted to the Arctic Data Center, details of these dependencies should be made clear within the metadata description of the code files as well as within the method's metadata. For large models see [Guidelines for Large Models](#guidelines-for-large-models).


## File Format Guidelines

The Arctic Data Center primarily supports and encourages the upload of open-source, ubiquitous, and easy-to-read file formats. Examples of such formats are Comma Separated Values (CSV) files, text (TXT) files, PNG, JPEG or TIFF image files, R or Python scripts, and NetCDF files, among many others.
For projects that plan to submit to the Arctic Data Center, it is strongly advised to incorporate plans for creating open-source files from the initial stages of project development (i.e. within the data management plan of the project proposal). If work with any proprietary data formats such as Excel workbooks or MATLAB files is deemed necessary, plans should be made early on to transform all data stored in these formats into open-source formats before submission to the Arctic Data Center. If for any reason it is determined that certain files created in a project must be submitted in a proprietary format, the Center may request an explanation before publishing the files.

- For tabular data, it is advised to use common file formats such as CSV or TXT.
- For image files, it is advised to use common file formats such as PNG, JPEG, TIFF, etc.
- For GIS files, it is acceptable to submit ESRI files.
- For MATLAB or other matrix-based programs, it is advised to use NetCDF (an open binary format).
- NetCDF is also encouraged for many files due to the ability to organize and document files in such a format. See [here](https://www.unidata.ucar.edu/software/netcdf/docs/index.html) for more information about NetCDF files.

## Metadata Guidelines

The Arctic Data Center primarily stores metadata using the [Ecological Metadata Language (EML)](https://knb.ecoinformatics.org/#external//emlparser/docs/eml-2.1.1/index.html). Transformation of plain text metadata documentation into an EML format for archiving will be done automatically when submitting through the [Arctic Data Center website](https://arcticdata.io/catalog/#share). It is advised for projects that plan to submit to the Arctic Data Center that complete, plain text metadata records be readily available before submission. Accordingly, plans to create and store metadata records should be made during the initial stages of project development (i.e. within the data management plan of the project proposal).

The goal of metadata is to document a project's output so that a reasonable scientist will be able to understand and use all the components of the output without any outside consultation. The following components represent a non-exhaustive list of components typically expected within metadata records submitted to the Arctic Data Center:

- A descriptive title that includes the topic, geographic location, dates, and, if applicable, the scale of the data.
- A descriptive data package abstract that provides a brief overview summarizing the specific contents and purpose of the data package.
- Funding information (typically the NSF award number).
- A list of all people or organizations associated with the data package with at least one person or organization acting as a creator and one acting as a contact (these can be the same). See the [Identification Guidelines](#identification-guidelines) for more information about listing people within Arctic Data Center metadata records.
- Full records of field and laboratory sampling times and locations, including a geographic description interpretable by a general scientific audience. 
- Full records of taxonomic coverage within the data package (if applicable). 
- Full descriptions of field and laboratory sample collection methods.
- Full descriptions of field and laboratory sample processing methods.
- Full descriptions of any hardware and software used (including make, model, and version where applicable). 
- Full attribute/variable information for all data (see [Metadata Guidelines for Tabular Data](#metadata-guidelines-for-tabular-data)).
- Quality control procedures.
- Relevant explanations for why the particular components detailed above were chosen for the project.

Additional guidance for specific metadata cases is included below.

### Metadata Guidelines for Tabular Data

For data packages with tabular data (e.g. CSV files), submitted metadata should contain the following components for **every** attribute (attributes may also be known as variables and in tabular data are arranged in either columns or rows). Note, storage of data in a long versus wide format will allow for more succinct metadata (see [File Organization Guidelines](#file-organization-guidelines). Also, please note that tabular data stored within structured formats such as zip, NetCDF, or ESRI spatial files should also comply with these guidelines. 

- A name (often the column or row header in the file). Like file names, only letters, numbers, hyphens (“-“), and underscores (“_”) should be used in attribute names. Always avoid using spaces and specialized ASCII characters when naming attributes.
- A complete definition. The definition should fully clarify the measurement to a broad scientific audience. For example, a definition like %C may always be interpreted within a certain discipline in a uniform way. However, it might always be interpreted within another certain discipline in a different uniform way. A full technical definition such as "percent soil carbon by dry soil mass" helps to limit possible confusion.
- Any missing value codes along with explanations for those codes.
- For all numeric data, unit information is needed.
- For all date-time data, a date-time format is needed (e.g. "YYYY-MM-DD").
- For text data, full descriptions for all patterns/codes are needed if the text is constrained to a list of patterns or codes (e.g. a phone number would be constrained to a certain pattern and abbreviations for site locations may be constrained to a list of codes). 

### Metadata Guidelines for Software

For data packages with software (including models), submitted metadata should contain the following components, among others:

- Instructions on how to use the software.
- Version information.
- Licensing information.
- A list of software/hardware used in development.
- A list of software/hardware dependencies needed to run the software.
- Information detailing source data for models.
- Any mathematical/physical explanations needed to understand models.
- Any methods used to evaluate models.

## Submission Guidelines for Large Data Packages

The Arctic Data Center does not have data package or file size limitations for NSF funded projects. Many multi-terabyte data packages have been archived on the Arctic Data Center. In most cases, all data and metadata relevant to each project should be archived regardless of total file size (note, non-NSF funded projects may be subject to a one-time processing fee depending on the total data package size). The [Arctic Data Center website](https://arcticdata.io/catalog/#share) can handle the upload of multiple large files simultaneously. However, users with slow internet connections or users that experience any trouble uploading any file through the website should contact the Arctic Data Center support team at support@arcticdata.io. The Arctic Data Center support team has many options to upload large data packages when connection speed is limited or files are exceptionally large.
 
### Guidelines for Large Models

Models with extensive outputs are a case where data package sizes can become substantially large. In general, it is advised to archive the model output if it is relevant to the project. That being stated, sometimes model output can be regenerated from archived input data and model code. Accordingly, depending on the specifics of a project, it may be reasonable to archive only the code and model inputs as well as a clear workflow on how to recompute the model output (rather than the output itself).  However, if re-running the model would require prohibitive amounts of compute cycles or other resources (such as access to specialized or expensive software or hardware), then it is still recommended to archive the output especially if the output is a valuable data package that others may want to analyze and use in their own work. For example, many climate model outputs are difficult for the average scientist to recompute but are valuable for a myriad of downstream uses. Additionally, some models are stochastic and the interpretation of subsequent products depends on specific model runs. In these (and most related cases) archival of model outputs is recommended.


## Identification Guidelines

The Arctic Data Center utilizes [ORCID iDs](https://orcid.org/) to identify individuals associated with each data package. When submitting to the Arctic Data Center, an ORCiD is required for the submitter of each data package. ORCiDs are not required for all associated parties (contacts, additional creators, etc.), but are strongly encouraged, especially for the primary creator, so that proper identification and attribution can be given. Additionally, access to edit each data package can only be granted to individuals using ORCiDs. Therefore, it is advised that a plan to [register](https://orcid.org/register/) and record ORCID iDs for each individual involved with the project be created during the initial stages of project development (i.e. within the data management plan of the project proposal).

## Publication Policy

The Arctic Data Center provides a long-lived and publicly accessible system that is free for users to obtain data and metadata files. Complete submissions to the Center meet [the requirements set by The Office of Polar Programs](https://www.nsf.gov/pubs/2016/nsf16055/nsf16055.jsp) which require that metadata files, full datasets, and derived data products be deposited in a long-lived and publicly accessible archive. 

Submission of data packages to the Arctic Data Center is free for all NSF ARC-funded projects. data packages from projects funded by sources that do not include NSF are permitted to submit to the Center but may be subject to a one-time processing fee, depending on the size and processing needs of the data package. Additionally, data packages from projects not funded by NSF ought to cover Arctic science-relevant research to be published on the Arctic Data Center. Please note that submissions of NSF-funded data packages are prioritized in our processing queue. 

The Arctic Data Center publicly releases data packages once complete data packages have been submitted and compiled. In the typical submission process, users will submit data to the Arctic Data Center through the [Arctic Data Center website](https://arcticdata.io/catalog/#share) (see [Alternative Submission Methods](#alternative-submission-methods) or [Submission Support](#submission-support) if needed). Then, the Center's support team will review the data package. If the support team discovers any issues with the initial submission, the data team will work with the submitter to resolve the issues as quickly as possible (we primarily correspond via emails from support@arcticdata.io to the email address registered with the submitter's ORCID iD). **It is advised to submit data packages well before deadlines.** For most ARC-funded projects, all data and metadata submissions are due within two years of collection or before the end of the award, whichever comes first. The data submission deadline is stricter for Arctic Observing Network (AON) projects, with real-time data needed to be made publicly available immediately and all data required to be fully quality controlled and submitted within 6 months of collection. Please see below for the [submission requirement exceptions](#licensing-and-data-distribution-policy) for sensitive social science data.

Depending on the complexity of the data package and the quality of the initial submission, the review process can take anywhere from a few hours to several weeks. Long processing times generally occur when initial submissions have incomplete metadata and/or poorly organized files and/or the submitter is not responsive to follow-up emails. Compliance with the guidelines detailed here should ensure quick processing times. Well organized and complete data packages can potentially be published within one business day. After the review process, each data package will be given a unique Digital Object Identifier (DOI) that will assist with attribution and discovery.	

## Licensing and Data Distribution Policy

All data and metadata published to the Arctic Data Center will be released under either the CC-0 Public Domain Dedication or the Creative Commons Attribution 4.0 International License (CC-BY), with the potential exception of social science data that have certain sensitivities related to privacy or confidentiality. In cases where legal (e.g., contractual) or ethical (e.g., human subjects) restrictions to data sharing exist, requests to restrict data publication must be made in advance and in writing and are subject to the approval of NSF, who will ensure compliance with all federal, university, and Institutional Review Board policies on the use of restricted data.	

## Alternative Submission Methods

Most users submit to the Arctic Data Center through the [Arctic Data Center website](https://arcticdata.io/catalog/#share). However, there are several alternative tools to submit data packages to the Center.

- Users can submit data inside an R workflow using the [dataone R package](https://github.com/DataONEorg/rdataone).
- Users can submit data inside a MATLAB workflow using the [Matlab DataONE library](https://github.com/DataONEorg/matlab-dataone).
- In addition to our web and data tools shown above, the Arctic Data Center provides the ability to access and submit data via the [DataONE REST API](https://arcticdata.io/catalog/#api). This allows the community to use many programming languages to add data and metadata to the repository, search for and access data, and automate any process that might otherwise be highly time-consuming. Most useful to groups with repetitive tasks to perform, such as submitting many data files of the same type, the REST API can be a real time saver.

## Submission Support

If, for whatever reason, support with a submission is needed, contact support@arcticdata.io and an Arctic Data Center support team member will respond promptly.

If you have a large volume of files to submit or the total size of your data is too large to upload via the web form, please first submit your complete data package description (metadata) through the Arctic Data Center website and then write to support@arcticdata.io to arrange another method for the data transfer. The support team has multiple options for transferring large amounts of data, including via Google Drive or our SFTP. 