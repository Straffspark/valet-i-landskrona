# Valet i Landskrona

En fristående webbapp med valresultaten i Landskrona: kommun-, region- och riksdagsvalet 2026 per valdistrikt, utvecklingen 2006–2026 och bakgrundsdata från SCB.

**Appen:** https://straffspark.github.io/valet-i-landskrona/

## Lägg appen på hemskärmen (iPhone)

1. Öppna länken ovan i Safari.
2. Tryck på dela-ikonen och välj **Lägg till på hemskärmen**.

Appen öppnas då i helskärm som en vanlig app och fungerar även utan nät efter första besöket.

## Lösenord

Appen är lösenordsskyddad. Datan och nedladdningsfilerna ligger krypterade i repot (AES-GCM, nyckel härledd ur lösenordet med PBKDF2-SHA256) och dekrypteras först i webbläsaren när rätt lösenord anges. Väljer man "Kom ihåg på den här enheten" sparas nyckeln lokalt i webbläsaren; knappen "Lås appen på den här enheten" längst ner i Översikt tar bort den.

Lösenordet står inte i repot. Byt lösenord genom att kryptera om `data.enc.json` och filerna i `nedladdning/` med ett nytt lösenord.

## Innehåll

- **Översikt** – partiernas andel 2026 jämfört med 2022, mandat i kommunfullmäktige och röstdelning mellan valen.
- **Karta** – andel eller förändring per valdistrikt, hela kommunen eller staden. Tryck på ett distrikt för detaljer.
- **2006–2026** – partiernas andel, mandat, valdeltagande och utvecklingen i kommunens fyra delar.
- **Distrikt** – sorterbar lista och distriktens utveckling 2010–2026.
- **Bakgrund** – SCB:s bakgrundsvariabler (utrikes födda, inkomst, utbildning, ålder) mot partival.

## Filer

| Fil | Innehåll |
|---|---|
| `index.html` | Appen |
| `data.enc.json` | All data som appen använder, krypterad |
| `manifest.webmanifest`, `sw.js`, `icons/` | Hemskärmsikon och offline-stöd |
| `nedladdning/*.enc` | Krypterade nedladdningar: rådata (Excel), rapport (Word) och resultat per distrikt (CSV). Hämtas via appen. |

## Källor och metod

- Valmyndigheten, slutligt valresultat per valdistrikt: [resultat.val.se](https://resultat.val.se/val2026) (2022–2026) och [historik.val.se](https://historik.val.se/val/val2018/statistik/index.html) (2006–2018). Distriktssummorna stämmer mot Valmyndighetens kommuntotaler.
- I riksdagsvalet 2006 redovisades SD bland övriga partier; SD:s röster är hämtade separat per distrikt.
- SCB:s valanalys för riksdagsvalet 2026 (röstberättigade i riksdagsvalet per valdistrikt).
- Valdistriktsgränser: Valmyndighetens geodata 2026, förenklade.
- Distriktsgränserna har ändrats mellan valen (senast 2018 och 2022). Jämförelser per distrikt över tid görs på namn och ska läsas med försiktighet. Kommunens fyra delar (stad, Ven, Annelöv–Häljarp–Asmundtorp, Glumslöv–Härslöv) har i stort sett oförändrade yttre gränser.
