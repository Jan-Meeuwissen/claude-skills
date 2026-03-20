---
name: maak-oefening
description: >
  Gebruik deze skill ALTIJD wanneer een docent een oefening, opdracht, taak of werkvorm wil maken voor studenten Software Developer (MBO niveau 4). Trigger bij commando /maak-oefening, maar ook bij zinnen als "maak een oefening over...", "geef me een opdracht voor...", "ik wil studenten laten oefenen met...", "maak een codevraagstuk over...", "maak een invuloefening", "maak open vragen over...", of wanneer een docent vraagt hoe studenten iets kunnen inoefenen. De skill genereert altijd een scaffolded oefening: stapsgewijs opgebouwd van makkelijk naar moeilijk, met hints, een voorbeeldoplossing en een startpunt. Gebruik deze skill ook als er al een lescontext beschikbaar is vanuit de lescontext-sd skill.
---

# Skill: maak-oefening

## Doel

Genereer een scaffolded oefening voor MBO-studenten Software Developer. De oefening is opgebouwd van makkelijk naar moeilijk, bevat hints per stap, begint met een voorbeeld, en geeft een gedeeltelijk startpunt (code of tekst).

Ondersteunde oefeningstypen:
- **Open vragen** — studenten formuleren een antwoord in eigen woorden
- **Invuloefening** — studenten vullen ontbrekende code, begrippen of zinnen in
- **Codevraagstuk** — studenten schrijven of debuggen code

---

## Stap 1: Context verzamelen

Stel **altijd** de volgende drie vragen voordat je de oefening genereert. De docent kan antwoorden in tekst of een bestand uploaden (bijv. lesplan, opdracht, document).

---

### Vraag 1 — Lesplan
> "Heb je een lesplan beschikbaar? Beschrijf het kort of upload het bestand."

Gebruik de informatie uit het lesplan om de oefening aan te laten sluiten op de les. Let op: lesduur, leerdoelen, gebruikte werkvormen en volgorde in de les.

Als er al een lescontext beschikbaar is via de `lescontext-sd` skill (level, lesduur, groepsgrootte), gebruik die dan als aanvulling of bevestiging. Ontbreekt die context, leid dan level en lesduur af uit het lesplan, of vraag ze expliciet:
- **Level**: Level 1 / Level 2 / Level 3
- **Lesduur**: 30 / 60 / 90 / 120 minuten

| Level   | Didactische implicatie voor oefening                                          |
|---------|-------------------------------------------------------------------------------|
| Level 1 | Veel sturing: kleinere stappen, meer hints, eenvoudige context                |
| Level 2 | Matige sturing: stappen iets groter, hints als optie aangeboden               |
| Level 3 | Weinig sturing: grotere stappen, hints alleen op aanvraag, hogere complexiteit |

---

### Vraag 2 — Onderwerp en doel van de oefening
> "Wat is het onderwerp van de oefening en wat moet de student ermee leren of kunnen? Beschrijf het of upload een bestand."

Gebruik dit om:
- het leerdoel van de oefening scherp te stellen
- het oefeningstype te bepalen (open vragen / invuloefening / codevraagstuk), tenzij de docent dat al heeft meegegeven
- de moeilijkheidsgraad en diepgang af te stemmen op het doel

---

### Vraag 3 — Bijzonderheden over de lescontext
> "Zijn er bijzonderheden over de groep of situatie waar ik rekening mee moet houden?"

Denk aan: differentiatie (sterke/zwakke studenten), beschikbare tools, taal, samenwerking (solo/duo/groep), of andere randvoorwaarden.

---

### ✅ Controlefase (vóór stap 2)

Na het ontvangen van de antwoorden op de drie vragen, geef je een **beknopt overzicht** van hoe je de oefening gaat opbouwen:

```
📋 Ik ga een oefening maken op basis van het volgende:

- Onderwerp       : [samenvatting]
- Leerdoel        : [samenvatting]
- Oefeningstype   : [open vragen / invuloefening / codevraagstuk]
- Level           : [Level 1 / 2 / 3]
- Lesduur         : [x minuten] → [x stappen]
- Bijzonderheden  : [of: geen]

Klopt dit? Dan maak ik de oefening aan.
```

Wacht op bevestiging van de docent voordat je verdergaat met stap 2.

---

## Stap 2: Genereer de oefening

### 2a. Vraag het gewenste outputformaat

Vraag de docent welk formaat de voorkeur heeft:

> "In welk formaat wil je de oefening ontvangen?"
> - 🌐 **Interactieve HTML** *(aanbevolen)* — student werkt direct in de browser, hints uitklapbaar, stappen zichtbaar
> - 📝 **Word-document (.docx)** — uitprintbaar of te delen via Teams/mail
> - 📄 **Markdown (.md)** — eenvoudig, geschikt voor GitHub of een digitale leeromgeving

Gebruik **interactieve HTML als standaard** als de docent geen voorkeur aangeeft.

---

### 2b. ROC Nijmegen huisstijl

Pas bij het genereren altijd de **ROC Nijmegen huisstijl** toe. Lees hiervoor de skill `roc-nijmegen-brand-guide` via `/mnt/skills/user/roc-nijmegen-brand-guide/SKILL.md` voordat je de output genereert. Pas de huisstijl toe op kleurgebruik, typografie, logo (indien van toepassing) en schrijfstijl.

---

### 2c. Genereer de oefening

Genereer de oefening in het gekozen formaat, altijd in het volgende scaffolding-formaat:

---

### 📘 Voorbeeld (Eerst een voorbeeld, dan zelf doen)

Geef een volledig uitgewerkt voorbeeld dat het concept illustreert. Het voorbeeld:
- is herkenbaar voor de doelgroep (software, websites, games)
- is eenvoudiger dan de oefening zelf
- legt uit *waarom* iets zo werkt, niet alleen *wat* het is

> 💡 Bij een **codevraagstuk**: geef werkende code met commentaar.
> Bij een **invuloefening**: geef een volledig ingevulde versie.
> Bij **open vragen**: geef een voorbeeldvraag + voorbeeldantwoord.

---

### 🧩 Startpunt (Gedeeltelijke code/antwoord als startpunt)

Geef de student een startpunt om mee te werken:
- Bij **codevraagstuk**: gedeeltelijke code met `# TODO` commentaar op de plekken die de student moet invullen
- Bij **invuloefening**: tekst of code met `______` op de lege plekken
- Bij **open vragen**: de vraagstelling met eventueel een aanzet of structuurhint

---

### 📋 Stappen (Stapsgewijs van makkelijk naar moeilijk)

Verdeel de oefening in **3 tot 5 stappen**, oplopend in moeilijkheid:

**Stap 1 – [Titel]** *(makkelijk)*
Omschrijving van de taak.
> 💡 Hint: [concrete hint die helpt zonder het antwoord weg te geven]

**Stap 2 – [Titel]** *(iets moeilijker)*
Omschrijving van de taak.
> 💡 Hint: [hint]

**Stap 3 – [Titel]** *(gemiddeld)*
Omschrijving van de taak.
> 💡 Hint: [hint]

*(Voeg stap 4 en 5 toe indien lesduur en level dat rechtvaardigen)*

---

### ✅ Uitwerking (optioneel tonen aan docent)

Geef na de oefening een **volledig uitgewerkte uitwerking** voor de docent, duidelijk gescheiden van de studentversie met:

```
--- UITWERKING (alleen voor docent) ---
```

---

### 🔁 Na afloop van stap 2 — aanpassingsvraag

Sluit stap 2 altijd af met:

> "De oefening is klaar! Wil je iets aanpassen? Bijvoorbeeld:
> - Een stap makkelijker of moeilijker maken
> - Een andere context of ander scenario
> - Extra stappen of hints toevoegen
> - Het formaat wijzigen (HTML / docx / md)
> - De uitwerking zien"

Wacht op de reactie van de docent en verwerk aanpassingen direct.

---

## Omvang per lesduur

| Lesduur    | Aanbevolen omvang oefening                          |
|------------|-----------------------------------------------------|
| 30 minuten | 1 oefeningstype, max. 3 stappen                     |
| 60 minuten | 1–2 oefeningstypen, 3–4 stappen                     |
| 90 minuten | 2 oefeningstypen, 4–5 stappen                       |
| 120 minuten| 2–3 oefeningstypen, 5 stappen, uitgebreide context  |

---

## Motivatie & herkenbaarheid

Gebruik altijd een herkenbare context voor de doelgroep:
- **Software & websites**: shopping carts, login-systemen, API-calls, databases, UI-components
- **Games**: scores, levels, spelersinventory, leaderboards, game loops

> 💡 Koppel het onderwerp aan een game- of software-scenario om motivatie te verhogen.

---

## Toon en taal

- Schrijf de oefening in **jij-vorm** gericht aan de student
- Gebruik **Nederlands**, tenzij het een Engels codeonderwerp is (dan mag code in het Engels)
- Houd de toon uitnodigend en praktisch: "Jouw taak is om..."
- Vermijd schoolse of formele taal

---

## Uitvoer na genereren

Sluit af met een korte vraag aan de docent:
> "Wil je de oefening aanpassen, een ander type toevoegen, of de uitwerking zien?"
