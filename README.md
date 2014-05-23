hcv-target-sites
================

Sample files and instructions for HCV Target sites providing electronic data feeds

## Introduction

This project provides sample files and instructions for sites who want to provide electronic data feeds to HCV-TARGET, the Hepatitis C Therapeutic Registry and Research Network.  HCV-TARGET receives data from participating sites and uses UF's RED-I to process and load the data into the REDCap instance that serves as the research data repository.

The sample files in this project describe the data feeds RED-I consumes and provides resources to assist Target sites in making those feeds accessible to RED-I and the HCV-Target project.  

See https://github.com/ctsit/redi for information about RED-I.
See http://www.hcvtarget.org/ for information about HCV-TARGET.

## Files

The files described here help define how to construct a query of the clinical data and how to format the output.  

The query has three dimensions: what, who, and when.  The query must say what values of are of interest.  These are identified by LOINC or SNOMED codes.  The codes of interest are described in "HCV Target Data Dictionary.xlsx".  

The query must say whose data is of interest using a clinical identifier.  Likewise the query needs a research identifier to use in the output data.  This unique research identifier allows this clinical data to be aligned with data in the REDCap system and allows the query to omit clinical identifiers.  This data is generated at the HCV Target site to prevent exposure of the clinical identifiers outside the site.  The file subjectMap.csv provides an example of the fields needed.  

The query must indicate the time frame of interest for each person in the query.  As each person could have a different start and end date on the study, the date ranges must be per person.  The file subjectMap.csv provides an example of the fields needed in additon to the person identifiers already discussed.

Files in the project:

 * "HCV Target Data Dictionary.xlsx" - a modified REDCap data dictionary for the HCV-TARGET project showing which fields can be processed by REDI.  The tab labeled dataDictionaryforREDI provides a summary view of just what is needed by REDI to populate the forms it can handle.  For each such lab field the loinc_code, loinc_component, and loinc_long_common_name are provided to identify which lab components should be exported from the clinical record.  In some cases two or more LOINC codes are identified for a single REDCap field.  RED-I imports data identified by these LOINC codes into the corresponding REDCap field names.  This file describes what values need to be exported from the clinical record.
 * subject_map.csv - a sample input file to a clinical data query.  This file provides clinical identifiers for a person, the corresponding research identifiers and the date range of interest for each person.  This file provides the who and when dimensions to the query of the clinical record.  
 * clinical-data-specification.md - a specification of the file format RED-I can consume.  
 * raw.txt - an example of the file format RED-I can consume.

## Maintainers

This project is maintained by 

  * Philip Chase <pbc@ufl.edu>
  * Nicholas Rejack <nrejack@ufl.edu>
