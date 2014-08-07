# Clinical Data Specification

Clinical data from an EHR should conform to this specification.  

* All data will be returned in the UTF-8 character set
* The first row of the file will be a header row showing the name of each column, enclosed in double quotes and separated by commas. 
* The field names in the header row are not strictly required, but the data they describe is required for REDI to load the data into REDCap. 
* The component_id needs to be a unique identifier for this test.  This could be an identifier local to your EHR or a LOINC code.  If the lab component identifier is a loinc code, please label it as such.
* Subsequent rows will show lab result values. All values will be enclosed in double quotes and separated by commas.
* Each row will show one lab result value.  

These fields may be specified in the data file: 

    Field Name      Field Required?  Field Description
    STUDY_ID            yes          Identifier of a person within a study
    NAME                yes          Name of lab component
    COMPONENT_ID        yes          Numeric identifier of lab component
    RESULT              yes          Result value for lab component
    REFERENCE_UNIT      yes          Units for ORD_VALUE
    DATE_TIME_STAMP     yes          Date and time specimen was taken from the patient/study subject. Date must be formatted as "YYYY-MM-DD HH:MM:SS". This corresponds to SNOMED SCTID: 399445004, "Specimen collection date (observable entity)."
    RESULT_DATE			yes			 Date that result was reported by the laboratory. This corresponds to SNOMED SCTID: 399651003, "Date of report (observable entity)."
    
