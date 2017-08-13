# additionalElements

**Beskrivelse**

```xml
<xs:element name="dataObjects">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:description" minOccurs="0"/>
      <xs:element ref="addml:dataObject" maxOccurs="unbounded"/>
      <xs:element ref="addml:processes" minOccurs="0"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Underelementer
* [description](description.md)
* [dataObject](dataObject.md)
* [processes](processes.md)

## Finnes i
* [dataset](dataset.md)
* [dataObject](dataObject.md)