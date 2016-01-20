# ConMeds Data Specification

Concurrent medications data from an EHR should conform to this specification.  

* All data will be returned in the UTF-8 character set
* The data file needs to be named conmeds.txt for consistency.
* The first row of the file will be a header row showing the name of each column, enclosed in double quotes and separated by commas. 
* The field names in the header row are required, but the data they describe is required for REDI to load the data into REDCap. 
* Subsequent rows will show lab result values. All values will be enclosed in double quotes and separated by commas.
* Each row will show one lab result value.  
* Required fields may have blank values if data is missing.
* If your institution does not have RXNORM_CD you may substitute a column with a local unique identifier.

These fields may be specified in the data file: 

    Field Name      		        Field Required? Field Description                 Format or Example       Note
    MED_ORDER_START_DATE	        yes				Medication start date (for order) YYYY-MM-DD HH:MM:SS
    MED_ORDER_DATE                  no (optional)   Medication order date.            YYYY-MM-DD HH:MM:SS     Use if MED_ORDER_START_DATE not present in your system.
    MED_ORDER_END_DATE		        yes				Medication stop date              YYYY-MM-DD HH:MM:SS
    MED_ORDER_DISPLAY_NAME	        yes				Medication name                   propofol (DIPRIVAN) 10 MG/ML injection
    MED_ORDER_DISCRETE_DOSE         yes				Medication dose                   25-250
    MED_ORDER_DISCRETE_DOSE_UNIT    yes             Medication unit                   mcg
    MED_ORDER_ROUTE_FREQ_DESC       yes             Medication dose frequency         EVERY 4 HOURS
    RXNORM_CD                       no              RxNorm code                       8782
    MEDICATION_ID                   no              Local unique ID for medication    123456                  Use if RXNORM_CD not present.
    STUDY_ID                        yes             ID of a person within a study     123-4567
