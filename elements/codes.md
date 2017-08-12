# codes

Liste over definerte koder som er tillatt for et felt.

```xml
<xs:element name="codes">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:code" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Underelementer
* [code](code.md)

## Finnes i
* [fieldDefinition](fieldDefinition.md)