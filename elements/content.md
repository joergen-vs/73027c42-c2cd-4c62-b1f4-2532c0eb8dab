# content

Inneholder informasjon, spesifikt knyttet til arkivuttrekket.

```xml
<xs:element name="content">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:description" minOccurs="0"/>
      <xs:element ref="addml:additionalElements" minOccurs="0"/>
      <xs:element ref="addml:processes" minOccurs="0"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Underelementer
* [description](description.md)
* [additionalElements](additionalElements.md)
* [processes](processes.md)

## Finnes i
* [reference](reference.md)