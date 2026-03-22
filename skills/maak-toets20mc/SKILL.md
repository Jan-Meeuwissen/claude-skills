---
name: maak-toets20mc
description: >
  Gebruik deze skill ALTIJD wanneer een docent een toets, proefwerk, kennischeck of multiple choice toets wil maken voor studenten Software Developer (MBO niveau 4). Trigger bij commando /maak-toets20mc, maar ook bij zinnen als "maak een toets over...", "maak meerkeuzevragen over...", "ik wil studenten toetsen op...", "maak een kennischeck", "genereer 20 vragen over...", of wanneer een docent vraagt om een formatieve of summatieve toets. De skill genereert altijd een toets van 20 meerkeuzevragen (A/B/C), oplopend in moeilijkheid, met toelichting per vraag, als interactieve HTML in ROC Nijmegen huisstijl.
---

# Skill: maak-toets20mc

## Doel

Genereer een toets van **20 meerkeuzevragen** voor MBO-studenten Software Developer. Elke vraag heeft **3 antwoordopties (A, B, C)**. De vragen lopen op in moeilijkheid. De output is een interactieve HTML-pagina in ROC Nijmegen huisstijl, met het toetsblad voor de student én een toelichting per vraag (antwoord + uitleg) in hetzelfde document.

---

## Stap 1: Context verzamelen

Stel **altijd** de volgende drie vragen voordat je de toets genereert. De docent kan antwoorden in tekst of een bestand uploaden (bijv. lesplan, leerstofoverzicht, document).

---

### Vraag 1 — Lesplan
> "Heb je een lesplan of leerstofoverzicht beschikbaar? Beschrijf het kort of upload het bestand."

Gebruik de informatie om de toets aan te laten sluiten op de behandelde leerstof. Let op: leerdoelen, behandelde onderwerpen en niveau.

Als er al een lescontext beschikbaar is via de `lescontext-sd` skill (level, lesduur, groepsgrootte), gebruik die dan als aanvulling of bevestiging. Ontbreekt die context, leid dan het level af uit het lesplan of vraag het expliciet:
- **Level**: Level 1 / Level 2 / Level 3

| Level   | Implicatie voor toetsvragen                                                  |
|---------|------------------------------------------------------------------------------|
| Level 1 | Reproductievragen, eenvoudige begrippen, herkenning van concepten            |
| Level 2 | Begrip en toepassing, vragen over gebruik in een context                     |
| Level 3 | Analyse en redeneren, vragen die inzicht en afweging vereisen                |

---

### Vraag 2 — Onderwerp en doel van de toets
> "Wat is het onderwerp van de toets en wat wil je meten? Beschrijf het of upload een bestand."

Gebruik dit om:
- de leerstof af te bakenen
- de juiste diepgang per vraag te bepalen
- afleidende antwoordopties realistisch en leerzaam te maken

---

### Vraag 3 — Bijzonderheden over de lescontext
> "Zijn er bijzonderheden waar ik rekening mee moet houden?"

Denk aan: tijdslimiet voor de toets, gebruik van hulpmiddelen (open/gesloten boek), taal, of specifieke onderwerpen die juist wél of niet aan bod moeten komen.

---

### ✅ Controlefase (vóór stap 2)

Na het ontvangen van de antwoorden geef je een **beknopt overzicht**:

```
📋 Ik ga een toets maken op basis van het volgende:

- Onderwerp       : [samenvatting]
- Te meten        : [samenvatting leerdoel]
- Level           : [Level 1 / 2 / 3]
- Aantal vragen   : 20 (A/B/C, oplopend in moeilijkheid)
- Bijzonderheden  : [of: geen]

Klopt dit? Dan genereer ik de toets.
```

Wacht op bevestiging van de docent voordat je verdergaat met stap 2.

---

## Stap 2: Genereer de toets

### 2a. Vereiste skills laden

Lees vóór het genereren de volgende twee skills:

1. **`/mnt/skills/user/mcq-expert/SKILL.md`** — voor itemkwaliteit (31 Haladyna-richtlijnen, Bloom-niveaus, IWF-check)
2. **`/mnt/skills/user/roc-nijmegen-brand-guide/SKILL.md`** — voor kleurgebruik, typografie, logo en schrijfstijl in de HTML-output
---

### 2b. Verdeling van de 20 vragen

Verdeel de vragen oplopend in moeilijkheid. Gebruik de **mcq-expert skill** (`/mnt/skills/user/mcq-expert/SKILL.md`) voor het genereren én bewaken van de kwaliteit van elk item. Lees die skill vóór je begint met schrijven.

Koppeling van toets-niveau aan Bloom (via mcq-expert):

| Vragen  | Niveau       | Bloom-niveaus (mcq-expert)         | Omschrijving                                                |
|---------|--------------|------------------------------------|-------------------------------------------------------------|
| 1 – 7   | Makkelijk    | 1 – Onthouden / 2 – Begrijpen      | Reproductie: herkennen, benoemen, definities                |
| 8 – 14  | Gemiddeld    | 2 – Begrijpen / 3 – Toepassen      | Begrip & toepassing: uitleggen, kiezen in een context       |
| 15 – 20 | Moeilijk     | 4 – Analyseren / 5 – Evalueren     | Analyse & redeneren: vergelijken, beoordelen, redeneren     |

---

### 2c. Structuur per vraag — via mcq-expert MAAK-modus

Genereer elk item via de **MAAK-modus van mcq-expert**. Pas de volledige set van 31 Haladyna-richtlijnen toe (zie `mcq-expert/references/haladyna-31-guidelines.md`). Gebruik de game- en software-context (zie §Motivatie).

Elke vraag volgt het mcq-expert outputformaat:

```
Vraag [nummer] — [moeilijkheidslabel] · Bloom: [niveau + naam]

[Vraagstelling]

A. [optie]
B. [optie]
C. [optie]

✓ Correct: [letter] — [korte uitleg]
✗ [letter]: [waarom dit een plausibele maar foute keuze is]
✗ [letter]: [idem]
```

Na het genereren van alle 20 vragen: voer intern een **IWF-check** uit (mcq-expert REVIEW-modus) en herstel eventuele Item Writing Flaws vóórdat de HTML wordt gegenereerd. Meld alleen flaws die niet konden worden opgelost zonder de inhoud te veranderen — de rest los je stil op.

---

### 2d. Toelichting per vraag (in hetzelfde document)

Na het toetsblad volgt een **toelichting** zichtbaar voor de docent (of inklapbaar in HTML):

```
✅ Vraag [nummer] — Juiste antwoord: [A / B / C]

Toelichting: [Leg in 1–3 zinnen uit waarom dit het juiste antwoord is en waarom de andere opties incorrect zijn.]
```

---

### 2e. HTML-opbouw (interactief)

Genereer de output als **interactieve HTML-pagina** met:
- ROC Nijmegen huisstijl (kleuren, typografie, logo)
- Toetsblad bovenaan: genummerde vragen met keuzerondjes (radio buttons) per vraag
- Knop **"Controleer antwoorden"** onderaan het toetsblad
- Na klikken: per vraag kleur-indicatie (groen = goed, rood = fout) + toelichting zichtbaar
- Scoreteller: "Je hebt X van de 20 vragen goed"
- Knop **"Toets herstarten"** na het tonen van de score: reset alle antwoorden, verbergt toelichtingen en scrolt terug naar vraag 1
- Printknop voor het toetsblad (zonder toelichting)

---

### 🔁 Na afloop van stap 2 — aanpassingsvraag

Sluit stap 2 altijd af met:

> "De toets is klaar! Wil je iets aanpassen? Bijvoorbeeld:
> - Een vraag makkelijker of moeilijker maken
> - Een andere context of ander scenario
> - Een vraag vervangen of toevoegen
> - De toelichting bij een vraag aanpassen"

Wacht op de reactie van de docent en verwerk aanpassingen direct.

---

## Motivatie & herkenbaarheid

Gebruik altijd een herkenbare context voor de doelgroep:
- **Software & websites**: shopping carts, login-systemen, API-calls, databases, UI-components
- **Games**: scores, levels, spelersinventory, leaderboards, game loops

> 💡 Koppel vragen aan een game- of software-scenario om motivatie te verhogen.

---

## Toon en taal

- Schrijf de vragen in **jij-vorm** gericht aan de student
- Gebruik **Nederlands**, tenzij het een Engels codeonderwerp is (dan mag code in het Engels)
- Houd de toon neutraal en helder: geen dubbele negaties, geen trucvragen

---

## Afhankelijkheden

| Skill | Waarvoor |
|---|---|
| `mcq-expert` | Itemkwaliteit: MAAK-modus voor schrijven, REVIEW-modus voor IWF-check, Bloom-niveau per vraag |
| `roc-nijmegen-brand-guide` | Visuele huisstijl van de HTML-output |
