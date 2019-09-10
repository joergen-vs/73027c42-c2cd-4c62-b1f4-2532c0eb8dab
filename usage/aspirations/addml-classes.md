# Components in additionalElement
All components will be inplemented as a property of additionalElement, in form of a type. Along with this, there is a change in naming, from a human-readable name to machine-readable UUID, along with a new property 'label'. This is to allow truly unique references, along with a dedicated property to be displayed to users.
Components are not extensions of each other, they are rules.
```xml
<additionalElement name="uuid">
  <properties>
    <property name="type">
      <value>component</value>
    </property>
    <property name="label">
      <value>Component</value>
    </property>
  </properties>
</additionalElement>
```
## <a id="component-unit"/>unit
Basic building-block, with the purpose of adding type and label to all components.
#### Properties
* type `Component-name of element`
* label `Label of element`

## <a id="agent"/>agent : [unit](#component-unit)
#### Properties
* role `Representation of individual or organization. Allowed values: ARCHIVIST, CONSUMER, CREATOR, OWNER, PRESERVATION, PRODUCER, SUBMITTER.`

## <a id="organization-agent"/>organization : [agent](#agent)
Found under context.
#### Properties
* entity `Value: ORGANIZATION.`
* info
  * name
  * id `Tax Identification Number or national equivalent`
  * note `Freetext description of agent`
  * address
  * telephone
    * type `FAX, HOME, MOBILE, WORK`
  * email
  * nationality

## <a id="individual-agent"/>individual : [agent](#agent)
Found under context.
#### Properties
* entity `Value: INDIVIDUAL.`
* info
  * name
  * note `Freetext description of agent`
  * address
  * telephone
    * type `FAX, HOME, MOBILE, WORK`
  * email
  * nationality

## <a id="system-agent"/>system : [agent](#agent)
Found under context. Origin of the data.
#### Properties
* entity `Value: SYSTEM.`
* info
  * name
  * version
  * note `Freetext description of agent`
  * type `Type of system.`
  * subjects
    * subject `Fields of knowledge covered by the system`

## <a id="extraction-agent"/>extraction : [system](#system-agent)
Found under content. The archival entity extracted from the system(s) described in context.
* entity `Value: EXTRACTION.`
* info
  * name
  * note `Freetext description of agent`
  * type `Type of extraction.`
  * version ``
  * subjects
    * subject `Fields of knowledge covered by the system`

# Classes in dataObject
All classes will be inplemented as a property of dataObject, in form of a type. Along with this, there is a change in naming, from a human-readable name to machine-readable UUID, along with a new property 'label'. This is to allow truly unique references, along with a dedicated property to be displayed to users.
Classes are not extensions of each other, they are rules.
```xml
<dataObject name="uuid">
  <properties>
    <property name="type">
      <value>class</value>
    </property>
    <property name="label">
      <value>Class-name</value>
    </property>
  </properties>
</dataObject>
```

![Complete](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/joergen-vs/73027c42-c2cd-4c62-b1f4-2532c0eb8dab/master/usage/aspirations/umls/uml.puml)

## <a id="object-unit"/>unit
Basic building-block, with the purpose of adding type and label to all classes.
#### Properties
* type `Class-name of object`
* label `Label of object`

## <a id="container"/>container : [unit](#object-unit)
Top-level object, containing different kinds of data-structures.
#### Properties
* info
  * type `Container-type, like 'MySQL' or 'Noark'`
    * version `Version of container-type`
* [namespace](#namespace) `Namespaces used inside container`

## <a id="namespace"/>namespace : [unit](#object-unit)
Refers to a set of pre-defined objects.
#### Properties
* identifier `Shorthand name used as reference for namespace`
* source `Reference to source`

![Archival](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/joergen-vs/73027c42-c2cd-4c62-b1f4-2532c0eb8dab/master/usage/aspirations/umls/uml-archival.puml)

## <a id="archive"/>archive : [container](#container)
Rotkatalogen for samlingen av filer og dokumenter som gjør opp et arkivuttrekk. Inneholder beskrivelse av selve arkivuttrekket.
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

![Location](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/joergen-vs/73027c42-c2cd-4c62-b1f4-2532c0eb8dab/master/usage/aspirations/umls/uml-location.puml)

## <a id="folder"/>folder : [unit](#object-unit)
Filesystem-folder, used for grouping similar types of files.
#### Properties
* folder
  * name `Relative file-path for folder.`
  * size `Size of folder in bytes.`
* info
  * numberOf
    * '.extension' `Number of files recursively in folder, based on extension. All files available with '.*'`

## <a id="file"/>file : [unit](#object-unit)
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

## <a id="xmlFile"/>xmlFile : [dataFile](#dataFile)
Xml-file.
#### Properties
* schemas
  * schema `Connects a validation-file to a xml-file.`
    * fileReference `Reference to the file to validate the xml-file against`

## <a id="delimitedFile"/>delimitedFile : [dataFile](#dataFile)
File where the records and fields are separated by a delimiter.

## <a id="fixedLengthFile"/>fixedLengthFile : [dataFile](#dataFile)
File where the length of records and fields do not vary.

## <a id="record"/>record : [unit](#object-unit)
Composed of fields.
#### Items
* field

## <a id="dataRecord"/>dataRecord : [record](#record)
Sub-class for record, adding definition-reference and type-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the record.`
* typeReference `Reference to type-object which contains how the record is read.`

## <a id="xmlRecord"/>xmlRecord : [dataRecord](#dataRecord)
TBD

## <a id="delimitedRecord"/>delimitedRecord : [dataRecord](#dataRecord)
TBD

## <a id="fixedLengthRecord"/>fixedLengthRecord : [dataRecord](#dataRecord)
TBD

## <a id="key"/>key : [unit](#object-unit)
Key for record, in the form of primary, foreign and candidate.

## <a id="primaryKey"/>primaryKey : key
..

## <a id="candidateKey"/>candidateKey
..

## <a id="foreignKey"/>foreignKey
..

## <a id="field"/>field : [unit](#object-unit)
Contains one item of information.

## <a id="dataField"/>dataField : [field](#field)
Abstract class for field, adding definition-reference and type-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the field`
* typeReference `Reference to type-object which contains how the field is read.`

## <a id="xmlField"/>xmlField : [dataField](#dataField)
TBD

## <a id="delimitedField"/>delimitedField : [dataField](#dataField)
TBD

## <a id="fixedLengthField"/>fixedLengthField : [dataField](#dataField)
TBD
#### Properties
* startPos
* endPos
* 

![Definition](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/joergen-vs/73027c42-c2cd-4c62-b1f4-2532c0eb8dab/master/usage/aspirations/umls/uml-definition.puml)

## <a id="defintions"/>defintions
Collection of definition-objects
#### Items
* [definition](#definition)

## <a id="definition"/>definition : [unit](#object-unit)
..
#### Items
..
#### Properties
..

## <a id="fileDefinition"/>fileDefinition : [definition](#definition)
Declaration of how the file is structured
#### Items
* recordDefinitionReference `Reference-object pointing to a record.`
  * definitionReference `Pointer to recordDefinition.`
  * minOccurs `Lower limit of occurence of record in file.`
  * maxOccurs `Upper limit of occurence of record in file.`

## <a id="recordDefinition"/>recordDefinition : [definition](#definition)
Declaration of how the record is structured.
#### Items
* fieldDefinitionReference `Reference-object pointing to a field.`
  * definitionReference `Pointer to fieldDefinition.`
  * minOccurs `Lower limit of occurence for field in record.`
  * maxOccurs `Upper limit of occurence for field in record.`
* recordDefinitionReference `Reference-object pointing to a record.`
  * definitionReference `Pointer to recordDefinition.`
  * minOccurs `Lower limit of occurence of record in record.`
  * maxOccurs `Upper limit of occurence of record in record.`

## <a id="definitionReference"/>definitionReference : [unit](#object-unit)
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
* definitionReference `Pointer to recordDefinition`
* minOccurs `Lower limit of occurence of record.`
* maxOccurs `Upper limit of occurence of record.`

## <a id="fieldDefinition"/>fieldDefinition : [definition](#definition)
..
#### Items
* codes `Contains pre-defined code-values for field`

## <a id="codes">codes</a>
Collection of code-objects
#### Items
* [code](#code)

## <a id="code"/> code : [unit](#object-unit)
Contains pre-defined code-values for field
#### Properties
* description `Meaning behind the value.`
* value `Code-value.`

![Type](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/joergen-vs/73027c42-c2cd-4c62-b1f4-2532c0eb8dab/master/usage/aspirations/umls/uml-type.puml)

## <a id="types">types</a>
Collection of type-objects
#### Items
* [type](#type)

## <a id="type"/>type : [unit](#object-unit)
..
#### Items
..
#### Properties
..

## <a id="processes"/>processes
Collection of process-objects
#### Items
* [process](#process)

## <a id="process"/>process : [unit](#object-unit)
..
#### Items
..
#### Properties
..

# ```Wishlist```
## <a id="database"/>database

## <a id="table"/>table

## <a id="column"/>column
