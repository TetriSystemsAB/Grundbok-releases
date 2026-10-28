# Grundbok — beta

Grundbok är ett svenskt bokföringsprogram för småföretag (enskild firma, AB, HB):
löpande bokföring med rättelseverifikationer, fakturor, moms (eSKD), deklaration
(INK2/NE/INK4 med SRU-export), SIE 4 och tolkning av kvitton i PDF. Allt körs
**lokalt på din dator**. Ingen molnlagring och inga konton hos oss. Grundbok
skickar ingenting över nätet – filer lämnar datorn bara när du själv skickar
dem.

Grundbok är byggd efter bokföringslagen och BFN:s allmänna råd (BFNAR 2013:2).
Ingen myndighet godkänner bokföringsprogram i Sverige. Företaget ansvarar för
sin egen bokföring.

Grundbok ges ut av Tetri Systems AB. Betan är gratis.

## Ladda ner

| Plattform | Fil | Status |
|---|---|---|
| macOS 26 (Tahoe) eller senare, Apple Silicon (M1 eller senare) | **Grundbok-0.10.0-beta.dmg** under [Releases](../../releases) | Beta |
| macOS (Intel) | — | Kommer senare |
| Windows | — | Kommer senare |

Appen kräver macOS 26 (Tahoe) eller senare. Vilken version du har ser du under
Apple-menyn → **Om den här datorn**.

Appen är signerad med Developer ID (Tetri Systems AB) och notariserad av Apple.

Kontrollsumma (SHA-256) finns i release-texten. Vill du kontrollera filen kan
du skriva det här i Terminal. Svaret ska vara samma som i release-texten.

```
shasum -a 256 ~/Downloads/Grundbok-0.10.0-beta.dmg
```

## Installera

1. Öppna **Grundbok-0.10.0-beta.dmg** (dubbelklicka på filen i Hämtade filer).
2. Dra **Grundbok** till **Applications** (mappen Program) i fönstret som öppnas.
3. Öppna Grundbok från **Program**, inte direkt från dmg-fönstret.
4. Första gången kan macOS fråga: *”Grundbok” är en app som hämtats från
   internet. Är du säker på att du vill öppna den?* Klicka **Öppna**.
5. Mata ut dmg-filen när du är klar (⏏ bredvid Grundbok i Finders sidofält).

## Uppgradera från 0.9.0-beta

Läs det här först:

- **Ta en säkerhetskopia innan du uppgraderar.** Öppna 0.9.0-beta och gå till
  Inställningar → Säkerhetskopiering. Spara kopian utanför datorn, till
  exempel på en extern disk.
- **Databasen uppgraderas första gången 0.10.0-beta startar. Det går bara åt
  ett håll.** Du kan inte gå tillbaka till 0.9.0-beta med samma databas.
- **Säkerhetskopior från 0.9.0-beta** saknar fingeravtryck, så det går inte
  att se om de har ändrats. De återställs bara när du skriver ÅTERSTÄLL.
  Företaget förblir då märkt som återställt från en okontrollerad kopia.
- **Första gången du bokför** frågar Grundbok efter ditt namn. Det sparas på
  varje verifikation. Du kan också ange det under Inställningar → Bokförare.
- Verifikationer från 0.9.0-beta saknar bokförarens namn – det sparades inte
  då. Fakturor från 0.9.0-beta har ingen sparad PDF. Grundbok återskapar den
  och säger det, och den kan skilja sig från den du skickade. Spara den PDF du
  skickade till kunden.

Så här gör du:

1. Ta säkerhetskopian (se ovan).
2. Avsluta Grundbok (⌘Q).
3. Installera 0.10.0-beta enligt stegen ovan. Välj **Ersätt** när macOS frågar.
4. Öppna Grundbok. Bokföringen finns kvar – den ligger i din användarkatalog,
   inte i appen.

## Kom igång

1. Öppna Grundbok.
2. Skapa ditt konto – användarnamn, lösenord och en **säkerhetsfråga**.
3. **Skriv upp svaret på säkerhetsfrågan.** Den är den enda återställningen –
   det finns ingen e-poståterställning, eftersom det inte finns någon server.
4. Lägg upp ditt företag.
5. Ange ditt namn under Inställningar → Bokförare. Annars frågar Grundbok
   första gången du bokför.
6. Har du bokfört tidigare? Läs in din SIE-fil under Inställningar → SIE-import.
7. Ta en säkerhetskopia då och då: Inställningar → Säkerhetskopiering. Spara
   den utanför datorn.

## Känt i betan

Vi säger hellre för mycket än för lite:

- **SRU-filerna** (deklarationsexporten) bygger på Skatteverkets
  fältkodstabeller. Stäm av mot Skatteverkets aktuella fältnamnstabell innan
  du lämnar in skarpt, och rapportera gärna avvikelser till oss. Stäm också av
  momsdeklarationens rutor första gången.
- **Automatisk bankkoppling är en planerad funktion.** Knappen *Anslut bank*
  visar "Planerad funktion" och gör ingenting. Import av kontoutdrag från fil
  (camt-XML, CSV, Excel) fungerar.
- **Fotograferade och skannade kvitton tolkas inte** i den här versionen –
  textigenkänningen ingår inte i appen. Du kan ändå bifoga bilden och bokföra
  för hand. PDF:er med textlager tolkas.
- **Bankfiler:** CSV och Excel känns igen från Nordea Business och SEB.
  Kontoutdrag i camt-XML går att läsa från andra banker. En CSV-fil i en annan
  teckenkodning än UTF-8 avvisas – exportera den på nytt utan att öppna den i
  Excel. En camt-fil i ISO-8859-1 kan förvanska å/ä/ö i motpartsnamn.
  Beloppen påverkas inte.
- **Nordea-CSV:** kortköp och Swish läses ur de vanliga raderna och är ännu
  inte prövade mot större exporter. Granska förslagen innan du bokför (det ska
  du alltid göra).
- **Kontoutdragsfilen sparas inte automatiskt.** Bifoga den till
  verifikationen om du behöver spara den.
- **Ett felaktigt bifogat underlag kan inte tas bort.** Rätta verifikationen
  och bokför om med rätt fil.
- **Databasen är okrypterad på disk.** Den ligger i din användarkatalog och
  skyddas av din inloggning på datorn. Inloggningen i Grundbok är en spärr,
  ingen kryptering. Kryptering i vila är planerad.
- **Kontrollkedjan är ingen signatur.** Den gör ändringar utanför Grundbok
  synliga. Men den som är beslutsam kan skriva om databasfilen och räkna om
  kedjan. Spara rapporter och SIE-filer utanför datorn, så går det att jämföra.
- **Registreringstiden** tas från datorns klocka. Se till att klockan går rätt.
- **Systemdokumentationen och behandlingshistoriken** är på svenska, även när
  appen visas på engelska.
- **Intel-Mac och Windows** kommer senare.

## Support och synpunkter

Mejla **Support@tetrisystems.eu** — betan blir bättre av varje rapport.
Ange gärna version (visas under Beta & support i appen).

---

© 2026 Tetri Systems AB. Alla rättigheter förbehållna.
Grundbok är proprietär programvara; betan är gratis att använda.
