# reference

addml er toppnivået i strukturen. Dette elementet skal eksistere en og kun en gang i henhold til reglene for XML

```xml
<xs:element name="reference">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:context" minOccurs="0"/>
      <xs:element ref="addml:content" minOccurs="0"/>
    </xs:sequence>
    <xs:attribute name="name" type="xs:string"/>
  </xs:complexType>
</xs:element>
```

## Datatype
element

## Attributter
*  name: **TODO**

## Underelementer
* [context](context.md)
* [content](content.md)

## Finnes i
* [dataset](dataset.md)