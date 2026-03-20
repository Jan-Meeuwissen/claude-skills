# Claude Skills bibliotheek — ROC Nijmegen

Deze bibliotheek bevat skills voor Claude: instructies die Claude automatisch inzet bij bepaalde taken, zoals het schrijven van bestuursdocumenten in de ROC Nijmegen stijl.

## Beschikbare skills

| Skill | Waarvoor |
|---|---|
| `schrijfstijl-beleid` | Beleidsnotities, CvB-voorstellen, besluitteksten en andere bestuursdocumenten |
| `lees-dim` | Vragen over het Directe Instructie Model (DIM/EDI) en verwante instructiemodellen |
| `lees-kd-itmw` | Kwalificatiedossier Medewerker ICT (crebo 25999, niveau 2, versie 2024) |
| `lees-kd-itss` | Kwalificatiedossier ICT support and systems (crebo 23405, versie 2025) |
| `lees-kd-sd` | Kwalificatiedossier Software Developer (crebo 25998, niveau 4, versie 2024) |
| `lees-rekeneisen` | Rekeneisen voor het MBO (Expertgroep Herijking Rekeneisen mbo, 2020) |
| `lees-visie` | Onderwijsvisie van het ICT-team Software Developer en ROC Nijmegen |
| `lescontext-sd` | Lescontext verzamelen (groepsgrootte, lesduur) voor lesvoorbereiding |
| `maak-lesplan` | Volledig lesplan maken via een begeleide workflow in acht stappen |
| `maak-oefening` | Scaffolded oefeningen maken voor studenten Software Developer (niveau 4) |
| `maak-opdracht` | Grotere casusopdrachten maken die de volledige lesstof omvatten |
| `maak-presentatie` | Docentpresentaties maken in ROC Nijmegen huisstijl, met sprekersnotities |
| `maak-toets20mc` | Toetsen van 20 meerkeuzevragen (A/B/C) maken, oplopend in moeilijkheid |
| `roc-nijmegen-brand-guide` | Huisstijl, kleuren, typografie en tone of voice van ROC Nijmegen |

## Gebruik

Start een nieuwe chat op [claude.ai](https://claude.ai) en stuur dit als eerste bericht:

```
Fetch https://raw.githubusercontent.com/Jan-Meeuwissen/claude-skills/main/skills/index/SKILL.md en volg de instructies daarin.
```

Claude laadt daarna automatisch de juiste skill in op basis van je vraag.

> **Tip:** Gebruik je de skills dagelijks? Maak dan een project aan op claude.ai en plak bovenstaande regel in het **Instructions** veld. Dan hoef je het niet elke keer opnieuw te doen.

## Vragen of verbeteringen?

Neem contact op met Jan Meeuwissen, of open een [issue](https://github.com/Jan-Meeuwissen/claude-skills/issues) in deze repository.
