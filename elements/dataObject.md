# dataObject

**Beskrivelse**

```xml
<xs:element name="dataObject">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:description" minOccurs="0"/>
      <xs:element ref="addml:properties" minOccurs="0"/>
      <xs:element ref="addml:dataObjects" minOccurs="0"/>
      <xs:element ref="addml:processes" minOccurs="0"/>
    </xs:sequence>
    <xs:attribute name="name" type="xs:string" use="required"/>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Attributter
*  name: **TODO**

## Underelementer
* [description](description.md)
* [properties](properties.md)
* [dataObjects](dataObjects.md)
* [processes](processes.md)

## Finnes i
* [dataObjects](dataObjects.md)