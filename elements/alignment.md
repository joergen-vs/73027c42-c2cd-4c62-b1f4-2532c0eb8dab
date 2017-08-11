# alignment

```xml
<xs:element name="alignment" type="xs:string"/>
```

Justering bør være høyrestilt, men andre varianter aksepteres. Eventuelle blanke tegn fjernes under behandlingen. Mulige varianter er høyre, venstre og midt. Dersom justeringen er høyrestilt, kan taggen sløyfes. Dersom justering ikke er med, forventes at feltet er høyrestilt.

Eksempel:
```xml
<alignment>right</alignment> 
```

## Verdier
* left
* center
* right

## Datatype
tekst-streng

## Finnes i
* [fieldType](fieldType.md)