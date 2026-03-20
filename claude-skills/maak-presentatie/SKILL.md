---
name: maak-presentatie
description: >
  Gebruik deze skill ALTIJD wanneer een docent een presentatie wil maken voor een les aan studenten Software Developer (MBO niveau 4). Trigger bij commando /maak-presentatie, maar ook bij zinnen als "maak een presentatie over...", "ik wil een les geven over...", "maak slides over...", "geef me een lesuitleg in presentatievorm", of wanneer een docent vraagt om een visuele lesopbouw. De skill genereert een volledige docentpresentatie met spreker-notities en visuele suggesties per slide, in ROC Nijmegen huisstijl of een alternatief formaat naar keuze.
---

# Skill: maak-presentatie

## Doel

Genereer een **docentpresentatie** voor een les aan MBO-studenten Software Developer. De presentatie bevat slides met inhoud, spreker-notities per slide en visuele suggesties. De presentatie bevat altijd concrete voorbeelden om de lesstof te verduidelijken, bij voorkeur uit een herkenbare software- of game-context.

---

## Stap 1: Context verzamelen

Stel **altijd** de volgende vragen voordat je de presentatie genereert. De docent kan antwoorden in tekst of een bestand uploaden.

---

### Vraag 1.1 — Lesplan
> "Heb je een lesplan beschikbaar? Beschrijf het kort of upload het bestand."

Gebruik dit om de presentatie aan te laten sluiten op de opbouw van de les. Let op: lesduur, leerdoelen, volgorde van onderwerpen en gebruikte werkvormen.

Als er al een lescontext beschikbaar is via de `lescontext-sd` skill (level, lesduur, groepsgrootte), gebruik die dan als aanvulling of bevestiging. Ontbreekt die context, leid dan het level en de lesduur af uit het lesplan, of vraag ze expliciet:
- **Level**: Level 1 / Level 2 / Level 3
- **Lesduur**: 30 / 60 / 90 / 120 minuten

| Level   | Implicatie voor de presentatie                                                |
|---------|-------------------------------------------------------------------------------|
| Level 1 | Meer uitleg, kleinere stappen, veel voorbeelden, eenvoudige taal              |
| Level 2 | Balans tussen uitleg en toepassing, voorbeelden koppelen aan praktijk         |
| Level 3 | Meer diepgang, kritische vragen, eigen redenering van studenten stimuleren    |

---

### Vraag 1.2 — Onderwerp en doel van de presentatie
> "Wat is het onderwerp van de presentatie en wat moet de student erna weten of kunnen? Beschrijf het of upload een bestand."

Gebruik dit om:
- de kernboodschap per slide te bepalen
- het juiste abstractieniveau te kiezen
- voorbeelden passend te maken bij het leerdoel

---

### Vraag 1.3 — Casus
> "Is er sprake van een casus bij deze les?"

**Als er geen casus is:** ga verder zonder casus. Een casus is optioneel bij een presentatie.

**Als er wel een casus is:** vraag de docent hem te beschrijven of te uploaden.
> "Beschrijf de casus of upload een bestand."

Gebruik de casus als rode draad door de presentatie: introduceer hem aan het begin en verwijs er bij elke slide naar terug waar relevant.

---

### ✅ Controlefase (vóór stap 2)

Na het ontvangen van de antwoorden op 1.1 t/m 1.3 geef je een **beknopt overzicht**:

```
📋 Ik ga een eerste versie van de presentatie maken op basis van het volgende:

- Onderwerp       : [samenvatting]
- Leerdoel        : [samenvatting]
- Casus           : [titel/samenvatting, of: geen]
- Level           : [Level 1 / 2 / 3]
- Lesduur         : [x minuten] → [geschat aantal slides]

Klopt dit? Dan maak ik een eerste versie in Markdown.
```

Wacht op bevestiging van de docent voordat je verdergaat met stap 2.

---

## Stap 2: Genereer de presentatie (Markdown-versie)

Genereer de presentatie eerst altijd als **Markdown (.md)**. Dit is de werkversie waarmee de docent de inhoud beoordeelt en aanpassingen doorgeeft vóórdat de definitieve opmaak wordt gemaakt.

### 2a. Opbouw van de presentatie

Gebruik de volgende standaardopbouw, afgestemd op de lesduur:

| Lesduur    | Geschat aantal slides |
|------------|-----------------------|
| 30 minuten | 8 – 12 slides         |
| 60 minuten | 12 – 18 slides        |
| 90 minuten | 18 – 25 slides        |
| 120 minuten| 25 – 35 slides        |

**Vaste structuur:**
1. **Titelslide** — onderwerp, lesdoel, eventueel casus-intro
2. **Terugblik** — korte verbinding met vorige les (1 slide)
3. **Leerdoelen** — wat weet/kan de student aan het einde (1 slide)
4. **Inhoud** — kernslides met uitleg, voorbeelden en tussenvragen
5. **Samenvatting** — kernpunten in één oogopslag (1 slide)
6. **Afsluiting** — opdracht, volgende stap of reflectievraag (1 slide)

---

### 2c. Structuur per slide

Elke slide volgt dit formaat:

```
## Slide [nummer] — [titel]

**Inhoud:**
[Kernboodschap in max. 5 bullets of 1 korte alinea. Geen lange zinnen.]

**Voorbeeld:**
[Concreet voorbeeld uit een software- of game-context — zie §Motivatie]

**Visuele suggestie:**
[Beschrijving van een passende afbeelding, icoon, diagram of animatie]

**Spreker-notities:**
[Wat de docent zegt bij deze slide: toelichting, anekdote, vraag aan de klas, overgang naar volgende slide]
```

---

### 2d. Voorbeelden in de presentatie

Voeg bij elke inhoudslide minimaal **één concreet voorbeeld** toe dat de leerstof verduidelijkt. Kies voorbeelden die herkenbaar zijn voor de doelgroep:

- **Software & websites**: shopping carts, login-systemen, API-calls, databases, UI-components, formulieren
- **Games**: scores, levels, spelersinventory, leaderboards, game loops, multiplayer-netwerken

> 💡 Als er een casus beschikbaar is, gebruik die dan als terugkerend voorbeeld door de hele presentatie.

---

### 2e. Iteratieloop — aanpassingen verwerken

Sluit de Markdown-versie altijd af met:

> "Hier is de eerste versie van de presentatie! Wil je iets aanpassen? Bijvoorbeeld:
> - Een slide toevoegen of verwijderen
> - Een voorbeeld aanpassen of uitbreiden
> - De volgorde van slides wijzigen
> - Meer of minder spreker-notities
> - Een slide makkelijker of moeilijker maken"

Verwerk de aanpassingen direct en toon de bijgewerkte versie. **Herhaal dit totdat de docent aangeeft tevreden te zijn.** Ga dan pas verder met stap 3.

---

## Stap 3: Definitieve output

Pas wanneer de docent tevreden is met de inhoud, stel je de volgende twee vragen:

### Vraag 3.1 — Outputformaat
> "In welk formaat wil je de definitieve presentatie ontvangen?"
> - 🌐 **Interactieve HTML** *(aanbevolen)* — slides in de browser, spreker-notities inklapbaar, fullscreen-modus
> - 📊 **PowerPoint (.pptx)** — bewerkbaar, te gebruiken op smartboard
> - 📄 **Markdown (.md)** — blijf in Markdown als dat voldoet

Gebruik **interactieve HTML als standaard** als de docent geen voorkeur aangeeft.

### Vraag 3.2 — Huisstijl
> "Welke huisstijl wil je gebruiken?"
> - 🎨 **ROC Nijmegen** *(standaard)* — officiële kleuren, typografie en logo
> - 🖤 **Minimalistisch** — zwart/wit met accentkleur, geen logo
> - 🌙 **Dark mode** — donkere achtergrond, lichte tekst, geschikt voor verduisterd lokaal
> - ✏️ **Eigen voorkeur** — docent beschrijft zelf wat hij wil

Gebruik **ROC Nijmegen als standaard** als de docent geen voorkeur aangeeft. Lees in dat geval de skill `roc-nijmegen-brand-guide` via `/mnt/skills/user/roc-nijmegen-brand-guide/SKILL.md` voordat je genereert.

---

### 3a. Genereer definitieve versie

Genereer de presentatie in het gekozen formaat met de gekozen huisstijl.

**Bij interactieve HTML:**
- Gekozen huisstijl (kleuren, typografie, eventueel logo)
- Navigatie tussen slides (pijltjestoetsen of knoppen)
- Spreker-notities inklapbaar onder elke slide
- Visuele suggestie zichtbaar als beschrijving of placeholder
- Volledig-scherm modus (presentatiemodus)
- Printknop voor een handout-versie (slides zonder notities)

---

## Motivatie & herkenbaarheid

Gebruik altijd een herkenbare context voor de doelgroep:
- **Software & websites**: shopping carts, login-systemen, API-calls, databases, UI-components
- **Games**: scores, levels, spelersinventory, leaderboards, game loops

> 💡 Koppel voorbeelden aan een game- of software-scenario om motivatie en herkenbaarheid te verhogen.

---

## Toon en taal

- Schrijf de slide-inhoud in **heldere, korte zinnen** — geen lange teksten op een slide
- Schrijf spreker-notities in **spreektaal**, alsof de docent het hardop vertelt
- Gebruik **Nederlands**, tenzij het een Engels codeonderwerp is
- Houd de toon activerend: stel tussenvragen aan de klas, gebruik "Wat denk jij?", "Herken je dit?"
