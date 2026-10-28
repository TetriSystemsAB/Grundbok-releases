# Grundbok v0.9.0-beta

Första publika betan. macOS (Apple Silicon) — Intel-Mac och Windows kommer
inom kort.

**Osignerad app:** 0.9.0-beta var osignerad. Från 0.10.0-beta är appen
signerad och notariserad av Apple. Se README för hur du installerar.

## I den här versionen

- Löpande bokföring med append-only-verifikationer och rättelsekedja
- Likviditetsgraf på översikten: bank och kassa, snabbt likvida och bundna
  tillgångar över räkenskapsåret – räknat ur bokföringen, helt lokalt
- Kvitto- och fakturaskanning med lokal textigenkänning (ingen molntjänst) —
  fotograferade kvitton rätas, ljusutjämnas och skalas upp före tolkning
- Kontoförslag via nyckelord, motpartsglossar och ditt eget motpartsminne
- Fakturor med PDF, OCR-nummer och automatisk bokföring; fakturaspråk
  svenska/engelska per kund
- Bankimport: camt.053 (XML), bank-CSV (Nordea, SEB m.fl.) och xlsx —
  direkt i appen, filerna lämnar aldrig datorn
- Flera bankkonton: varje kontoutdrag bokförs mot rätt konto (Företagskonto,
  Plusgiro, Sparkonto …) — förslag ur filnamnet, valet sparas per konto, och
  egna överföringar mellan konton flaggas så de bara bokförs en gång
- Inkorg för kontohändelser: efter importen öppnas Verifikationer med en
  lista bredvid formuläret — klicka på en händelse, välj motkonto, bokför, och
  raden bockas av tills alla är bokförda
- Rätta vänder felet och lägger originalets rader i formuläret för ombokning
- Moms: underlag + eSKD-fil till Skatteverket
- Deklaration: INK2 (AB), NE (enskild firma), INK4 med delägarfördelning (HB),
  K4 — med SRU-export
- SIE 4-export och -import, fullständig säkerhetskopiering/återställning
- Rapporter: resultat- och balansräkning, huvudbok, verifikationslista
- Gränssnitt på svenska och engelska
- Flera företag och flera konton på samma dator, åtskilda per inloggning

## Rättat sedan interna testet

- Momsdeklarationen täcker nu alla rutor i Skatteverkets blankett: export och
  EU-försäljning (35–40), momsfri försäljning och bidrag (42), inköp med
  omvänd skattskyldighet — t.ex. programvara från USA eller EU — (20–24, 30–32)
  och import (50, 60–62). Tidigare hamnade export i ruta 05 och omvänd moms
  saknades helt. eSKD-filen följer specifikationens radordning
- Inkomstdeklarationen (SRU) får rätt beskattningsperiod även för brutet
  räkenskapsår, räkenskapsschemat täcker hela BAS-kontoplanen (skattekonto,
  periodiseringsfonder, övriga rörelseintäkter m.m. saknades förut), och
  appen varnar för konton som inte skulle komma med. Postadress krävs nu
  innan export, eftersom Skatteverket annars avvisar hela filen
- Fakturor: "Öppna PDF" fäller ut fakturan direkt i fakturalistan, med
  Ladda ner och Stäng – inget nytt fönster att hitta tillbaka från. "Ladda ner
  PDF" sparar via macOS spara-dialog
- Faktura-PDF:er får unika filnamn med datum och kund
  (t.ex. Mitt_Foretag_AB_F1001_2026-01-15_Kund.pdf) och skriver inte längre
  över en äldre faktura med samma nummer
- Kontoutdrag som importeras igen dubbelbokas inte: redan bokförda händelser
  känns igen ur bokföringen
- Importera flera kontoutdrag efter varandra (t.ex. Plusgiro och Sparkonto) och
  bokför sedan allt från en lista, grupperad per konto. Listan sparas mellan
  sessioner, och ett nyare utdrag för samma konto lägger bara till nya händelser
- Bankimport (CSV/camt/xlsx) och värdepappersvyerna kraschade tyst efter
  språkväxlingen infördes – en lokal variabel skuggade översättnings-
  funktionen. Rättat, och en vakt i testsviten hindrar att det återkommer
- Fel lösenord vid inloggning visar nu ett felmeddelande i stället för att
  tyst ladda om sidan
- Inloggningen är ett riktigt formulär — lösenordshanterare erbjuder sig nu
  att spara

## Känt i betan

Se README-avsnittet "Känt i betan" — kortversionen: stäm av SRU-fältkoder mot
Skatteverkets aktuella tabell före skarp inlämning, granska bankimportens
förslag innan du bokför, ta säkerhetskopior, och skriv upp svaret på din
säkerhetsfråga (enda återställningen).
