# Grundbok 0.10.1-beta

En rättelseversion av 0.10.0-beta, med en ny inställning för momsen.

Kräver macOS 26 (Tahoe) eller senare och en Mac med Apple Silicon (M1 eller
senare).

## Nytt

- **När momsdeklarationen ska lämnas.** Under Inställningar → Företag finns
  nu valet "Momsdeklaration lämnas". Välj det som står på ditt
  registreringsbesked från Skatteverket. Datumet under Rapporter → Moms och i
  momsrapportens PDF följer valet. Standard är "Enligt Grundboks beräkning",
  som förut.

## Rättat

- **Första räkenskapsåret för en ny enskild firma** kan vara upp till 18
  månader. Det kan börja vilken dag som helst och slutar den 31 december samma
  år eller året efter (bokföringslagen 3 kap. 1 och 3 §§). En firma som startar
  i oktober kan alltså ha sitt första år till och med 31 december nästa år.
  Ett sådant år läses också in som det är från en SIE-fil.
- **Handelsbolag med en fysisk person som delägare** har kalenderår, precis
  som en enskild firma (3 kap. 1 §). Grundbok ser det i delägarregistret
  (Inställningar → Delägare). Har handelsbolaget inga delägare registrerade
  frågar Grundbok innan ett brutet räkenskapsår skapas, också när företaget
  läggs upp. Grundbok frågar på samma sätt om ingen delägare är en fysisk
  person men någon har ett organisationsnummer som börjar med 9. Den serien
  har handelsbolag och kommanditbolag, och Grundbok ser inte vilka som äger
  dem.
- **Det sista året kan kortas av.** Ett år från 1 januari till slutet av en
  tidigare månad skapas när du bekräftar att det är året då
  bokföringsskyldigheten upphör (3 kap. 3 §). För en enskild firma och ett
  handelsbolag med en fysisk person som delägare skapas ett senare år sedan
  bara när du bekräftar att bokföringsskyldigheten har börjat igen. Det året
  följer reglerna för ett första år.
- **Byte från brutet räkenskapsår till kalenderår.** Nästa år börjar dagen
  efter att det brutna året slutar och slutar 31 december, högst 18 månader.
  Det skapas när du bekräftar att räkenskapsåret läggs om. Ett sådant byte
  behöver inte Skatteverkets tillstånd (3 kap. 6 § punkt 1). För en enskild
  firma och ett handelsbolag med en fysisk person som delägare säger Grundbok
  också att Skatteverket kan förelägga företaget att byta, vid vite (7 §).
- **Andra byten av räkenskapsår kräver tillstånd.** För aktiebolag, och
  handelsbolag utan fysiska personer som delägare, frågas ett senare år först
  om det inte är tolv månader eller slutar i en annan månad än året före.
  Frågan säger att bytet bara får göras med Skatteverkets tillstånd (3 kap.
  6 §). Undantaget är ett byte till gemensamt räkenskapsår enligt 4 och 5 §§
  (6 § punkt 2).
- **Inga glapp och inga överlapp.** Ett år som byter räkenskapsår måste börja
  dagen efter att året före slutar. Exemplen Grundbok visar börjar den dagen
  och krockar aldrig med ett år som redan finns.
- **SIE-import** byter inte längre räkenskapsår om någon verifikation då
  skulle falla bort. Filen nekas i stället, och ingenting sparas. När Grundbok
  rättar filens år till ett kalenderår ändras aldrig ett räkenskapsår som
  redan finns. Gäller filen ett år efter ett avkortat sista år, eller ett
  brutet år i ett handelsbolag med en delägare vars nummer börjar med 9,
  frågar Grundbok först, som när året skapas för hand.
- **Text klipps inte längre av i Verifikationer.** Märkningar som "rättelse"
  och antal underlag syns alltid. Belopp, knappar och fält får plats även i
  smala fönster. En lång verifikationstext slutar med … i listan, men hela
  texten visas när du håller pekaren över raden eller öppnar den.
- **Toppraden ryms på en rad** när fönstret är ungefär 860 punkter brett
  eller mer, på svenska och engelska. Ledtexten i fältet för var underlaget
  finns klipps inte längre i smala fönster.

## Bra att veta

- Med valet "Samma dag som inkomstdeklarationen" visar momsrapporten vilket
  datum Grundbok räknar med. Jämför det med beskedet från Skatteverket.
- Grundbok kan inte se om Skatteverket har gett tillstånd att byta
  räkenskapsår. Det är ditt ansvar.
- Ett räkenskapsår som redan finns i Grundbok kan inte förlängas i efterhand.
- Räkenskapsår som redan finns kontrolleras inte på nytt om du ändrar
  företagsformen eller delägarregistret.
- För en enskild firma eller ett handelsbolag med en fysisk person som
  delägare kan rutan för nytt räkenskapsår ibland föreslå datum som Grundbok
  inte godtar. Beskedet säger då vad som gäller, ofta med exempel på år som
  går att skapa.
- En SIE-fil kan ersätta ett tomt räkenskapsår som överlappar filens år.
  Grundbok säger det efter inläsningen, inte före.
- För en enskild firma eller ett handelsbolag med en fysisk person som
  delägare kan Grundbok, efter ett avkortat sista år, neka en SIE-fil som bara
  gäller en del av ett år, till exempel ett momskvartal.
- I ett smalt fönster (under ungefär 1 000 punkter) kan företagsnamnet i
  toppraden kortas av så att nästan inget syns. Hela namnet syns när du byter
  företag.

## Installera

1. Öppna **Grundbok-0.10.1-beta.dmg** (dubbelklicka på filen i Hämtade filer).
2. Dra **Grundbok** till **Applications** (mappen Program) i fönstret som öppnas.
3. Öppna Grundbok från **Program**, inte direkt från dmg-fönstret.
4. Första gången kan macOS fråga om du vill öppna en app som hämtats från
   internet. Klicka **Öppna**.
5. Mata ut dmg-filen när du är klar (⏏ bredvid Grundbok i Finders sidofält).

## Uppgradera från 0.10.0-beta

Samma databas. Första gången 0.10.1-beta startar lägger Grundbok till den nya
momsinställningen. Den står då på "Enligt Grundboks beräkning", som ger samma
datum som förut.

1. Avsluta Grundbok (⌘Q).
2. Installera 0.10.1-beta enligt stegen ovan. Välj **Ersätt** när macOS frågar.
3. Öppna Grundbok. Bokföringen finns kvar – den ligger i din användarkatalog,
   inte i appen.

Ta gärna en säkerhetskopia först, som alltid (Inställningar →
Säkerhetskopiering).

## Uppgradera från 0.9.0-beta

Läs "Viktigt vid uppgradering" i release-texten för 0.10.0-beta först.
Databasen uppgraderas första gången den nya versionen startar, och det går
bara åt ett håll.

## Kontrollsumma

SHA-256 för Grundbok-0.10.1-beta.dmg:
`5a5f2a0e69c50fc1e8a972a692cd82853ff928d4c2d48f400643af7e8a3341f9`
