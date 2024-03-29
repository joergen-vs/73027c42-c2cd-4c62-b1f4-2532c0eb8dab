# Classes in ADDML
This is an attempt to declare complex elements, or classes, for additionalElement- and dataObject-element, along with declaring rules for property-element.

## <a id="unit"/>[unit](#unit)
Abstract building-block, with the purpose of adding type and label. This enables identifying additionalElement or dataObject as classes.
#### Properties
* type `Class-name`
* label `Name for instance of class`

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

## <a id="additionalElement"/>[additionalElement](#additionalElement) : [unit](#unit)
#### Properties
* role `Representation of individual or organization. Allowed values: ARCHIVIST, CONSUMER, CREATOR, OWNER, PRESERVATION, PRODUCER, SUBMITTER.`

Context contains zero or more of the following items:
* agents `Set of agents`
  * [agent](#agent) ([individual](#individual-agent) / [organization](#organization-agent) / [software](#software-agent) / [system](#system-agent))
* comments
    * [comment](#comment)

Content contains zero or more of the following items:
* [extraction](#extraction-agent)
* [documentation](#documentation-agent)
* [namespace](#namespace)
* comments
    * [comment](#comment)

## <a id="agent"/>[agent](#agent) : [additionalElement](#additionalElement)
#### Properties
* role `Representation of individual or organization. Allowed values: ARCHIVIST, CONSUMER, CREATOR, OWNER, PRESERVATION, PRODUCER, SUBMITTER.`

## <a id="organization-agent"/>[organization](#organization-agent) : [agent](#agent)
Found under context.
#### Properties
* entity `Value: ORGANIZATION.`
* info
  * name
  * id `Tax Identification Number or national equivalent`
  * address
  * telephone
    * type `FAX, HOME, MOBILE, WORK`
  * email
  * nationality
  * operationalPeriod `Timeperiod when the organization was active.`
    * startDate
    * endDate `Indicates when organization is shut down.`
  * areal `Ser of areas`
    * area `Functional area of the organisation`

#### Items
* contacts `Set of agents representing the organization`
  * [agent](#agent) (individual / organization / software / system)

## <a id="individual-agent"/>[individual](#individual-agent) : [agent](#agent)
Found under context.
#### Properties
* entity `Value: INDIVIDUAL.`
* info
  * name
  * address
  * telephone
    * type `FAX, HOME, MOBILE, WORK`
  * email
  * nationality

## <a id="software-agent"/>[software](#software-agent) : [agent](#agent)
Found under context. Origin of the data.
#### Properties
* entity `Value: SOFTWARE`
* info
  * name
  * version

## <a id="system-software"/>[system](#system-software) : [software](#software-agent)
Found under context. Origin of the data.
#### Properties
* entity `Value: SYSTEM.`
* info
  * name
  * version
  * type `Type of system.`
  * operationalPeriod `Timeperiod when the system was in use.`
    * startDate
    * endDate `Indicates when system is taken out of use.`
  * subjects `Set of fields`
    * subject `Field of knowledge covered by the system`

## <a id="extraction-software"/>[extraction](#extraction-agent) : [agent](#agent)
Found under content. The archival entity extracted from the system(s) described in context.
#### Properties
* entity `Value: EXTRACTION`
* info
  * name
  * version `Type-version of extraction`
  * type `Type of extraction`
  * archivalperiod `Gives the timeperiod of the extracted data`
    * startDate `Beginning of actual timeperiod`
    * endDate `End of actual timeperiod`
  * agreement `Reference to case-number containing agreement of delivery (preservation-id)`
  * extractionDate `Date when extraction was accomplished`
  * subjects `Set of fields`
    * subject `Fields of knowledge covered by the system`

## <a id="documentation-agent"/>[documentation](#documentation-agent) : [agent](#agent)
Found under content. Describes accompanying documentation, such as manuals for system, user or records managemen plan.
#### Properties
* entity `Value: DOCUMENTATION`
* info
  * name
  * description `Defines what area the documentation covers, like SYSTEM, USAGE, RMP etc.`
  * link `Link to documentation.`
  * reference `Name of dataObject-file or -folder with the documentation.`

## <a id="standard-agent"/>[standard](#standard-agent) : [agent](#agent)
Found under content. Describes standards used, such as structure and files.
#### Properties
* entity `Value: STANDARD`
* info
  * name
  * description `Short description of the standard.`
  * link `Link to standard.`
  * reference `Name of dataObject-file or -folder which uses the standard.`

## <a id="namespace"/>[namespace](#namespace) : [additionalElement](#additionalElement)
Found under content. Connects to a source
#### Properties
* name `Full name of namespace`
* version
* prefix `Shorthand id used for referencing namespace`
* source `Resource identifier specifying the real or virtual origin of namespace`
* reference `Name of dataObject-file with the definitions`

## <a id="comment" />[comment](#comment) : [additionalElement](#additionalElement)
Found under context and content. Contains information.

# Classes in dataObject

## <a id="dataObject"/>[dataObject](#dataObject) : [unit](#unit)
All classes will be inplemented as a property of dataObject, in the form of a type. Along with this, there is a change in naming, from a human-readable name to machine-readable UUID, along with a new property 'label'. This is to allow truly unique references, along with a dedicated property to be displayed to users.
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

![Complete](http://www.plantuml.com/plantuml/png/pPAnRiCm34HtVOMQNP6Zf4rGTCYlq19ZiPKbWwGJvEzh5nawT6yMWdS740y7daM1THwBtK1AOzaO-Q8w0SDe2rNK-uHsQkM-Yh-onfgRCLGL-G8HRMnLOKdP950GLFlXt2_NI8I2TXTEdRrHqlmmJbrdCzAGrPWNgh7C2MSkDgjEykuzmsqxaEQvdmLvlOTLjx6D_hCX3rZTLVnntuLZF0GNGqpk4D-2wtUNWmkl-n0xx4y9UZ-2ABAV1GRq81CnABKgVgdXPpZWcEaAPJijwlznrY9x47mM7BnGfTLy4g3r4HyePwnfMRu1)

## <a id="container"/>[container](#container) : [dataObject](#dataObject)
Top-level object, containing different kinds of data-structures.
#### Properties
* info
  * type `Container-type, like 'MySQL' or 'Noark'`
    * version `Version of container-type`
* [namespace](#namespace) `Namespaces used inside container`

## <a id="namespace"/>[namespace](#namespace) : [dataObject](#dataObject)
Refers to a set of pre-defined objects.
#### Properties
* identifier `Shorthand name used as reference for namespace`
* source `Reference to source`

![Archival](http://www.plantuml.com/plantuml/png/RO_FJiCm38VlUGgpUvgH5OPGDOqBx-6wNXj8ayfn1XBYtUbwuRBB9__HP_btBegYTOwmUnEQmXKZyBSAaeQSTiQ4f2mN90RAIJ4a5cCMf4yS-Ru3NVUUuy1oEi6FCG3mhq9dBU0cyRRPy10InJfmbGYJwb9UdHFyQiQWK-rhORaTuAGDvTbzP9QHaxqMTppi_P5QRydJO5jwzhP_lBJMFnqyxRb_6R1tCnPbSRNWo0xB4WHlVnQtfjvWOwPjr2nhPyolCMTEmrh_0G00)

## <a id="archive"/>[archive](#archive) : [container](#container)
Rotkatalogen for samlingen av filer og dokumenter som gjør opp et arkivuttrekk. Inneholder beskrivelse av selve arkivuttrekket.
#### Items
* [definition](#definition) `Defines the meaning of the objects in the structure.`
* [file](#file) `Files which are part of the archive, as metadata or documentation.`
* [folder](#folder) `Folders which are part of the archive.`
* [process](#process)
* [structureType](#structureType) `Defines how the structure is supposed to be read.`
#### Properties
* info
  * period `Declares the timeperiod for the data in the archive`
    * inboundPeriod `Start-date`
    * outgoingPeriod `End-date`
  * containsScreenedInformation `True or false: Are there metadata in the archive which is screened?`
  * containsBusinessSpesificinformation `True or false: Are there metadata in the archive which is business-specific?`
  * containsDocumentsScheduledForDisposal `True or False: Are there documents in the archive which is scheduled for disposal?`
  * containsDocumentsWhichIsDisposed `True or False: Are there documents in the archive which is disposed?`
  * standards
    * referencedStandard `Reference to standard used to understand how to locate, read and understand the information.`

![Location](http://www.plantuml.com/plantuml/png/TP71Ry8W5CRl_1N4tPOWhhgvBCPuykHfL-FX5LvR71G3r9Wi-z-NGbTP6a-Gx_q-tlU5dG_WGcSq8HSGNr0ZdHsiWA1iEwERpTw1mUsMVXFL1dGL2AGI0koLHdeyDY5S_0VdjGfDLyw5DVniqTNOigldw-MYM8jLmKGX95k9juALBzMA5Q_BGYomV9TGybBRaXlm0HtlFDJ8mL-KYmay1ocDPaA3z-ZdHZxzBJ-TiaGEXNKo4og5MX82JZJgYlIPCLfPBT7zbvH6GjA0RXXBpH97-k5TxCdXajIpj-rKlHaz5ILgPLH0EHrLweRoW6qTcZWSNatnXbRf69T-9ZLkUW3670ENBtz4ZypWoLCzTcNKu2FtVD4JsyIV66-KiMtw7TfN6E4OEHAzF46pXADXr29zHoRcIT1epzJeoB794pzaXwtiZFu5)

## <a id="folder"/>[folder](#folder) : [dataObject](#dataObject)
Filesystem-folder, used for grouping similar types of files.
#### Properties
* folder
  * name `Relative file-path for folder.`
  * size `Size of folder in bytes.`
  * content `Type of content`
    * VALUE = DATAFILES | DOCUMENTATION | DOCUMENTS | REPORTS | OTHER
* info
  * numberOf
    * '.extension' `Number of files recursively in folder, based on extension. All files available with '.*'`

## <a id="dataFolder"/>[dataFolder](#dataFolder) : [folder](#folder)
Folder of data-files, used for grouping similar types of files with data-properties. Enables validating a group of files.
#### Properties
* schemas
  * schema `Connects a validation-file to all files in folder.`
    * fileReference `Reference to the validation-file`

## <a id="file"/>[file](#file) : [dataObject](#dataObject)
File in the archive.
#### Properties
* file
  * name `Relative file-path.`
  * size `Size of file in bytes.`
  * checksum `Contains the algorithm and value of checksum-calculation for file.`
    * algorithm `Checksum-algorithm used for calculation.`
    * value `Calculated value of file.`

## <a id="dataFile"/>[dataFile](#dataFile) : [file](#file)
File with a set of records.
#### Items
* [record](#record)
#### Properties
* definitionReference `Reference to definition-object which contains the description of the file`
* typeReference `Reference to structureType-object which contains how the file is read.`
* info
  * numberOf `Contains a reference to a type of record, and the number of times it occurs in the file.`
    * recordIdentifier `Name of record-object`
    * recordCount `Number of records`

## <a id="jsonFile"/>[jsonFile](#jsonFile) : [dataFile](#dataFile)
Json-file
####

## <a id="xmlFile"/>[xmlFile](#xmlFile) : [dataFile](#dataFile)
Xml-file.
#### Properties
* schemas
  * schema `Connects a validation-file to a xml-file.`
    * fileReference `Reference to the file to validate the xml-file against`

## <a id="delimitedFile"/>[delimitedFile](#delimitedFile) : [dataFile](#dataFile)
File where the records and fields are separated by a delimiter.

## <a id="fixedLengthFile"/>[fixedLengthFile](#fixedLengthFile) : [dataFile](#dataFile)
File where the length of records and fields do not vary.

## <a id="record"/>[record](#record) : [dataObject](#dataObject)
Composed of fields.
#### Items
* field

## <a id="dataRecord"/>[dataRecord](#dataRecord) : [record](#record)
Sub-class for record, adding definition-reference and structureType-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the record.`
* typeReference `Reference to structureType-object which contains how the record is read.`

## <a id="jsonRecord"/>[jsonRecord](#jsonRecord) : [dataRecord](#dataRecord)
TBD

## <a id="xmlRecord"/>[xmlRecord](#xmlRecord) : [dataRecord](#dataRecord)
TBD

## <a id="delimitedRecord"/>[delimitedRecord](#delimitedRecord) : [dataRecord](#dataRecord)
TBD

## <a id="fixedLengthRecord"/>[fixedLengthRecord](#fixedLengthRecord) : [dataRecord](#dataRecord)
TBD

## <a id="key"/>[key](#key) : [dataObject](#dataObject)
Key for record, in the form of primary, foreign and candidate.

## <a id="primaryKey"/>primaryKey : key
..

## <a id="candidateKey"/>candidateKey
..

## <a id="foreignKey"/>foreignKey
..

## <a id="field"/>[field](#field) : [dataObject](#dataObject)
Contains one item of information.

## <a id="dataField"/>[dataField](#dataField) : [field](#field)
Abstract class for field, adding definition-reference and structureType-reference.
#### Properties
* definitionReference `Reference to definition-object which contains the description of the field`
* typeReference `Reference to structureType-object which contains how the field is read.`

## <a id="jsonField"/>[jsonField](#jsonField) : [dataField](#dataField)
TBD

## <a id="xmlField"/>[xmlField](#xmlField) : [dataField](#dataField)
TBD

## <a id="delimitedField"/>[delimitedField](#delimitedField) : [dataField](#dataField)
TBD

## <a id="fixedLengthField"/>[fixedLengthField](#fixedLengthField) : [dataField](#dataField)
TBD
#### Properties
* startPos
* endPos
* 

![Definition](http://www.plantuml.com/plantuml/png/TP11QWCn34NtEeN9iZ0t68OiIZSzXR2_Kp4UsMYSXIczUvCiOZCaI_ttlYnytYjRlMw9zbMqiF7caYXgAt0bftOVNh5izISJ5VOhN-1EduYYKYNhVdBp_7MJiIpkbqYqmY9xkF1qXd158_9PAul2tCSq3TvED0m7E38ttr2KX7x7aHfyjl2UHq4QCHqBZ-UBoSRMlj5UyvWDSj6ttBC62LnnD_eoDqtBuokU_HuDbHxIS6vVdWFeZ-WC3TSj_GC0)

## <a id="definitions"/>[definitions](#definitions) : [dataObject](#dataObject)
Collection of definitions in a container
#### Items
..* [definition](#definition)
#### Properties
..

## <a id="definition"/>[definition](#definition) : [dataObject](#dataObject)

#### Properties
..

## <a id="fileDefinition"/>[fileDefinition](#fileDefinition) : [definition](#definition)
Declaration of how the file is structured
#### Items
* recordDefinitionReference `Reference-object pointing to a record.`
  * definitionReference `Pointer to recordDefinition.`
  * minOccurs `Lower limit of occurence of record in file.`
  * maxOccurs `Upper limit of occurence of record in file.`

## <a id="recordDefinition"/>[recordDefinition](#recordDefinition) : [definition](#definition)
Declaration of how the record is structured.
#### Properties
* ..
* namespaceReference `Reference to prefix + element-name associated with recordDefinition`
* ..
#### Items
* fieldDefinitionReference `Reference-object pointing to a field.`
  * definitionReference `Pointer to fieldDefinition.`
  * minOccurs `Lower limit of occurence for field in record.`
  * maxOccurs `Upper limit of occurence for field in record.`
* recordDefinitionReference `Reference-object pointing to a record.`
  * definitionReference `Pointer to recordDefinition.`
  * minOccurs `Lower limit of occurence of record in record.`
  * maxOccurs `Upper limit of occurence of record in record.`

## <a id="definitionReference"/>[definitionReference](#definitionReference) : [dataObject](#dataObject)
Reference-object pointing to a definition
#### Properties
* definitionReference `Pointer to definition.`

## <a id="fieldDefinitionReference"/>[fieldDefinitionReference](#fieldDefinitionReference) : [definitionReference](#definitionReference)
Reference-object pointing to a fieldDefinition
#### Properties
* minOccurs `Lower limit of occurence of field.`
* maxOccurs `Upper limit of occurence of field.`

## <a id="recordDefinitionReference"/>[recordDefinitionReference](#recordDefinitionReference) : [definitionReference](#definitionReference)
Reference-object pointing to a recordDefinition
#### Properties
* definitionReference `Pointer to recordDefinition`
* minOccurs `Lower limit of occurence of record.`
* maxOccurs `Upper limit of occurence of record.`

## <a id="fieldDefinition"/>[fieldDefinition](#fieldDefinition) : [definition](#definition)
..
#### Properties
* ..
* namespaceReference `Reference to prefix + element-name associated with fieldDefinition`
* ..
#### Items
* [code](#code) `Contains pre-defined code-values for field`

## <a id="code"/>[code](#code) : [dataObject](#dataObject)
Contains pre-defined code-values for field
#### Properties
* description `Meaning behind the value.`
* value `Code-value.`

![Type](http://www.plantuml.com/plantuml/png/TOn1YeH034NtEKLmEU0DH5nvWhb0AEDCOQmgKgc5D7ttBkr64DfLo7l__o4RgPLL82y-959QKNnWsn9ZYhBjppSNrVuZG2Atq1zZyrjXRh3hnXhZliS7-62iCpd6R5gS5UKz1U1YCAf3YZzjYxOt0OvpW6lwyc5N_UpbJYcxgDDjZ-Nju9WukP2D7t0rvyPq-YV0m64ggxm0)

## <a id="types"/>[types](#types) : [dataObject](#dataObject)
Collection of types for a container
#### Items
* [structureType](#structureType)

## <a id="structureType"/>[structureType](#structureType) : [dataObject](#dataObject)
..
#### Items
..
#### Properties
..

## <a id="fileType"/>[fileType](#fileType) : [structureType](#structureType)
Declaration of how the file is read
#### Properties
* charset `Defines the charset used in the file.`
* charDefinitions `Redefined characters are listed here.`

## <a id="structuredFileType"/>[structuredFileType](#structuredFileType) : [fileType](#fileType)
Declaration of how a structured file is read
* name
* version
* formatted

## <a id="flatFileType"/>[flatFileType](#flatFileType) : [fileType](#fileType)
Declaration of how a flat-file is read
#### Properties
* recordSeparator `Specifies character[s] used as record-separator.`
* fieldSeparatingChar `Specifies character[s] used as field-separator.`
* quotingChar `Specifies character[s] used as quotation around complex fields.`

## <a id="recordType"/>[recordType](#recordType) : [structureType](#structureType)
Declaration of how the record is read.
#### Properties
* trimmed `True or false, based on whether all fields in record have removed leading zeros and tailing blanks`

#### Items
..

## <a id="processes"/>[processes](#processes) : [dataObject](#dataObject)
Collection of processes for a container
#### Items
* [process](#process)
#### Properties
..

## <a id="process"/>[process](#process) : [dataObject](#dataObject)
..
#### Items
..
#### Properties
..

# ```Wishlist```
## <a id="database"/>database

## <a id="table"/>table

## <a id="column"/>column
