## Kontroller p� dataset og filniv�
Convert_Charset
> Utf�rer konvertering fra ett tegnsett til et annet.Som parameter angis det nye tegnsettet.

Convert_Format
> Utf�rer konvertering fra ett filformat til et annet.Som parameter angis det nye formatet.

Convert_RecordSeparator
> Utf�rer konvertering fra ett postskille til et annet.Som parameter angis det nye postskillet.

Convert_PreserveStructure
> Utf�rer konvertering ved � beholde filstrukturen som den var. Den vil alts� beholde filen som en fil selv om det skulle v�re flere posttyper, hvor det vil v�re default � splitte disse. Den vil ogs� beholde tegnsettet og feltene slik de er, selv om noen i utgangspunktet skulle v�rt pakketutog konvertert til et gyldig tegnsett.Prosessen har ingen parametre.

## Kontroller p� postniv�
Convert_AddKeyFields
> Prosessen legger p� n�kkelfelt ved splitting p� flere posttyper. Som parametre angis feltene som skal legges p� med deres innbyrdes rekkef�lge, samt hvor de skal plasseres i posttypen.

Convert_SplitRepeatingGroup
> Splitter en posttype med repeterende gruppe opp i en fil med hoveddelen av posten og en fil med den repeterende gruppen med n�kkelfelt.Som parametre angis n�kkelfeltene som skal legges p�.

## Kontroller p� feltniv�
Convert_Dataformat
> Konvertering av verdien i et felt fra en datatype til en annen. Som parameter angis den nye datatypen.

Convert_PreservePacked
> Konvertering hvor dette feltet beholdes i pakket form.Prosessen har ingen parametre.