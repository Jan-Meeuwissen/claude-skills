---
name: lescontext-sd
description: >
  Gebruik deze skill ALTIJD wanneer een gebruiker een les, lesplan, lesactiviteit, werkvorm of lesopzet wil maken of bespreken. 
  De skill verzamelt de benodigde lescontext (groepsgrootte en lesduur) voordat verdere stappen worden gezet.
  Trigger ook bij vragen als: "maak een les over...", "geef me een lesidee", "hoe pak ik dit onderwerp aan in de klas", 
  "maak een opdracht voor mijn studenten", of elk verzoek gericht op onderwijs of lesvoorbereiding.
---

# Skill: lescontextSD

## Doel

Deze skill legt de vaste lescontext vast voor een specifieke onderwijssituatie en vraagt de gebruiker naar de variabele parameters. De verzamelde context wordt gebruikt als basis voor een lesplan (via de skill `lesplan`).

---

## Vaste lescontext (altijd van toepassing)

| Parameter         | Waarde                                      |
|-------------------|---------------------------------------------|
| Lokaal            | Klaslokaal met groot smartboard             |
| Capaciteit        | 28 studenten                                |
| Opleiding         | MBO niveau 4                                |
| Doelgroep         | Voornamelijk mannelijk, leeftijd 15–25 jaar |
| Apparatuur        | Eigen Windows laptop per student            |
| Affiniteit        | Software maken, websites bouwen             |
| Hobby's           | Gamen (veel studenten)                      |

---

## Variabele parameters — altijd opvragen

Vraag de gebruiker bij elke nieuwe les de volgende drie parameters:

### 1. Groepsgrootte
Bied drie keuzes aan:
- 10–15 studenten
- 15–20 studenten
- 20–25 studenten

### 2. Lesduur
Bied vier keuzes aan:
- 30 minuten
- 60 minuten
- 90 minuten
- 120 minuten

### 3. Leerjaar
Bied vier keuzes aan: 1, 2, 3 of 4

De keuze bepaalt de stage-ervaring van de studenten en beïnvloedt werkvormen, voorbeelden en zelfstandigheid:

| Leerjaar | Stage-ervaring                   | Didactische implicatie                                      |
|----------|----------------------------------|-------------------------------------------------------------|
| 1        | Geen stage-ervaring              | Meer sturing nodig, theorie eerst, veel docent-uitleg       |
| 2        | Enkele maanden stage             | Voorzichtig koppelen aan praktijkervaringen                 |
| 3        | Meerdere maanden stage           | Bouwen op werksituaties, meer zelfstandigheid               |
| 4        | Ca. 10 maanden stage-ervaring    | Sterk reflectief, probleemoplossend, min. sturing nodig     |

---

## Motivatie & herkenbaarheid (vaste doelgroepkenmerken)

Gebruik de interesses van studenten om voorbeelden, opdrachten en contexten herkenbaar te maken:

- **Software & websites** — gebruik codevoorbeelden, bouw-opdrachten, debugging-scenario's en UI/UX vraagstukken als context voor leerstof
- **Gamen** — gebruik game-mechanismen (levels, scores, achievements, quests) als metafoor of werkvorm; verwijs naar bekende games als illustratie van concepten (bijv. datastructuren in games, netwerken in multiplayer, UI-design in game-interfaces)

> 💡 Koppel leerdoelen waar mogelijk aan een game- of software-context om motivatie en herkenbaarheid te verhogen.

---

## Instructies voor gebruik

1. **Begroet de gebruiker kort** en geef aan dat je de lescontext gaat verzamelen.
2. **Stel de drie vragen** (groepsgrootte, lesduur en leerjaar) — bij voorkeur alle tegelijk zodat de gebruiker snel kan antwoorden.
3. **Bevestig de volledige context** door een overzicht te tonen van zowel de vaste als de variabele parameters.
4. **Geef aan** dat de context klaar is voor gebruik in een lesplan (via de skill `lesplan`).

### Toon van communicatie
- Vriendelijk en praktisch
- Spreek de gebruiker aan als collega-docent
- Gebruik Nederlands
- Houd het beknopt — geen onnodige uitleg

---

## Uitvoer na het verzamelen van context

Toon een bevestigingsoverzicht in dit formaat:

```
✅ Lescontext vastgelegd

📍 Lokaal         : Klaslokaal met smartboard
👥 Groepsgrootte  : [keuze gebruiker]
🎓 Opleiding      : MBO niveau 4
📅 Leerjaar       : [keuze gebruiker] ([bijbehorende stage-ervaring])
👤 Doelgroep      : Voornamelijk mannelijk, 15–25 jaar
💻 Apparatuur     : Eigen Windows laptop
🎮 Interesses     : Software/websites maken, gamen
⏱ Lesduur        : [keuze gebruiker]

Klaar om een lesplan te maken. Geef het onderwerp of leerdoel op!
```

---

## Doorgave aan lesplan-skill

Na bevestiging geef je de volgende gestructureerde context door aan de `lesplan`-skill:

```
LESCONTEXT:
- lokaal: klaslokaal met smartboard
- groepsgrootte: [10-15 | 15-20 | 20-25]
- opleiding: MBO niveau 4
- leerjaar: [1 | 2 | 3 | 4]
- stage-ervaring: [geen | enkele maanden | meerdere maanden | ca. 10 maanden]
- doelgroep: voornamelijk mannelijk, 15-25 jaar
- affiniteit: software maken, websites bouwen
- hobby: gamen
- apparatuur: eigen Windows laptop per student
- lesduur: [30 | 60 | 90 | 120] minuten
```
