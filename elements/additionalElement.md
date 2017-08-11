# additionalElement

**Beskrivelse**

```xml
<xs:element name="additionalElement">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:value" minOccurs="0"/>
      <xs:element ref="addml:properties" minOccurs="0"/>
      <xs:element ref="addml:additionalElements" minOccurs="0"/>
      <xs:element ref="addml:processes" minOccurs="0"/>
    </xs:sequence>
    <xs:attribute name="name" type="xs:string" use="required"/>
    <xs:attribute name="dataType" type="xs:string"/>
    <xs:attribute name="format" type="xs:string"/>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Attributter
*  name: **TODO**
*  dataType: **TODO**
*  format: **TODO**

## Underelementer
* [value](value.md)
* [properties](properties.md)
* [additionalElements](additionalElements.md)
* [processes](processes.md)

## Finnes i
* [additionalElements](additionalElements.md)