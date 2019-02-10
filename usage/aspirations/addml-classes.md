<style>
dO{color:blue}
pp{color:orangered}
val{color:green}
classRef{color:lightsteelblue}
</style>
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
## <a id="unit"/>unit
Basic building-block, with the purpose of adding type and label to all classes.
#### Properties
* type `Class-name of object`
* label `Label of object`

## <a id="container"/>container : [unit](#unit)
Top-level object, containing different kinds of data-structures.
#### Properties
* info
  * type `Container-type, like 'MySQL' or 'Noark'`
    * version `Version of container-type`
* [namespace](#namespace) `Namespaces used inside container`

## <a id="namespace"/>namespace : [unit](#unit)
Refers to a set of pre-defined objects.
#### Properties
* identifier `Shorthand name used as reference for namespace`
* source `Reference to source`

## <a id="archive"/>archive : [container](#container)
..
#### Items
* [definitions](#definitions) `Defines the meaning of the objects in the structure.`
* [file](#file) `Files which are part of the archive, as metadata or documentation.`
* [folder](#folder) `Folders which are part of the archive.`
* [processes](#processes)
* [types](#types) `Defines how the structure is supposed to be read.`
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

## <a id="folder"/>folder : [unit](#unit)
Filesystem-folder, used for grouping similar types of files.
#### Properties
* folder
  * name `Relative file-path for folder.`
  * size `Size of folder in bytes.`
* info
  * numberOf
    * '.extension' `Number of files recursively in folder, based on extension. All files available with '.*'`

## <a id="file"/>file : [unit](#unit)
File in the archive.
#### Properties
* file
  * name `Relative file-path.`
  * size `Size of file in bytes.`
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

## <a id="dataFile"/>dataFile : [file](#file)
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

## <a id="xmlFile"/>xmlFile : dataFile
Xml-file.
#### Properties
* schemas
  * schema `Connects a validation-file to a xml-file.`
    * fileReference `Reference to the file to validate the xml-file against`

## <a id="delimitedFile"/>delimitedFile : dataFile
File where the records and fields are separated by a delimiter.

## <a id="fixedLengthFile"/>fixedLengthFile : dataFile
File where the length of records and fields do not vary.

## <a id="record"/>record : [unit](#unit)
Composed of fields.
#### Items
* field

## <a id="dataRecord"/>dataRecord : record
Sub-class for record, adding definition-reference and type-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the record.`
* typeReference `Reference to type-object which contains how the record is read.`

## <a id="xmlRecord"/>xmlRecord
TBD

## <a id="delimitedRecord"/>delimitedRecord
TBD

## <a id="fixedLengthRecord"/>fixedLengthRecord
TBD

## <a id="key"/>key : [unit](#unit)
Key for record, in the form of primary, foreign and candidate.

## <a id="primaryKey"/>primaryKey : key
..

## <a id="candidateKey"/>candidateKey
..

## <a id="foreignKey"/>foreignKey
..

## <a id="field"/>field : [unit](#unit)
Contains one item of information.

## <a id="dataField"/>dataField : field
Abstract class for field, adding definition-reference and type-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the field`
* typeReference `Reference to type-object which contains how the field is read.`

## <a id="xmlField"/>xmlField
TBD

## <a id="delimitedField"/>delimitedField
TBD

## <a id="fixedLengthField"/>fixedLengthField
TBD
#### Properties
* startPos
* endPos
* 

## <a id="defintions"/>defintions
Collection of definition-objects
#### Items
* [definition](#definition)

## <a id="definition"/>definition : [unit](#unit)
..
#### Items
..
#### Properties
..

## <a id="fileDefinition"/>fileDefinition : [definition](#definition)

#### Items
* recordDefinitionReference `Reference-object pointing to a record.`
  * definitionReference `Pointer to recordDefinition.`
  * minOccurs `Lower limit of occurence of record in file.`
  * maxOccurs `Upper limit of occurence of record in file.`

## <a id="recordDefinition"/>recordDefinition : [definition](#definition)
Declaration of how the record is constructed.
#### Items
* fieldDefinitionReference `Reference-object pointing to a field.`
  * definitionReference `Pointer to fieldDefinition.`
  * minOccurs `Lower limit of occurence for field in record.`
  * maxOccurs `Upper limit of occurence for field in record.`
* recordDefinitionReference `Reference-object pointing to a record.`
  * definitionReference `Pointer to recordDefinition.`
  * minOccurs `Lower limit of occurence of record in record.`
  * maxOccurs `Upper limit of occurence of record in record.`

## <a id="definitionReference"/>definitionReference : [unit](#unit)
Reference-object pointing to a definition
#### Properties
* definitionReference `Pointer to definition.`

## <a id="fieldDefinitionReference"/>fieldDefinitionReference : [definitionReference](#definitionReference)
Reference-object pointing to a fieldDefinition
#### Properties
* minOccurs `Lower limit of occurence of field.`
* maxOccurs `Upper limit of occurence of field.`

## <a id="recordDefinitionReference"/>recordDefinitionReference : [definitionReference](#definitionReference)
Reference-object pointing to a recordDefinition
#### Properties
* minOccurs `Lower limit of occurence of record.`
* maxOccurs `Upper limit of occurence of record.`

## <a id="fieldDefinition"/>fieldDefinition : [definition](#definition)
..
#### Items
* codes `Contains pre-defined code-values for field`

## <a id="codes"/>codes
Collection of code-objects
#### Items
* [code](#code)

## <a id="code"/> code : [unit](#unit)
Contains pre-defined code-values for field
#### Properties
* description `Meaning behind the value.`
* value `Code-value.`

## <a id="types"/>types
Collection of type-objects
#### Items
* [type](#type)

## <a id="type"/>type : [unit](#unit)
..
#### Items
..
#### Properties
..

## <a id="processes"/>processes
Collection of process-objects
#### Items
* [process](#process)

## <a id="process"/>process : [unit](#unit)
..
#### Items
..
#### Properties
..

# ```Wishlist```
## <a id="database"/>database

## <a id="table"/>table

## <a id="column"/>column