# delimFileFormat

**Beeskrivelse**

```xml
<xs:element name="delimFileFormat">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:recordSeparator"/>
      <xs:element ref="addml:fieldSeparatingChar"/>
      <xs:element ref="addml:quotingChar" minOccurs="0"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Underelementer
* [recordSeparator](recordSeparator.md)
* [fieldSeparatingChar](fieldSeparatingChar.md)
* [quotingChar](quotingChar.md)

## Finnes i
* [flatFileType](flatFileType.md)