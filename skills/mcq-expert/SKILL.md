---
name: mcq-expert
description: >
  Wetenschappelijk onderbouwde MCQ-expert op basis van Haladyna, Downing & Rodriguez (2002) en de
  AERA/APA/NCME Standards. Gebruik deze skill ALTIJD wanneer iemand:
  - MCQ-vragen wil maken of laten genereren op basis van lesstof, een onderwerp of leerdoelen
  - Bestaande MCQ-vragen wil laten nakijken, reviewen of verbeteren (Item Writing Flaws)
  - Wil weten op welk Bloom-niveau een vraag zit, of vragen wil genereren op een specifiek niveau
  - Vraagt om "goede meerkeuzevragen", "toetsvragen", "quizvragen", "kennischeck" of "items"
  - Zegt: "check deze vraag", "klopt deze MCQ wel?", "is dit een goede vraag?", "maak vragen over X"
  Trigger ook bij lossere verzoeken als "maak wat vragen over Python" of "kun je mijn toets nakijken".
  Standaard: 3 antwoordopties (A/B/C), tenzij de gebruiker anders vraagt.
---

# MCQ Expert

Wetenschappelijk onderbouwde assistent voor het **maken**, **reviewen** en **analyseren** van
Multiple Choice Questions (MCQ). Gebaseerd op de taxonomie van 31 item-writing guidelines van
Haladyna, Downing & Rodriguez (2002), empirisch gevalideerd via 27 meetkundige leerboeken en
27 onderzoeksstudies.

---

## Drie modi

Bepaal op basis van het verzoek welke modus van toepassing is.
Combinaties zijn mogelijk (bijv. maak + analyseer meteen op Bloom).

| Modus | Wanneer |
|---|---|
| **MAAK** | Gebruiker wil nieuwe MCQ-vragen genereren |
| **REVIEW** | Gebruiker heeft bestaande vragen en wil feedback |
| **ANALYSEER** | Gebruiker wil weten op welk Bloom-niveau vraag/vragen zitten |

---

## MODUS: MAAK

### Stap 1 — Verzamel context (als niet gegeven)

Vraag compacte input als het ontbreekt:
- **Onderwerp / leerstof** — wat moeten studenten kennen of kunnen?
- **Doelgroep** — welk niveau, welke opleiding?
- **Bloom-niveau** — onthouden, begrijpen, toepassen, analyseren, evalueren, creëren? (zie referentie)
- **Aantal vragen** — hoeveel items?
- **Opties** — standaard 3 (A/B/C); vraag alleen af als gebruiker anders aangeeft

Vraag niet alles tegelijk als er al veel context is — gebruik wat gegeven is.

### Stap 2 — Genereer de vragen

Pas voor **elk item** de volgende regels toe (Haladyna et al., 2002):

#### Inhoud (Content)
- Elk item meet **één specifiek leerdoel** en **één mentale handeling** (regel 1)
- Toets **belangrijke inhoud** — geen triviale weetjes (regel 2)
- Gebruik **nieuw materiaal of herformuleringen** bij hogere orde denken — niet letterlijk uit de les (regel 3)
- Houd items **inhoudelijk onafhankelijk** van elkaar (regel 4)
- Vermijd te specifieke of te algemene formulering (regel 5)
- **Geen mening-gebaseerde items** — er moet een verdedigbaar juist antwoord zijn (regel 6)
- **Geen strikvragen** — het doel is kennis meten, niet misleiden (regel 7)
- Gebruik **begrijpelijk taalgebruik** passend bij de doelgroep (regel 8)

#### De stam (Stem)
- De stam bevat het **centrale idee en de vraag** — niet de antwoordopties (regel 15)
- Formuleer de stam als een **volledige vraag of opdracht** (regel 14)
- Vermijd **onnodige informatie** (window dressing) (regel 16)
- Gebruik **positieve formulering**; vermijd NIET of BEHALVE. Als het tóch nodig is: schrijf het woord **VET en HOOFDLETTERS** (regel 17)

#### De opties (Choices)
- **Standaard 3 opties** (A/B/C) — onderzoek toont aan dat 3 opties psychometrisch optimaal zijn (Rodriguez, 2005, meta-analyse van 80 jaar onderzoek); gebruik 4 opties alleen op expliciete vraag
- Er is **precies één correct antwoord** — geen ambiguïteit (regel 19)
- Varieer de positie van het juiste antwoord over de itemset (niet altijd A of C) (regel 20)
- Rangschik opties **logisch of numeriek** waar mogelijk (regel 21)
- Opties zijn **onderling uitsluitend** — geen overlappende antwoorden (regel 22)
- Opties zijn **homogeen** in inhoud en grammaticale structuur (regel 23)
- Houd opties **gelijk in lengte** — het langste antwoord is anders verdacht (regel 24)
- Vermijd "Geen van bovenstaande" (gebruik alleen als de afwezigheid van kennis toetsbaar is) (regel 25)
- Vermijd "Alle bovenstaande" — dit onthult gedeeltelijk juiste opties (regel 26)
- Formuleer opties **positief**; vermijd NIET in de opties (regel 27)

#### Distractoren (foute opties)
- Elke distractor moet **plausibel** zijn — echte verleidingen voor iemand zonder kennis (regel 29)
- Gebruik **typische fouten van studenten** als basis voor distractoren (regel 30)
- Vermijd aanwijzingen die het juiste antwoord verraden (regel 28):
  - Geen absolute termen: *altijd, nooit, volledig, absoluut*
  - Geen klankassociatie met woorden uit de stam
  - Grammaticale consistentie in alle opties
  - Geen overduidelijk absurde optie
  - Geen paren/drietallen die samen de richting aangeven

### Stap 3 — Geef het item terug in dit formaat

```
**Vraag [n]** · Bloom: [niveau] · Leerdoel: [korte omschrijving]

[Stam: de vraag of situatieschets]

A. [optie]
B. [optie]
C. [optie]

✓ Correct: [letter] — [korte uitleg waarom dit het juiste antwoord is]
✗ Distractor B: [waarom dit een plausibele maar foute keuze is]
✗ Distractor C: [idem]
```

Sluit af met een korte **kwaliteitscheck**: meld proactief als een item op een regel scoort die
aandacht verdient (bijv. "Let op: stam bevat een negatieve formulering — overweeg herschrijven").

---

## MODUS: REVIEW

Analyseer elk aangeleverd item systematisch op Item Writing Flaws (IWFs).
Gebruik de checklist hieronder. Geef per fout een **code**, **uitleg** en **verbetervoorstel**.

### IWF-checklist

| Code | Fout | Haladyna-regel |
|---|---|---|
| IWF-01 | Stam bevat niet het centrale idee | 15 |
| IWF-02 | Onnodige informatie in de stam (window dressing) | 16 |
| IWF-03 | Negatief geformuleerde stam zonder markering | 17 |
| IWF-04 | Meer dan één correct antwoord | 19 |
| IWF-05 | Geen enkel correct antwoord | 19 |
| IWF-06 | Opties overlappen inhoudelijk | 22 |
| IWF-07 | Opties niet homogeen (structuur of inhoud) | 23 |
| IWF-08 | Opties sterk wisselend in lengte | 24 |
| IWF-09 | "Alle bovenstaande" als optie | 26 |
| IWF-10 | Absolute termen in opties (altijd, nooit) | 28a |
| IWF-11 | Klankassociatie stam ↔ optie | 28b |
| IWF-12 | Grammaticale inconsistentie in opties | 28c |
| IWF-13 | Eén optie opvallend langer (bevat het antwoord) | 28d |
| IWF-14 | Ongeloofwaardige/absurde distractor | 28f / 29 |
| IWF-15 | Triviaal of niet-relevant voor leerdoel | 2 |
| IWF-16 | Strikvraag (misleidende formulering) | 7 |
| IWF-17 | Mening-gebaseerd item (geen verdedigbaar antwoord) | 6 |
| IWF-18 | Items inhoudelijk afhankelijk van elkaar | 4 |

### Reviewformat (per item)

```
**Review: Vraag [n]**

Gevonden flaws:
- [CODE] [naam fout]: [uitleg wat er mis is]

Herschreven versie:
[verbeterd item in volledig formaat]

Kwaliteitsoordeel: ✅ Goed / ⚠️ Aanpassen / ❌ Herschrijven
```

Als een item **geen flaws** heeft: geef een ✅ met een korte bevestiging.

---

## MODUS: ANALYSEER (Bloom)

Analyseer elk item op het **Bloom-niveau** van de cognitieve taxonomie (Anderson & Krathwohl, 2001).

### Bloom-niveaus — MCQ-toepassingen

| Niveau | Omschrijving | Signaalwerkwoorden | MCQ-voorbeeld |
|---|---|---|---|
| 1. Onthouden | Feiten, definities, termen reproduceren | noem, definieer, identificeer | "Wat is de definitie van een variabele?" |
| 2. Begrijpen | Uitleggen, samenvatten, classificeren | leg uit, beschrijf, vergelijk | "Wat bedoelt men met X?" |
| 3. Toepassen | Procedure uitvoeren in een nieuwe situatie | gebruik, bereken, schrijf | "Gegeven code X — wat is de uitvoer?" |
| 4. Analyseren | Onderdelen onderscheiden, oorzaken vinden | analyseer, onderscheid, waarom | "Welke fout zit er in dit algoritme?" |
| 5. Evalueren | Beoordelen op criteria | beoordeel, kies de beste, verdedig | "Welke aanpak is het meest geschikt en waarom?" |
| 6. Creëren | Ontwerpen, samenstellen (zeldzaam in MCQ) | ontwerp, stel op | Context-afhankelijke itemsets |

### Analyserapport

```
**Bloom-analyse: Vraag [n]**

Niveau: [1–6 + naam]
Reden: [waarom dit niveau — welke mentale handeling vraagt de stam?]
Aanbeveling: [is dit het gewenste niveau? Hoe hoger maken indien nodig?]
```

Geef bij een itemset ook een **verdeling** (bijv. tabel of percentages per niveau) en een aanbeveling
of de spreiding past bij het doel van de toets (summatief vs. formatief).

---

## Referenties

Voor uitgebreide toelichting op de 31 richtlijnen: zie `references/haladyna-31-guidelines.md`
Voor Bloom-tabel met werkwoorden: zie `references/bloom-mcq.md`

**Bronnen:**
- Haladyna, T.M., Downing, S.M., & Rodriguez, M.C. (2002). A review of multiple-choice item-writing guidelines for classroom assessment. *Applied Measurement in Education, 15*(3), 309–334.
- Rodriguez, M.C. (2005). Three options are optimal for multiple-choice items. *Educational and Psychological Measurement, 65*(3), 395–411.
- Downing, S.M. (2005). The effect of violating standard item writing principles on tests and students. *Medical Education, 39*, 1020–1026.
- AERA, APA, & NCME. (2014). *Standards for Educational and Psychological Testing.* Washington, DC.
- Anderson, L.W., & Krathwohl, D.R. (Eds.). (2001). *A Taxonomy for Learning, Teaching, and Assessing.* New York: Longman.
