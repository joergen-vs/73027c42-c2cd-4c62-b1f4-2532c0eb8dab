# dataset

dataset er hovednivået i beskrivelsen. Dette tilsvarer et arkivuttrekk. Imidlertid kan en og samme beskrivelse også inneholde flere dataset. Dette for at det skal være mulig å samle beskrivelser når de skal benyttes sammen, for eksempel i en brukssituasjon.

```xml
<xs:element name="dataset">
  <xs:complexType>
    <xs:sequence>
      <xs:element ref="addml:description" minOccurs="0"/>
      <xs:element ref="addml:reference" minOccurs="0"/>
      <xs:element ref="addml:flatFiles" minOccurs="0"/>
      <xs:element ref="addml:dataObjects" minOccurs="0"/>
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
* [description](description.md)
* [reference](reference.md)
* [flatfiles](flatFiles.md)
* [dataObjects](dataObjects.md)

## Finnes i
* [dataset](dataset.md)