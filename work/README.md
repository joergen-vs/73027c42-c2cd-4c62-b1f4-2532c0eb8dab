![](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuShBJqbL22ufAiqkAIs2y5nIqpBpCekpylCW_93AWbG8Aw0elpYrk3YrY0kcGq7N3bazWWcK06j4gBJHrKKOWAGIJS8XDIy5w300)<br>
*Koblingen mellom ulike deler i addml*<p>

![](//www.plantuml.com/plantuml/png/TP113e8m44NtFKKlG4zW28biZ1kZNg09GqHWQZhJXRStE9QX9ExuRrxR-JJ4FdAQ9uEX0zjwzWJCHk8LUeWU2QBa4-8ZJ9s4Sq26aTYePQkgpj8Egsxo8r-irk_DOq3s0wxvnZ6DdAAa5le11te6b7n_lq2-BZ4Gq79FFc5TlVKLkrhEwT0Ud1EMhONedNjL1zk9q_8b_TDT9REsNWRQkT1bvmtHDKgilx01xD8yVG00)<br>
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
