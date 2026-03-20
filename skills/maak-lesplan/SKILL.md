---
name: maak-lesplan
description: >
  Gebruik deze skill altijd wanneer een docent een volledig lesplan wil maken via een begeleide workflow.
  De skill doorloopt acht stappen: het kwalificatiedossier lezen (sbb-kd-sd), de teamvisie lezen
  (lees-visie), een instructiemodel kiezen (lees-dim), de lescontext vastleggen (lescontext-sd),
  lesdoelen en onderwerp invoeren, voorkennis en vorige les bespreken, het lesplan genereren en
  opslaan, en optioneel hulpmiddelen maken.
  Trigger bij commando's als "/maak-lesplan", "maak een lesplan", "begeleid me bij het maken
  van een les", "stap voor stap een les maken", of wanneer een docent begeleiding wil bij
  lesvoorbereiding in de Software Developer opleiding.
  Voer de stappen ALTIJD één voor één uit en vraag bij elke stap bevestiging voordat je verdergaat.
---

# Skill: maak-lesplan (begeleide stap-voor-stap aanpak)

## Doel

Deze skill begeleidt een docent stap voor stap door het maken van een lesplan. Elke stap bouwt
voort op de vorige. Sla geen stappen over. Vraag bij elke stap expliciet om bevestiging voordat
je verdergaat naar de volgende stap.

---

## Werkwijze

### Algemene regels

- Voer **één stap per keer** uit.
- **Vraag altijd bevestiging** aan het einde van elke stap voordat je doorgaat.
- Geef bij stappen met keuzes altijd een **duidelijk keuzemenu** (gebruik de `ask_user_input_v0` tool).
- Sla de verzamelde informatie op in een **werkgeheugen-blok** dat je bijhoudt en aan het begin
  van elke volgende stap kort samenvat.
- Gebruik een **vriendelijke, collegiale toon** in het Nederlands.

---

## De acht stappen

### Stap 1 — Kwalificatiedossier lezen (`/sbb-kd-sd`)

**Wat je doet:**
Lees de inhoud van het SBB Kwalificatiedossier Software Developer via de `sbb-kd-sd` skill.
Presenteer aan de docent:
- De twee kerntaken (B1-K1 en B1-K2) met een korte toelichting per kerntaak.
- De werkprocessen per kerntaak (B1-K1-W1 t/m W5, B1-K2-W1 t/m W3).
- Een korte uitleg van wat gedragsindicatoren zijn en waarom ze belangrijk zijn voor lesontwerp.

**Doel voor de docent:** Bewustzijn van de beroepscontext waarbinnen de les plaatsvindt.

**Afsluiting:** Vraag of de docent meer wil weten over een specifiek werkproces, of bevestiging
om door te gaan naar stap 2.

---

### Stap 2 — Teamvisie lezen (`/lees-visie`)

**Wat je doet:**
Lees de teamvisie via de `lees-visie` skill. Presenteer aan de docent de kernpunten van de
onderwijsvisie van het ICT-team Software Developer van ROC Nijmegen, met aandacht voor:
- De visie op leren en de leeromgeving
- De begeleidingsfilosofie en talentontwikkeling
- Betekenisvol en contextrijk onderwijs
- Zelfregulering van studenten

**Doel voor de docent:** De les die straks gemaakt wordt sluit aan op de gedeelde visie van het team.
Gebruik de visie later in het lesplan als verantwoording voor werkvormen en keuzes.

**Sla op in werkgeheugen:** relevante visie-principes die van toepassing zijn op deze les.

**Afsluiting:** Vraag bevestiging om door te gaan naar stap 3.

---

### Stap 3 — Instructiemodel kiezen (`/lees-dim`)

**Wat je doet:**
Lees de inhoud van de `lees-dim` skill. Presenteer de beschikbare instructiemodellen als keuzemenu:

| Model | Kernkenmerk |
|-------|-------------|
| **EDI** | Expliciete leerdoelen, kleine lesafsluiting, controle van begrip als rode draad |
| **DIM** | Klassiek directe instructie, sterk leraargestuurd, stapsgewijze opbouw |
| **ADI** | Meer interactie, sociaal-constructivistisch element |
| **IGDI** | Convergente differentiatie; minimale doelen voor alle leerlingen |
| **GRR** | Geleidelijke overdracht van verantwoordelijkheid (Ik → Wij → Jullie → Jij) |

Geef bij elk model een korte uitleg (2-3 zinnen) zodat de docent een weloverwogen keuze kan maken.

**Sla op in werkgeheugen:** gekozen model.

**Afsluiting:** Bevestiging vragen om door te gaan naar stap 4.

---

### Stap 4 — Lescontext vastleggen (`/lescontext-sd`)

**Wat je doet:**
Lees de inhoud van de `lescontext-sd` skill. Presenteer de **vaste context** (lokaal, opleiding,
doelgroep, apparatuur, interesses) en vraag de **variabele parameters** op via een keuzemenu:

- **Groepsgrootte:** 10–15 / 15–20 / 20–25 studenten
- **Lesduur:** 30 / 60 / 90 / 120 minuten
- **Leerjaar:** 1 / 2 / 3 / 4

Toon daarna een bevestigingsoverzicht van de volledige lescontext (vast + variabel).

Geef de docent **de optie om de context aan te passen** voordat je verdergaat.

**Sla op in werkgeheugen:** groepsgrootte, lesduur, leerjaar, stage-ervaring.

**Afsluiting:** Bevestiging vragen (inclusief optie "Ik wil de context aanpassen") om door te gaan
naar stap 5.

---

### Stap 5 — Lesdoelen en/of onderwerp invoeren

**Wat je doet:**
Vraag de docent naar:
1. **Het onderwerp** van de les (vrije invoer).
2. **De lesdoelen** — formuleer ze bij voorkeur als: *"Aan het einde van de les kun jij..."*
   (Geef een voorbeeld passend bij het gekozen instructiemodel en het KD.)

Als de docent alleen een onderwerp geeft maar geen lesdoelen, help dan actief bij het formuleren
van 1–3 concrete, meetbare lesdoelen op basis van het KD en het gekozen model.

Koppel de lesdoelen expliciet aan een werkproces uit het KD (bijv. B1-K1-W3).

**Sla op in werkgeheugen:** onderwerp, lesdoelen, KD-koppeling.

**Afsluiting:** Toon een samenvatting van onderwerp + lesdoelen en vraag bevestiging voor stap 6.

---

### Stap 6 — Voorkennis en vorige les

**Wat je doet:**
Stel de volgende vragen (bij voorkeur tegelijk via een widget):

1. **Wat weten studenten al?** (voorkennis relevant voor dit onderwerp)
2. **Wat is er in de vorige les behandeld?** (of: is er een lesplan van de vorige les beschikbaar?)
3. **Zijn er studenten die extra ondersteuning nodig hebben?** (optioneel, voor differentiatie)

Gebruik de antwoorden later in het lesplan bij de fase *Activatie van voorkennis* (EDI/DIM)
of de *Terugblik* (DIM fase 1 / Rosenshine).

**Sla op in werkgeheugen:** voorkennis, vorige les, differentiatiebehoefte.

**Afsluiting:** Bevestiging vragen om door te gaan naar de laatste stap.

---

### Stap 7 — Lesplan genereren

**Wat je doet:**
Genereer een volledig lesplan op basis van alle verzamelde informatie:

```
LESCONTEXT (werkgeheugen):
- KD-koppeling: [werkproces + gedragsindicatoren]
- Instructiemodel: [gekozen model]
- Groepsgrootte / lesduur / leerjaar: [waarden]
- Onderwerp: [onderwerp]
- Lesdoelen: [geformuleerde doelen]
- Voorkennis: [samenvatting]
- Vorige les: [samenvatting]
```

**Hulpmiddelen**

Elk lesplan vermeldt altijd welke hulpmiddelen worden ingezet. Sommige zijn verplicht, andere optioneel:

| Hulpmiddel | Wanneer | Omschrijving |
|------------|---------|--------------|
| **Presentatie** | Altijd | Gebruikt door de docent tijdens de les; bevat de kern van de lesstof zodat studenten er later in kunnen terugvinden. |
| **Lesopdracht** | Altijd | De centrale werkopdracht die studenten (zelfstandig of samen) uitvoeren. |
| **Oefening** | Optioneel | Extra oefenmateriaal, bijv. voor begeleide of zelfstandige inoefening. |
| **Diagnostische toets** | Optioneel | Korte toets om te checken of het lesdoel behaald is (bijv. als kleine lesafsluiting bij EDI). |

Benoem in het lesplan bij elke fase **welk hulpmiddel** op dat moment gebruikt wordt.
Noteer ook welke hulpmiddelen voor deze les gemaakt moeten worden (altijd presentatie +
lesopdracht; oefening en/of diagnostische toets indien van toepassing).

> 💡 Voor het daadwerkelijk uitwerken van deze hulpmiddelen bestaan aparte skills
> (presentatie-skill, lesopdracht-skill, oefening-skill, diagnostische-toets-skill).
> Het lesplan verwijst naar deze skills maar voert ze nog niet uit.

**Structuur van het lesplan** (pas aan op gekozen model):

| Fase | Tijd | Activiteit | Werkvorm | Hulpmiddel |
|------|------|------------|----------|------------|
| Terugblik / voorkennis activeren | ... | ... | ... | — |
| Lesdoel presenteren | ... | ... | ... | Presentatie |
| Instructie / modeling | ... | ... | ... | Presentatie |
| Begeleide inoefening | ... | ... | ... | Oefening (opt.) |
| Kleine lesafsluiting (EDI) | ... | ... | ... | Diagnostische toets (opt.) |
| Zelfstandige verwerking | ... | ... | ... | Lesopdracht |
| Verlengde instructie (indien nodig) | ... | ... | ... | Oefening (opt.) |
| Afsluiting / reflectie | ... | ... | ... | — |

Sluit het lesplan af met een **overzicht van benodigde hulpmiddelen**:

```
📦 BENODIGDE HULPMIDDELEN
─────────────────────────────────
✅ Presentatie     : [werktitel / korte omschrijving]
✅ Lesopdracht     : [werktitel / korte omschrijving]
☐  Oefening       : [wel/niet nodig — toelichting]
☐  Diag. toets    : [wel/niet nodig — toelichting]
```

Gebruik bij voorbeelden en contexten de interesses van de doelgroep (gamen, software bouwen).
Zorg dat het plan direct bruikbaar is in de klas.

**Opslaan als bestand**

Nadat het lesplan is goedgekeurd, vraag je de docent in welk formaat het opgeslagen moet worden:

| Formaat | Wanneer kiezen |
|---------|----------------|
| **Word (.docx)** | Standaardkeuze — makkelijk aan te passen in Word of Google Docs |
| **HTML (.html)** | Handig om te delen via een browser of intranet |
| **Markdown (.md)** | Voor gebruik in een kennisbank, GitHub of Notion |

Lees altijd eerst de ROC Nijmegen huisstijl via `/mnt/skills/user/roc-nijmegen-brand-guide/SKILL.md`
voordat je het bestand genereert. Pas kleuren, typografie, logo-gebruik en tone of voice toe
zoals beschreven in die skill.

Genereer daarna het bestand in het gekozen formaat:

- **docx** → gebruik de `docx` skill. Lees `/mnt/skills/public/docx/SKILL.md` voor aanvang.
  Pas de ROC huisstijl toe op kopteksten, kleuraccenten en lettertype.
- **html** → genereer een op zichzelf staande HTML-pagina met inline CSS op basis van de ROC huisstijl.
- **md** → genereer een overzichtelijk Markdown-document. Voeg een ROC-header toe (naam, opleiding, logo-verwijzing).

Sla het bestand op als `lesplan-[onderwerp]-[datum].docx/html/md` in `/mnt/user-data/outputs/`
en bied het aan via `present_files`.

**Afsluiting:** Bied de docent het bestand aan en vraag of er nog aanpassingen nodig zijn.

---

### Stap 8 — Hulpmiddelen maken (optioneel)

**Wat je doet:**
Vraag de docent welke hulpmiddelen nu uitgewerkt moeten worden. Toon het overzicht van benodigde
hulpmiddelen uit het gegenereerde lesplan als checklist en laat de docent kiezen.

**Keuzemenu** (meerdere opties mogelijk):

| Hulpmiddel | Skill | Wanneer |
|------------|-------|---------|
| **Presentatie** | `maak-presentatie` | Altijd beschikbaar |
| **Lesopdracht** | `maak-opdracht` | Altijd beschikbaar |
| **Oefening** | `maak-oefening` | Altijd beschikbaar |
| **Diagnostische toets** | `maak-toets20mc` | Altijd beschikbaar |
| Nog niet — ik doe dit later | — | — |

Voor elk gekozen hulpmiddel:
1. Lees de betreffende skill (`/mnt/skills/user/[skill-naam]/SKILL.md`).
2. Geef het volledige werkgeheugen van het lesplan mee als startcontext, zodat het hulpmiddel
   direct aansluit op het onderwerp, de lesdoelen, de lescontext en het gekozen instructiemodel.
3. Voer de skill uit volgens haar eigen instructies.
4. Sla het resultaat op in ROC huisstijl (lees `roc-nijmegen-brand-guide`) en bied het aan via `present_files`.

Als de docent meerdere hulpmiddelen wil: maak ze één voor één, met bevestiging na elk hulpmiddel.

**Afsluiting:** Geef een overzicht van alles wat er in deze sessie gemaakt is:
lesplan + alle gegenereerde hulpmiddelen, elk als downloadbaar bestand.

---

## Werkgeheugen-template

Houd dit blok bij en toon het (verkort) aan het begin van elke stap:

```
📋 WERKGEHEUGEN LESPLAN-WORKFLOW
─────────────────────────────────
KD-koppeling   : [nog niet ingevuld]
Visie-principes: [nog niet ingevuld]
Model          : [nog niet gekozen]
Groepsgrootte  : [nog niet ingevuld]
Lesduur        : [nog niet ingevuld]
Leerjaar       : [nog niet ingevuld]
Onderwerp      : [nog niet ingevuld]
Lesdoelen      : [nog niet ingevuld]
Voorkennis     : [nog niet ingevuld]
Vorige les     : [nog niet ingevuld]
```

---

## Afhankelijkheden

Deze skill maakt gebruik van vier andere skills. Lees ze op het juiste moment:

| Stap | Skill | Leesmoment |
|------|-------|------------|
| 1 | `sbb-kd-sd` → `references/kd-software-developer.md` | Bij aanvang stap 1 |
| 2 | `lees-visie` | Bij aanvang stap 2 |
| 3 | `lees-dim` | Bij aanvang stap 3 |
| 4 | `lescontext-sd` | Bij aanvang stap 4 |
| 7 | `roc-nijmegen-brand-guide` | Voor het genereren van het bestand |
| 7 | `docx` (indien docx gekozen) | Voor het genereren van het bestand |
| 8 | `maak-presentatie` (indien gekozen) | Bij aanvang hulpmiddel |
| 8 | `maak-opdracht` (indien gekozen) | Bij aanvang hulpmiddel |
| 8 | `maak-oefening` (indien gekozen) | Bij aanvang hulpmiddel |
| 8 | `maak-toets20mc` (indien gekozen) | Bij aanvang hulpmiddel |
