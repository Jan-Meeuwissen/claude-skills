---
name: maak-opdracht
description: >
  Gebruik deze skill ALTIJD wanneer een docent een grotere opdracht wil maken die de hele lesstof omvat voor studenten Software Developer (MBO niveau 4). Trigger bij commando /maak-opdracht, maar ook bij zinnen als "maak een opdracht over...", "geef me een projectopdracht", "ik wil studenten de hele stof laten toepassen", "maak een casus-opdracht", "maak een afsluitende opdracht", of wanneer een docent vraagt om een opdracht waarbij studenten zelfstandig aan de slag gaan. De skill verschilt van /maak-oefening: een oefening traint één klein stukje lesstof, een opdracht omvat de volledige leerstof en bevat altijd een casus. De opdracht heeft 4 scaffolding-varianten (van begeleid naar zelfstandig) waar de student zelf uit kiest.
---

# Skill: maak-opdracht

## Doel

Genereer een **volledige opdracht** voor MBO-studenten Software Developer, gebaseerd op een casus. De opdracht omvat de hele leerstof van de les of module. De student kiest zelf één van **4 scaffolding-varianten**, oplopend van eenvoudig en begeleid naar moeilijk en zelfstandig.

---

## Stap 1: Context verzamelen

Stel **altijd** de volgende vragen voordat je de opdracht genereert. De docent kan antwoorden in tekst of een bestand uploaden.

---

### Vraag 1 — Lesplan
> "Heb je een lesplan of leerstofoverzicht beschikbaar? Beschrijf het kort of upload het bestand."

Gebruik dit om de opdracht te laten aansluiten op de volledige behandelde leerstof. Let op: alle leerdoelen, behandelde onderwerpen en volgorde.

Als er al een lescontext beschikbaar is via de `lescontext-sd` skill (level, lesduur, groepsgrootte), gebruik die dan als aanvulling of bevestiging. Ontbreekt die context, leid dan het level af uit het lesplan of vraag het expliciet:
- **Level**: Level 1 / Level 2 / Level 3

| Level   | Implicatie voor de opdracht                                                        |
|---------|------------------------------------------------------------------------------------|
| Level 1 | Meer sturing in alle varianten; variant 1 zeer gestructureerd met veel stapjes     |
| Level 2 | Matige sturing; variant 1 begeleid, variant 4 vraagt zelfstandig redeneren         |
| Level 3 | Weinig sturing; zelfs variant 1 vraagt eigen aanpak, variant 4 is open en complex  |

---

### Vraag 2 — Onderwerp en doel van de opdracht
> "Wat is het onderwerp van de opdracht en wat moet de student ermee laten zien? Beschrijf het of upload een bestand."

Gebruik dit om:
- de leerstof volledig te dekken in de opdracht
- de casus passend te maken bij het onderwerp
- de vier varianten goed te differentiëren in moeilijkheid en zelfstandigheid

---

### Vraag 3 — Casus
> "Is er al een casus beschikbaar voor deze opdracht? Beschrijf hem of upload een bestand."

**Als er een casus is:** gebruik die als basis voor de opdracht. Vraag de docent na het tonen van de casus of hij goed genoeg is, voordat je verdergaat.

**Als er geen casus is:** genereer zelf een passende casus op basis van het onderwerp en level. Presenteer de casus aan de docent met de vraag:
> "Ik heb een casus gemaakt. Vind je deze goed genoeg, of wil je iets aanpassen?"

Wacht op goedkeuring van de docent voordat je verdergaat.

Een goede casus:
- Beschrijft een herkenbare situatie uit de software- of game-wereld
- Geeft duidelijke context (opdrachtgever, probleem, gewenst resultaat)
- Is uitdagend genoeg om de volledige leerstof toe te passen
- Is concreet genoeg om alle 4 varianten op te baseren

---

### Vraag 4 — Outputformaat
> "In welk formaat wil je de opdracht ontvangen?"
> - 🌐 **Interactieve HTML** *(aanbevolen)* — student kiest variant in de browser, instructies per variant zichtbaar
> - 📝 **Word-document (.docx)** — uitprintbaar of te delen via Teams/mail
> - 📄 **Markdown (.md)** — geschikt voor GitHub of een digitale leeromgeving

Gebruik **interactieve HTML als standaard** als de docent geen voorkeur aangeeft.

---

### Vraag 5 — Uitwerking voor docent
> "Wil je een voorbeelduitwerking meegeven voor de docent?"
> - Ja, altijd een voorbeeldoplossing per variant
> - Nee, alleen de opdracht zelf

---

### Vraag 6 — Werkvorm
> "Hoe werkt de keuze tussen de varianten?"
> - Student kiest zelf een variant en maakt die
> - Student doorloopt alle 4 varianten oplopend
> - Docent wijst een variant toe per student

---

### ✅ Controlefase (vóór stap 2)

Na het ontvangen van alle antwoorden geef je een **beknopt overzicht**:

```
📋 Ik ga een opdracht maken op basis van het volgende:

- Onderwerp       : [samenvatting]
- Leerdoel        : [samenvatting]
- Casus           : [titel of korte samenvatting]
- Level           : [Level 1 / 2 / 3]
- Werkvorm        : [keuze docent]
- Uitwerking      : [ja / nee]
- Outputformaat   : [HTML / docx / md]

Klopt dit? Dan maak ik de opdracht aan.
```

Wacht op bevestiging van de docent voordat je verdergaat met stap 2.

---

## Stap 2: Genereer de opdracht

### 2a. ROC Nijmegen huisstijl

Lees de skill `roc-nijmegen-brand-guide` via `/mnt/skills/user/roc-nijmegen-brand-guide/SKILL.md` voordat je de output genereert. Pas de huisstijl toe op kleurgebruik, typografie, logo en schrijfstijl.

---

### 2b. De vier scaffolding-varianten

De opdracht bestaat altijd uit **4 varianten**, oplopend van begeleid naar zelfstandig. De student kiest zelf welke variant hij maakt (tenzij de docent anders aangeeft).

| Variant | Naam              | Kenmerken                                                                 |
|---------|-------------------|---------------------------------------------------------------------------|
| 1       | 🟢 Begeleid        | Veel sturing: stappenplan, invulplekken, hints bij elke stap, voorbeeldcode of -tekst |
| 2       | 🔵 Ondersteund     | Matige sturing: globaal stappenplan, hints beschikbaar maar niet opgedrongen |
| 3       | 🟠 Zelfstandig     | Weinig sturing: alleen het eindresultaat beschreven, student bepaalt aanpak |
| 4       | 🔴 Uitdagend       | Geen sturing: open eindopdracht, student voegt eigen keuzes en uitbreidingen toe |

Alle 4 varianten zijn gebaseerd op **dezelfde casus** en dekken **dezelfde leerstof** — het verschil zit uitsluitend in de hoeveelheid begeleiding en structuur.

---

### 2c. Opbouw per variant

#### Variant 1 — Begeleid 🟢
- Volledige beschrijving van de taak
- Stap-voor-stap instructies (klein en concreet)
- Gedeeltelijk startpunt (code, tekst of sjabloon)
- Hint bij elke stap
- Duidelijke verwachting van het eindresultaat

#### Variant 2 — Ondersteund 🔵
- Beschrijving van de taak
- Globaal stappenplan (minder gedetailleerd dan variant 1)
- Hints beschikbaar maar niet bij elke stap
- Verwachting van het eindresultaat

#### Variant 3 — Zelfstandig 🟠
- Beschrijving van de taak en het gewenste eindresultaat
- Geen stappenplan — student bepaalt eigen aanpak
- Geen hints
- Eventueel een checklist van wat er minimaal in moet zitten

#### Variant 4 — Uitdagend 🔴
- Beschrijving van de casus en het minimale eindresultaat
- Student voegt eigen keuzes, uitbreidingen of verbeteringen toe
- Ruimte voor creativiteit en eigen ontwerp
- Beoordelingscriteria in plaats van instructies

---

### 2d. HTML-opbouw (interactief)

Genereer de output als **interactieve HTML-pagina** met:
- ROC Nijmegen huisstijl (kleuren, typografie, logo)
- Introductie van de casus bovenaan, zichtbaar voor alle varianten
- Keuzemenu of tabs waarmee de student zijn variant selecteert
- Per variant: de bijbehorende instructies, hints (uitklapbaar) en startpunt
- Indien uitwerking gewenst: inklapbaar blok "Voorbeelduitwerking (alleen voor docent)" per variant
- Printknop voor de geselecteerde variant

---

### 🔁 Na afloop van stap 2 — aanpassingsvraag

Sluit stap 2 altijd af met:

> "De opdracht is klaar! Wil je iets aanpassen? Bijvoorbeeld:
> - Een variant makkelijker of moeilijker maken
> - De casus aanpassen
> - Extra hints of stappen toevoegen
> - De werkvorm of het formaat wijzigen
> - Een voorbeelduitwerking toevoegen of aanpassen"

Wacht op de reactie van de docent en verwerk aanpassingen direct.

---

## Motivatie & herkenbaarheid

Gebruik altijd een herkenbare context voor de doelgroep:
- **Software & websites**: shopping carts, login-systemen, API-calls, databases, UI-components
- **Games**: scores, levels, spelersinventory, leaderboards, game loops

> 💡 Koppel de casus aan een game- of software-scenario om motivatie en herkenbaarheid te verhogen.

---

## Toon en taal

- Schrijf de opdracht in **jij-vorm** gericht aan de student
- Gebruik **Nederlands**, tenzij het een Engels codeonderwerp is (dan mag code in het Engels)
- Houd de toon uitnodigend en praktisch: "Jouw taak is om..."
- Vermijd schoolse of formele taal
