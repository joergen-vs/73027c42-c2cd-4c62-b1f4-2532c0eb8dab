# addml

addml er toppnivået i strukturen. Dette elementet skal eksistere en og kun en gang i henhold til reglene for XML

```xml
<xs:element name="addml">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:dataset" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="name" type="xs:string"/>
  </xs:complexType>
</xs:element>
```

## Datatype
rotelement

## Attributter
*  name: **TODO**

## Underelementer
* [dataset](dataset.md)