
Inneholder informasjon, spesifikt knyttet til arkivuttrekket.

```xml
<flatFiles>
  <flatFile name="Unikt navn for filobjekt" definitionReference="Referanse til fildefinisjon">
    <properties>
      <property name="fileName">
		<value>Relativ filsti</value>
	  </property>
      <property name="numberOfRecords">
		<value>Antall poster i filen</value>
	  </property>
      <property name="checksum">
		<properties>
		  <property name="algorithm">
			<value>Algoritme for produksjon av sjekksum</value>
		  </property>
		  <property name="value">
			<value>Sjekksum for fil, produsert med algoritme</value>
		  </property>
		</properties>
	  </property>
    </properties>
  </flatFile>
  <flatFileDefinitions>
	<flatFileDefinition name="Unikt navn for fildefinisjon" typeReference="Referanse til type">
	  <recordDefinitionFieldIdentifier>Unik nøkkel for post</recordDefinitionFieldIdentifier>
	    <recordDefinitions>
	      <recordDefinition name="Unikt navn for postdefinisjon">
			<keys>
			  <key name="Unikt navn for nøkkel">
			    <primaryKey />
				<fieldDefinitionReferences>
				  <fieldDefinitionReference name="Navn på feltdefinisjon" />
				</fieldDefinitionReferences>
			  </key>
			</keys>
		  <fieldDefinitions>
		    <fieldDefinition name="Unikt navn for feltdefinisjon" typeReference="Referanse til type">
			  <description>Beskrivende tekst av felt</description>
			</fieldDefinition>
		  </fieldDefinitions>
	    </recordDefinition>
	  </recordDefinitions>
	</flatFileDefinition>
  </flatFileDefinitions>
  <structureTypes>
    <flatFileTypes>
	  <flatFileType name="Unikt navn for type">
	    <charset>Tegnsettet som brukes i filen</charset>
		<delimFileFormat>
		  <recordSeparator>Post-skilletegn</recordSeparator>
		  <fieldSeparatingChar>Felt-skilletegn</fieldSeparatingChar>
		  <quotingChar>Plasseres rundt felt som inneholder post-eller felt-skilletegn</quotingChar>
		</delimFileFormat>
	  </flatFileType>
	</flatFileTypes>
	<fieldTypes>
	  <fieldType name="Unikt navn for type">
	    <dataType>Data-type for felt</dataType>
	  </fieldType>
	</fieldTypes>
  </structureTypes>
</flatFiles>
```