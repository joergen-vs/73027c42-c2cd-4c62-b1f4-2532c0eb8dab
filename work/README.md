![](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuShBJqbL22ufAiqkAIs2y5nIqpBpCekpylCW_93AWbG8Aw0elpYrk3YrY0kcGq7N3bazWWcK06j4gBJHrKKOWAGIJS8XDIy5w300)<br>
*Koblingen mellom ulike deler i addml*<p>

![](http://www.plantuml.com/plantuml/png/LP5D3e8m48NtFKKlG4zW28biZ1kZNg09GqHmQZh3mjkBZ7IO7U-Rhp-lDCGny_oQ7AOEV1iv4Z0xYLVe8KSao99FY8yqTHBE2Hb6OgUMhwgwI1QhxhP3LgpM_ypZuiK1IxvndaUUiwGM-W47UYQKVF-yGRukEH7GRvzjXG_rtbSSQbcdGty8GLYn5g9x6jKCzfEWvItLxgNTMbujEz3I1iiD3TARs6VLLsm0k-N_VW40)<br>
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
