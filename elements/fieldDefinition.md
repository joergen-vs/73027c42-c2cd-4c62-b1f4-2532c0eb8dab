# fieldDefinition

**Beskrivelse**

```xml
<xs:element name="fieldDefinition">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:description" minOccurs="0"/>
      <xs:element ref="addml:properties" minOccurs="0"/>
      <xs:element ref="addml:startPos" minOccurs="0"/>
      <xs:element ref="addml:endPos" minOccurs="0"/>
      <xs:element ref="addml:fixedLength" minOccurs="0"/>
      <xs:element ref="addml:minLength" minOccurs="0"/>
      <xs:element ref="addml:maxLength" minOccurs="0"/>
      <xs:element ref="addml:unique" minOccurs="0"/>
      <xs:element ref="addml:notNull" minOccurs="0"/>
      <xs:element ref="addml:fieldParts" minOccurs="0"/>
      <xs:element ref="addml:codes" minOccurs="0"/>
    </xs:sequence>
    <xs:attribute name="name" type="xs:string" use="required"/>
    <xs:attribute name="typeReference" type="xs:string" use="required"/>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Attributter
*  name: **TODO**
*  typeReference: **TODO**


## Underelementer
* [description](description.md)
* [properties](properties.md)
* [startPos](startPos.md)
* [endPos](endPos.md)
* [fixedLength](fixedLength.md)
* [minLength](minLength.md)
* [maxLength](maxLength.md)
* [unique](unique.md)
* [notNull](notNull.md)
* [fieldParts](fieldParts.md)
* [codes](codes.md)

## Finnes i
* [fieldDefinitions](fieldDefinitions.md)
* [fieldParts](fieldParts.md)