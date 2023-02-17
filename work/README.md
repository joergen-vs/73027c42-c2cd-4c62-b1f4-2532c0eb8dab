![](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuShBJqbL22ufAiqkAIs2y5nIqpBpCekpylCW_93AWbG8Aw0elpYrk3YrY0kcGq7N3bazWWcK06j4gBJHrKKOWAGIJS8XDIy5w300)<br>
*Koblingen mellom ulike deler i addml*<p>

![](http://www.plantuml.com/plantuml/png/NP1H3e8m38RVTufTW9t0419vCRuOzG9BA161pgpTWxTNhD3g6__NhwnjGnmpbtboc3hmRUH8mEmadg67794WIpuWtjBKIJWcP1Y9dLg-gkfD-iMgk_MH3rRh--R-xSK1jtpXN4OkML8B_O03tHDAlZuV85-dd0Xe-S_QuKDjVSMXbZuj-bq8mZPh8VhFFrKBjX9qUKljxkjsCeLQzYYMQyDIq6DONGQtn0vkiTws0UpAFBq0)<br>
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
