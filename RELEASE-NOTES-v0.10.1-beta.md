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
  läggs upp.
- **Det sista året kan kortas av.** Ett år från 1 januari till slutet av en
  tidigare månad skapas när du bekräftar att det är året då
  bokföringsskyldigheten upphör (3 kap. 3 §).
- **Byte till kalenderår.** Efter ett brutet räkenskapsår kan nästa år börja
  den 1:a i en månad och sluta 31 december, högst 18 månader. Det skapas när du
  bekräftar att räkenskapsåret läggs om. Om omläggningen kräver Skatteverkets
  tillstånd kontrollerar Grundbok inte.
- **Aktiebolag, och handelsbolag utan fysiska personer som delägare:** ett
  senare år som inte är tolv månader, eller som slutar i en annan månad än året
  före, frågas först. Frågan säger att en omläggning kräver Skatteverkets
  tillstånd (3 kap. 6 §).
- **SIE-import** byter inte längre räkenskapsår om någon verifikation då
  skulle falla bort. Filen nekas i stället, och ingenting sparas.
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
- Ett räkenskapsår som redan finns i Grundbok kan inte förlängas i efterhand.
- Räkenskapsår som redan finns kontrolleras inte på nytt om du ändrar
  företagsformen eller delägarregistret.
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
`aff8aee02913e1d4333cf4699557d61091efd3094fc7185f69b13a2483626fa4`
