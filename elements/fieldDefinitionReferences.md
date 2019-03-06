# fieldDefinitionReferences

**Beskrivelse**

```xml
<xs:element name="fieldDefinitionReferences">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:fieldDefinitionReference" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>
  <xs:unique name="uniqueFieldReference">
    <xs:selector xpath="addml:fieldDefinitionReference"/>
    <xs:field xpath="@name"/>
  </xs:unique>
</xs:element>
```

## Datatype
element


## Underelementer
* [fieldDefinitionReference](fieldDefinitionReference.md)

## Finnes i
* [fieldDefinitions](fieldDefinitions.md)
* [fieldParts](fieldParts.md)