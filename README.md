# Claude Skills bibliotheek — ROC Nijmegen

Deze bibliotheek bevat skills voor Claude: instructies die Claude automatisch inzet bij bepaalde taken, zoals het schrijven van bestuursdocumenten in de ROC Nijmegen stijl.

## Beschikbare skills

| Skill | Waarvoor |
|---|---|
| `schrijfstijl-beleid` | Beleidsnotities, CvB-voorstellen, besluitteksten en andere bestuursdocumenten |

## Eenmalig instellen (eerste keer)

Om de skills te kunnen gebruiken koppel je deze GitHub-repo eenmalig aan je Claude-project:

1. Open [claude.ai](https://claude.ai) en ga naar je project
2. Ga naar **Project Knowledge** en klik op **+**
3. Kies **GitHub**
4. Plak de repo-URL: `https://github.com/Jan-Meeuwissen/claude-skills`
5. Kies via **Configure files** het bestand `skills/index/SKILL.md`
6. Klaar — Claude weet nu waar de rest van de skills te vinden zijn

De index skill bevat de URL van het manifest op GitHub. Claude haalt dat manifest op zodra het nodig is, en laadt daarna automatisch de juiste skill in.

### Skills up-to-date houden

Zijn er nieuwe skills toegevoegd aan de bibliotheek? Klik op het **Sync**-icoon naast de gekoppelde repo in Project Knowledge. Claude heeft dan direct de nieuwste versie.

## Hoe gebruik je een skill?

Zodra de index skill actief is, werkt het zo:

1. Open Claude en stel je vraag zoals je normaal zou doen, bijvoorbeeld: *"Schrijf een voorstel aan het CvB over..."*
2. Claude herkent automatisch dat de schrijfstijl-skill van toepassing is, laadt die in, en past de ROC Nijmegen schrijfstijl toe.
3. Je hoeft de skill niet zelf aan te roepen.

Wil je weten welke skills er beschikbaar zijn? Vraag het gewoon aan Claude: *"Welke skills heb je beschikbaar?"*

## Overzicht van alle skills

Het volledige overzicht staat in [`index.json`](./index.json). Dat bestand wordt automatisch bijgewerkt als er nieuwe skills worden toegevoegd.

## Vragen of verbeteringen?

Neem contact op met Jan Meeuwissen, of open een [issue](https://github.com/Jan-Meeuwissen/claude-skills/issues) in deze repository.
