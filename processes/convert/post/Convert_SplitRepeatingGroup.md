## Kontroller på dataset og filnivå
Convert_Charset
> Utfører konvertering fra ett tegnsett til et annet.Som parameter angis det nye tegnsettet.

Convert_Format
> Utfører konvertering fra ett filformat til et annet.Som parameter angis det nye formatet.

Convert_RecordSeparator
> Utfører konvertering fra ett postskille til et annet.Som parameter angis det nye postskillet.

Convert_PreserveStructure
> Utfører konvertering ved å beholde filstrukturen som den var. Den vil altså beholde filen som en fil selv om det skulle være flere posttyper, hvor det vil være default å splitte disse. Den vil også beholde tegnsettet og feltene slik de er, selv om noen i utgangspunktet skulle vært pakketutog konvertert til et gyldig tegnsett.Prosessen har ingen parametre.

## Kontroller på postnivå
Convert_AddKeyFields
> Prosessen legger på nøkkelfelt ved splitting på flere posttyper. Som parametre angis feltene som skal legges på med deres innbyrdes rekkefølge, samt hvor de skal plasseres i posttypen.

Convert_SplitRepeatingGroup
> Splitter en posttype med repeterende gruppe opp i en fil med hoveddelen av posten og en fil med den repeterende gruppen med nøkkelfelt.Som parametre angis nøkkelfeltene som skal legges på.

## Kontroller på feltnivå
Convert_Dataformat
> Konvertering av verdien i et felt fra en datatype til en annen. Som parameter angis den nye datatypen.

Convert_PreservePacked
> Konvertering hvor dette feltet beholdes i pakket form.Prosessen har ingen parametre.