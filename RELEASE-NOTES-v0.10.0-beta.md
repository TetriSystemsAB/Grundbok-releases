# Grundbok v0.10.0-beta

Grundbok 0.10.0-beta är byggd efter bokföringslagen och BFN:s allmänna råd
(BFNAR 2013:2). Appen är nu signerad och notariserad av Apple. Den kräver
macOS 26 (Tahoe) eller senare och en Mac med Apple Silicon (M1 eller senare).
Intel-Mac och Windows kommer senare.

Ingen myndighet godkänner bokföringsprogram i Sverige. Företaget ansvarar för
sin egen bokföring.

**Uppgraderar du från 0.9.0-beta? Läs "Viktigt vid uppgradering" först.**

## Nytt

### Det bokförda står kvar
- Som tidigare kan det bokförda inte ändras eller tas bort i Grundbok. Ett fel
  rättas med en ny verifikation (rättelse).
- Varje verifikation får registreringstid och bokförarens namn när den sparas.
  Namnet anger du en gång (Inställningar → Bokförare).
- Stängda perioder: när du skapar momsdeklarationen stängs perioden. Du kan
  också stänga den själv (*Stäng perioden*). Sedan går det inte att bokföra i
  den, utom bokslutsposter på årets sista dag. En sen händelse bokförs i en
  öppen period.

### Underlag och fakturor
- Kvitton och fakturor du bifogar sparas oförändrade, med kontrollsumma
  (SHA-256), tid och namn. De kan inte ändras eller tas bort i Grundbok.
- En utfärdad faktura sparas som PDF när den skapas. Den byggs aldrig om – en
  ny adress eller ett nytt bankgiro ändrar inte en skickad faktura.

### Historik, dokumentation och kontroll
- Behandlingshistorik: en logg över ändringar som påverkar bokföringen, till
  exempel konton, momskoder, låsta år och säkerhetskopior.
- Systemdokumentation i appen, med företagets egna uppgifter.
- Båda finns under Inställningar → Systemdokumentation och
  behandlingshistorik, och kan laddas ner som PDF.
- Kontrollkedja: vid varje start kontrollerar Grundbok att inget bokfört har
  ändrats utanför appen. Hittar den något visas en varning.

### Säkerhetskopior och arkiv
- Återställningen kontrollerar kopian först. En kopia som har skadats eller
  ändrats av misstag, eller som inte går ihop, återställs inte.
  Fingeravtrycket är ingen signatur.
- Hela arkivet: en zip med det som ska sparas i sju år – SIE, rapporter som
  PDF, underlag, fakturor, momsdeklarationer, historik och
  systemdokumentation, med kontrollsummor. Filerna går att öppna utan
  Grundbok (Inställningar → Säkerhetskopiering).
- Ett företag med bokföring kan inte raderas förrän bevarandetiden har gått ut:
  till och med det sjunde året efter det kalenderår då räkenskapsåret slutade.

### Räkenskapsår och ingående balans
- Nya räkenskapsår följer reglerna: högst 18 månader, slutar på sista dagen i
  en månad, kalenderår för enskild firma. Ett avvikande år skapas bara när du
  bekräftar det.
- Ingående balans jämförs med förra årets utgående. Är förra året låst måste
  de stämma.

### Gränssnitt
- Språkflaggor (svenska/engelska) bredvid företagsnamnet.
- Många engelska texter rättade.
- *Anslut bank* visar nu "Planerad funktion". Automatisk bankkoppling finns
  inte än. Import av kontoutdrag från fil fungerar.

### Installation
- Appen är signerad med Developer ID (Tetri Systems AB) och notariserad av
  Apple. Se README för hur du installerar.

## Viktigt vid uppgradering

- **Ta en säkerhetskopia innan du uppgraderar:** i 0.9.0-beta,
  Inställningar → Säkerhetskopiering. Spara kopian utanför datorn.
- **Databasen uppgraderas första gången 0.10.0-beta startar. Det går bara åt
  ett håll.** Du kan inte gå tillbaka till 0.9.0-beta med samma databas.
- **Säkerhetskopior från 0.9.0-beta** återställs bara när du skriver
  ÅTERSTÄLL. Företaget förblir då märkt som återställt från en okontrollerad
  kopia.
- **Första gången du bokför** frågar Grundbok efter ditt namn.
- Verifikationer från 0.9.0-beta saknar bokförarens namn. Fakturor från
  0.9.0-beta har ingen sparad PDF – den återskapas och kan skilja sig från den
  du skickade. Spara den du skickade.

## Känt i betan

Se README-avsnittet "Känt i betan". Kortversionen:

- Appen kräver macOS 26 (Tahoe) eller senare.
- Fotograferade och skannade kvitton tolkas inte – textigenkänningen ingår
  inte i appen. PDF:er med textlager tolkas.
- Stäm av SRU-fältkoder och momsrutor mot Skatteverket före skarp inlämning.
- Automatisk bankkoppling är en planerad funktion. Filimport fungerar.
- Granska bankimportens förslag innan du bokför.
- Databasen är okrypterad på disk.
- Kontrollkedjan är ingen signatur. Spara rapporter och SIE-filer utanför
  datorn.
- Ta säkerhetskopior, och skriv upp svaret på din säkerhetsfråga (enda
  återställningen).

Kontrollsumma (SHA-256) för Grundbok-0.10.0-beta.dmg:
`d8140c0cc78dbfbfca7c1b8bd75c202cef4f15752774ec3ea394b784420e2a1b`
