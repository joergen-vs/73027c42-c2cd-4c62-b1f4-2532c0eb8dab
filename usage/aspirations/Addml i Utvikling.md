# Addml i Utvikling

## ADDMML v.7

* Pre-defined reference-metadata, separated in archive-name of source and series-name, start- and end-date.
* Pre-defined tests per dataset, file, record and field-level. Separated in controls, analysis and manipulation.
* Documentation of file:
    * Record- and field-separator, along with quotations and padding
    * sql-extraction and -view
    * Charset, number of records and size of file
* Documentation of record:
    * Identifier and lengths of record
    * Primary-, alternate- and foreign-keys
* Documentation of field:
    * Position and length in record
    * Rules on reading value, like datatype and nullable
    * Rules on reading field, like packing and repetition
* Documentation of code:
    * Value in field and explanation of value

![Version 7](https://www.plantuml.com/plantuml/png/5SvD4e8m343XlQVG0vHWGN5SSHCdJIFKwG_Jf7XzSVMMxvj5iMfByNG9cMBpt6eyhwgRF04gVhibwDfS4wvKidBMZag2J-6wS3Qxm3JqTgBH6hBapKXtQzprFHfx6oprx1uU7IGKvGfDS650sK953IKB76i1z3wb-DgdRljJPix-w0y0?cache=no)

## ADDML v.8

* No defined reference-structure, only guidelines. Like mets's agent; agent(name, role, contact(name, email))
* No defined tests, any implementation depends on the tool used for verification
    * Re-structured to resemble the structure
* Added queries, to document usage and the extraction process.
* "How to read" is moved to structureTypes, for files, records and fields.
* Separated file-info from file-definition, to separate information regarding the file (location, checksum) from definition-information (description, identifiers)
    * Record- and field-definitions still contain both location-information along with definition-information.
* Added dataObject to document structures outside of flat-files (like xml).
    * No defined dataObject-structure, guidelines gives examples limited to location, statistics and verification.


![Version 8](https://www.plantuml.com/plantuml/png/5SvFie8m383n_Jl5ym0bM50OLzp4ITC8TVg7QLAylhZwbjzl4SMgBSM_IyWKc-TMu_-ckii3eEAdMuDkpJNXIYKhP-se97WNhYjdSmXCGsyd6gqXIzwCTBV6NL-ZiRV1KizkzkWWeIXNQ88h0yeUAceeMU1S2w3tAJwFkTj_aeMpF_i5?cache=no)

## ADDML v.9

* TODO

![Version 9](https://www.plantuml.com/plantuml/png/5SvDje8m343X-Ll5Sm4bM53K4Jlnf6c4Ulh3QLBSlZYwm_lDebYrfVXt2fbYyzng_5zLDta0LFnqIz2rkIPSgMJbh1sL1E_2TU5iTe5fwEr4epLaoPkHhjQuysiqzZ9OwjdTF3f8ACeLck32WBA5YXfA5ZZM0kXzYi_ztcq_oSpP7_q2?cache=no)