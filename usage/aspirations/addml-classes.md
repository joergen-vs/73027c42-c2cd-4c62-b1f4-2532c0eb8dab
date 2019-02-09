# Classes

All classes will be inplemented as a property of dataObject, in form of a type. Along with this, there is a change in naming, from a human-readable name to machine-readable UUID, along with a new property 'label'. This is to allow truly unique references, along with a dedicated property to be displayed to users.
Classes are not extensions of each other, they are rules.
```xml
<dataObject name="uuid">
	<properties>
		<property name="type">
			<value>class</value>
		</property>
		<property name="label">
			<value>Class</value>
		</property>
	</properties>
</dataObject>
```
## unit
Small building-block, with the purpose of adding type and label to all classes.
#### Properties
* type `Class-name of object`
* label `Label of object`

## container : [unit](#unit)
Top-level object, containing different kinds of data-structures.
#### Properties
* info
  * type `Container-type, like 'MySQL' or 'Noark'`
    * version `Version of container-type`
* [namespace](#namespace) `Namespaces used inside container`

## namespace : [unit](#unit)
Refers to a set of pre-defined objects.
#### Properties
* identifier `Shorthand name used as reference for namespace`
* source `Reference to source`

## archive : [container](#container)

#### Items
* [file](#file) `Files which are part of the archive, as metadata or documentation.`
* [definitions](#definitions) `Defines the meaning of the objects in the structure.`
* [types](#types) `Defines how the structure is supposed to be read.`
* [processes](#processes)
#### Properties
* info
  * numberOf
    * files `Number of files in archive`
  * sizeOf
    * files `Size of all files in archive`
  * period `Declares the timeperiod for the data in the archive`
    * inboundPeriod `Start-date`
    * outgoingPeriod `End-date`
  * containsScreenedInformation `True or false: Are there metadata in the archive which is screened?`
  * containsBusinessSpesificinformation `True or false: Are there metadata in the archive which is business-specific?`
  * containsDocumentsScheduledForDisposal `True or False: Are there documents in the archive which is scheduled for disposal?`
  * containsDocumentsWhichIsDisposed `True or False: Are there documents in the archive which is disposed?`
## folder : [unit](#unit)
Filesystem-folder, used for grouping similar types of files.
#### Properties
* folder
  * name `Relative file-path for folder.`
* info
  * numberOf
    * '.extension' `Number of files recursively in folder, based on extension. All files available with '.*'`
## file : [unit](#unit)
File in the archive.
#### Properties
* file
  * name `Relative file-path.`
  ```
  Useful, but necessary?
  * format
	* name
	* version
	* mime
	* puid
  ```
  * checksum `Contains the algorithm and value of checksum-calculation for file.`
    * algorithm `Checksum-algorithm used for calculation.`
    * value `Calculated value of file.`
## dataFile : [file](#file)
File with a set of records.
#### Items
* [record](#record)
#### Properties
* definitionReference `Reference to definition-object which contains the description of the file`
* typeReference `Reference to type-object which contains how the file is read.`
* info
  * numberOf `Contains a reference to a type of record, and the number of times it occurs in the file.`
    * recordIdentifier `Name of record-object`
    * recordCount `Number of records`
## xmlFile : dataFile
Xml-file.
#### Properties
* schemas
  * schema `Connects a validation-file to a xml-file.`
    * fileReference `Reference to the file to validate the xml-file against`
## delimitedFile : dataFile
File where the records and fields are separated by a delimiter.
## fixedLengthFile : dataFile
File where the length of records and fields do not vary.
## record : [unit](#unit)
Composed of fields.
#### Items
* keys
  * key `Key-object, in the form of primary, foreign and candidate.`
## dataRecord : record
Sub-class for record, adding definition-reference and type-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the record.`
* typeReference `Reference to type-object which contains how the record is read.`
## xmlRecord
TBD
## delimitedRecord
TBD
## fixedLengthRecord
TBD
## key : [unit](#unit)
Key for record, in the form of primary, foreign and candidate.
## primaryKey : key
..
## candidateKey
..
## foreignKey
..
## field : [unit](#unit)
Contains one item of information.
## dataField : field
Abstract class for field, adding definition-reference and type-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the field`
* typeReference `Reference to type-object which contains how the field is read.`
## xmlField
TBD
## delimitedField
TBD
## fixedLengthField
TBD
## defintions
Collection of definition-objects
#### Items
* [definition](#definition)
## definition : [unit](#unit)
..
#### Items
..
#### Properties
..
## types
Collection of type-objects
#### Items
* [type](#type)
## type : [unit](#unit)
..
#### Items
..
#### Properties
..
## processes
Collection of process-objects
#### Items
* [process](#process)
## process : [unit](#unit)
..
#### Items
..
#### Properties
..
# ```Wishlist```
## database
## table
## column