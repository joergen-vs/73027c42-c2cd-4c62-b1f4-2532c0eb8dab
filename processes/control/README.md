## Kontroller på filnivå
Control_AllFixedLength
> Kontrollerer at oppgitt postlengde på samtlige posttyper er korrekt (kun fast format).

Control_NumberOfRecords
> Teller opp og kontrollerer at antall poster i filen er lik antallet som er oppgitt i egenskapen numberOfRecords i flatFile.

## Kontroller på postnivå
Control_FixedLength
> Kontrollerer om oppgitt postlengde er korrekt (kun for fast format)

Control_NotUsedRecordDef
> Kontrollerer om denne posttypen benyttes i datasettet.

Control_Key
> Kontrollerer at nøkkelen (primary eller alternate) er unik.

Control_ForeignKey
> Kontrollerer fremmednøkler for å sjekke at de går til en faktisk forekomst.

## Kontroller på feltnivå
Control_MinLength
> Kontrollerer om oppgitt minste lengde faktisk er minste lengde i feltet.

Control_MaxLength
> Kontrollerer om oppgitt største lengde faktisk er største lengde ifeltet.

Control_DataFormat
> Kontrollerer om oppgitt dataformat er korrekt.

Control_NotNull
> Kontrollerer om det fines null-verdier i feltet.

Control_Uniqueness
> Kontrollerer om verdiene i feltet er unike.

Control_Codes
> Kontrollerer om definerte koder benyttes og omdet benyttes koder som ikke er definert i kodelisten.