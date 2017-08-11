# additionalElements

**Beskrivelse**

```xml
<xs:element name="additionalElements">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:description" minOccurs="0"/>
      <xs:element ref="addml:additionalElement" maxOccurs="unbounded"/>
      <xs:element ref="addml:processes" minOccurs="0"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Attributter
Ingen

## Underelementer
* [description](description.md)
* [additionalElement](additionalElement.md)
* [processes](processes.md)

## Finnes i
* [context](context.md)
* [content](content.md)
* [additionalElement](additionalElement.md)