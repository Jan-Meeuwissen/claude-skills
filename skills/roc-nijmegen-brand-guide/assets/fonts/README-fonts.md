## Fonts (bronbestanden)

De huisstijlfonts zijn als bronbestanden bijgevoegd in `assets/fonts/`, zodat je ze niet meer online hoeft op te halen. Gebruik altijd deze meegeleverde bestanden — niet een online download, want fontpaden (zoals die van Google Fonts) veranderen en breken.

### Beschikbare bestanden

| Bestand | Font-familie (zo aanroepen) | Gewicht | Gebruik volgens huisstijl |
|---|---|---|---|
| `Bungee-Regular.ttf` | `Bungee` | Regular | Hoofdkoppen / display (mag 9° schuin) |
| `Montserrat-Regular.ttf` | `Montserrat` | Regular | Onderkoppen, korte teksten, kadertekst |
| `Montserrat-SemiBold.ttf` | `Montserrat SemiBold` | Regular | Accent / tussengewicht |
| `Montserrat-Bold.ttf` | `Montserrat` | Bold | Nadruk in koppen en korte teksten |
| `Montserrat-Black.ttf` | `Montserrat Black` | Regular | Zware koppen / labels |
| `Roboto-Regular.ttf` | `Roboto` | Regular | Broodtekst en tussenkoppen (brochures) |
| `Roboto-Bold.ttf` | `Roboto` | Bold | Nadruk in broodtekst |
| `Roboto-Black.ttf` | `Roboto Black` | Regular | Tussenkop (Roboto black) |

> Let op de familienamen: `Montserrat Black`, `Montserrat SemiBold` en `Roboto Black` zijn **eigen families** (niet via een "bold/black"-vlag te bereiken). Roep ze rechtstreeks bij die naam aan. Voor `Montserrat` en `Roboto` werkt het bold-gewicht wél via de standaard bold-instelling.

### Installeren in een build-omgeving (Linux / LibreOffice / PowerPoint-generatie)

```bash
mkdir -p ~/.fonts
cp assets/fonts/*.ttf ~/.fonts/
fc-cache -f ~/.fonts
fc-list | grep -iE "bungee|montserrat|roboto"   # controle
```

Daarna zijn de fonts beschikbaar voor o.a. `pptxgenjs` / LibreOffice. In een PowerPoint die je deelt is het verstandig de fonts in te sluiten (Bestand → Opties → Opslaan → "Lettertypen in het bestand insluiten"), zodat ze ook kloppen op een computer waar de fonts niet geïnstalleerd zijn.

### Herkomst en licenties

De fonts mogen worden meegeleverd; de licentiebestanden staan in dezelfde map.

- **Bungee** — SIL Open Font License 1.1 (`LICENSE-Bungee-OFL.txt`). Bron: Google Fonts (`ofl/bungee`).
- **Montserrat** — SIL Open Font License 1.1 (`LICENSE-Montserrat-OFL.txt`). De statische gewichten zijn gegenereerd uit het officiële variabele font van Google Fonts (`ofl/montserrat`).
- **Roboto** — Apache License 2.0 (`LICENSE-Roboto-Apache.txt`). Bron: npm-pakket `roboto-fontface` (woff2 omgezet naar TTF).

> Bij gebruik van OFL-fonts moeten de `OFL.txt`-bestanden meegeleverd blijven. Bij Roboto (Apache 2.0) moet de licentie eveneens behouden blijven. Verander de bestandsnamen van de licenties dus niet en haal ze niet weg.
