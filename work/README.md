![](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuShBJqbL22ufAiqkAIs2y5nIqpBpCekpylCW_93AWbG8Aw0elpYrk3YrY0kcGq7N3bazWWcK06j4gBJHrKKOWAGIJS8XDIy5w300)<br>
*Koblingen mellom ulike deler i addml*<p>

![](http://www.plantuml.com/plantuml/png/LP313S8m34NlcI8BX0bGLObU41S4B12fhYXj7HGx1xP7nQIkR_dFBudjbZXcBiliCFNWkyYHWDb9lC40EI91bdn6VAQvbt19o30HExLy2CqcMQowgv_yi5h_Fqy9EOwuvJldCd79aZeOHXpfbL3ou_C6ELrp8g3rdNh3XsRlAmwDtDEYFuOWh5ehqJUDQWhxoa67jrHdhzD95shPWWwjk7PjaNPYrwfRR07xiinV)<br>
*Foreslått endring*<p>

- Løsrivelse av struktur fra definisjon
- Struktur legger opp til utvidbare elementer, hvor dagens er reflektert i fil-post-felt. Andre er mappe, gruppe, kode og attributt.
    - Mappe brukes til å deklarere samling av dokumenter av en eller annen type, og kan selv utvides med datamappe, hvor man validerer innholdet opp mot struktur (alle filer i mappe valideres mot A)
    - gruppe brukes til samlenivå eller under-grupperinger av post-informasjon. eks. siard; table (gruppe), row (post), cell (felt)
    - Kode er koblingen kode-verdi brukt i felt, mot en definisjon
    - Attributt, fordi elementer knyttet til xml er under arbeid..
- Typer i struktur kan endres på nivåer, så strukturert informasjon inne i annen type kan beskrives. (json-kode i xml, fastlengde adresse-felt i tegnseparert, o.l.)
- Dokumentasjon av typer, så man kan skjønne hvordan f.eks. CSV eller TSV skal leses
- Definisjon er type-løs, ren dokumentasjon
    - Kobling mot ekstern eller interne dokumenter (anyuri)
    - Vil dokumentere alt fra "dette feltet er brukt til"
- Container som samlenivå, spenner over uttrekk, siard, database m.m.