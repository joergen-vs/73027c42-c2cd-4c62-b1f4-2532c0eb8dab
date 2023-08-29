![](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuShBJqbL22ufAiqkAIs2y5nIqpBpCekpylCW_93AWbG8Aw0elpYrk3YrY0kcGq7N3bazWWcK06j4gBJHrKKOWAGIJS8XDIy5w300)<br>
*Koblingen mellom ulike deler i addml*<p>

![](http://www.plantuml.com/plantuml/png/LP0n3i8m34Ltdo8NQ4w0gWvT40i2BX2fhYWj3hAT0I7k3fM9QhRyv-_eVtUYYRNS5w0yOEYJ9a5LC7d24JcH88UNaJtHDI-3YKCcnLaKtW16pifbri8_sUCuqIItJAOlpmVQwyXPK0GPwag8hVCx75lRsuPX5wEnwbg9-zDP_mVW6gqJPmIevKFJkkOEDpwXvpMX8pwDmzk5EgJXU_SF)<br>
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
