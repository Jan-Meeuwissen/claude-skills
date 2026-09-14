---
name: maak-leeruitkomst
description: >
  Gebruik deze skill ALTIJD wanneer iemand een leeruitkomst wil opstellen, herformuleren, aanscherpen, beoordelen of vergelijken op basis van een of meer SBB-kwalificatiedossiers. Trigger bij het commando /maak-leeruitkomst, maar ook bij zinnen als "schrijf een leeruitkomst voor...", "herformuleer deze leeruitkomst", "is deze leeruitkomst Tuning-proof?", "maak een gedeelde leeruitkomst voor opleiding A en B", "welke overlap hebben deze kwalificaties?", "klopt het zelfstandigheidsniveau in deze leeruitkomst?" of "kunnen deze opleidingen samen een module volgen?". Trigger ook bij termen als leeruitkomst, leeruitkomsten, Tuning, Tuning-proof, flexibel onderwijs, gedeelde leeruitkomst, schijnoverlap, complexiteit en zelfstandigheid, of bij het koppelen van onderwijs aan kerntaken en werkprocessen. De skill werkt volgens de Tuning-formule (werkwoord + type + onderwerp + standaard + context), aangevuld met de SBB-velden complexiteit en verantwoordelijkheid/zelfstandigheid.
---

# Skill: maak-leeruitkomst

## Doel

Help een docent, onderwijskundige of opleidingsmanager bij het **opstellen, herformuleren en onderbouwen van leeruitkomsten** op basis van het SBB Kwalificatieregister. De skill is generiek: bruikbaar voor elke opleiding en voor elke vraag over (gedeelde) leeruitkomsten.

Een leeruitkomst wordt altijd geschreven volgens de **Tuning-standaard** (Deel A), aangevuld met de SBB-velden **complexiteit** en **verantwoordelijkheid en zelfstandigheid** (Deel B), en onderbouwd met de werkwijze in Deel C.

---

## Stap 0: Bepaal de route

Stel vast welke vraag er ligt. Vraag het na als het niet duidelijk is.

| Route | Vraag van de gebruiker | Volg |
|---|---|---|
| **1. Opstellen** | "Schrijf een leeruitkomst voor opleiding X over onderwerp Y" | C.1, C.2, C.4 (en C.5 voor het zelfstandigheidsniveau) |
| **2. Herformuleren of beoordelen** | "Herformuleer / beoordeel deze leeruitkomst" | Route 2 hieronder, daarna C.4 |
| **3. Gedeelde leeruitkomst of vergelijking** | "Maak een leeruitkomst voor opleiding A en B", "wat is de overlap?" | C.1 tot en met C.6 volledig |

Verzamel vóór het schrijven altijd:

- welke opleiding(en) het betreft (naam, crebonummer of dossiernummer);
- het onderwerp of thema van de leeruitkomst;
- bij route 2: de bestaande tekst van de leeruitkomst.

### Route 2: een bestaande leeruitkomst herformuleren of beoordelen

1. **Ontleed** de bestaande tekst in de vijf Tuning-elementen. Zet dit in een tabel:

   | Element | Wat staat er in de tekst | Beoordeling |
   |---|---|---|
   | Werkwoord | ... | aanwezig / vaag / ontbreekt |
   | Type | ... | ... |
   | Onderwerp | ... | ... |
   | Standaard | ... | ... |
   | Context | ... | ... |

2. **Toets** de tekst aan de Tuning-proof-criteria (zie Deel A). Benoem per criterium kort of de tekst eraan voldoet.
3. **Controleer het niveau**: past het zelfstandigheidsniveau in de tekst bij de velden "Complexiteit" en "Verantwoordelijkheid en zelfstandigheid" van de betrokken kerntaak (C.2 en C.5)?
4. **Stel een nieuwe formulering voor** en licht per wijziging toe waarom deze nodig is.
5. **Toets de nieuwe tekst** tegen het dossier (C.4).

---

## Deel A: De Tuning-standaard

De Tuning-methodiek (afkomstig uit het Europese Tuning Educational Structures-project, toegepast in het Nederlandse flexibele mbo en hbo) beschrijft een leeruitkomst met vijf elementen, in deze volgorde:

| Nr. | Element | Betekenis |
|---|---|---|
| 1 | **Werkwoord** | Actief, waarneembaar werkwoord (uit een taxonomie zoals Bloom) dat beschrijft wat je iemand ziet doen |
| 2 | **Type** | Welke competentie(s) of kwalificatie-eis het betreft |
| 3 | **Onderwerp** | Het deskundigheidsgebied of de inhoud waarop de leeruitkomst wordt toegepast |
| 4 | **Standaard** | De richtlijnen, methodiek of het niveau waaraan het resultaat wordt afgemeten |
| 5 | **Context** | De omstandigheden waarin het gedrag getoond wordt (inclusief scope en complexiteit) |

**Formule:** actief werkwoord + type + onderwerp + standaard + context

Schrijfregels:

- Schrijf een leeruitkomst als **doorlopende tekst**, in de **je-vorm**, gericht tot de student.
- Verwerk de vijf elementen **impliciet** in die tekst, niet als los rijtje.

Kwaliteitscriteria (**Tuning-proof**): een leeruitkomst is

- relevant;
- open;
- specifiek en meetbaar;
- duurzaam;
- samenhangend;
- onderscheidend;
- volledig.

---

## Deel B: Aanvulling vanuit de SBB-kwalificatiedossiers

Los van Tuning kennen SBB-kwalificatiedossiers per kerntaak een eigen, aanvullend format:

- **Complexiteit**: wat het werk lastig of veeleisend maakt (aard van de taken, vereiste kennis en vaardigheden, mate van onvoorspelbaarheid).
- **Verantwoordelijkheid en zelfstandigheid**: hoe zelfstandig iemand werkt, met wie en wanneer wordt afgestemd, en welke beslissingsbevoegdheid iemand wel of niet heeft.

Dit zijn geen Tuning-elementen, maar ze sluiten goed aan op het element **Context**. Gebruik ze altijd om het juiste niveau van zelfstandigheid in een leeruitkomst te formuleren.

---

## Deel C: Werkwijze

De stappen hieronder verwijzen naar de tools van de **SBB-MCP-server** (`sbb_...`). Zijn die tools niet beschikbaar, vraag de gebruiker dan om de relevante dossiertekst aan te leveren. Voor Software Developer, ICT support and systems en Medewerker ICT kun je ook de skills `lees-kd-sd`, `lees-kd-itss` en `lees-kd-itmw` gebruiken.

### C.1 Kwalificatie(s) opzoeken en geldigheid controleren

Tool: `sbb_opleiding_zoek` (op naam, crebonummer of dossiernummer).

Noteer per kwalificatie:

- crebonummer, dossiernaam, dossier-id en niveau;
- **diplomeren_tot**: de laatste datum waarop zittende studenten nog kunnen afronden;
- **inschrijven_tot**: de laatste datum waarop nieuwe studenten nog konden instromen.

Let op:

- Dit zijn **twee verschillende datums**. Een dossier kan al jaren gesloten zijn voor instroom en toch nog diplomeerbaar zijn voor zittende studenten.
- Controleer of de gevonden versie **op de datum van vandaag** nog geldig is. Is diplomeren_tot verstreken, dan is het dossier niet meer bruikbaar. Zoek dan de actuele opvolger, zo nodig opnieuw op de functietitel: er kan een nieuwer dossier met een ander crebonummer bestaan.

### C.2 Kerntaken en werkprocessen ophalen

Tool: `sbb_haal_op` (met `dossier_id`, eventueel `hoofdstuk` zoals `B1-K1`). Gebruik hiervoor **niet** `sbb_zoek`: die geeft alleen de meest verwante resultaten en laat er stilzwijgend weg. Staat in de uitvoer `volledig: false`, vraag dan opnieuw op met een hogere `limiet`.

Haal per kwalificatie de **volledige** set kerntaken en werkprocessen op. Leg per werkproces vast:

- omschrijving;
- resultaat;
- gedrag (dit vormt later de basis voor beoordelingscriteria).

Neem per kerntaak ook mee: het blok **Vakkennis en vaardigheden** en de tekstvelden **Complexiteit** en **Verantwoordelijkheid en zelfstandigheid** (Deel B).

### C.3 Overlap tussen opleidingen bepalen

Tools: `sbb_vergelijk_opleidingen` (precies twee opleidingen, uitputtend) of `sbb_overlap` (twee of meer opleidingen, eventueel binnen een thema). Gebruik `sbb_uitspraak_context` om een afzonderlijke uitspraak in zijn volledige context te lezen.

Onderscheid drie soorten uitkomsten:

1. **Letterlijk gedeeld**: identieke uitspraken in beide dossiers. De overlap staat dan vast.
2. **Kandidaat-gedeeld**: uitspraken met een hoge gelijkenisscore die inhoudelijk kunnen overeenkomen, maar dat niet per se doen. Behandel deze altijd als **hypothese, niet als bewijs**: lees de volledige tekst en beoordeel de betekenis (zie schijnoverlap in C.6).
3. **Uniek per opleiding**: wat alleen bij de ene of de andere opleiding hoort. Dit bepaalt wat als differentiatie moet blijven bestaan als opleidingen (deels) worden samengevoegd.

Ontbreekt letterlijke overlap volledig, dan is dat geen reden om te stoppen. Een gedeelde leeruitkomst kan ook gebaseerd zijn op een inhoudelijk **complementair** beroepsproces: de ene opleiding levert het ene deel van een gezamenlijk eindresultaat, de andere het andere deel. Tool: `sbb_team_samenstelling`.

### C.4 Leeruitkomst formuleren en toetsen

Tool: `sbb_dekking_toets` (concepttekst + opleiding(en), bij voorkeur met een `thema`).

1. Formuleer een concepttekst volgens de Tuning-formule (Deel A).
2. Leg de concepttekst naast de kerntaken en werkprocessen en bekijk welke uitspraken het dichtst in de buurt komen.

Let op:

- De scores zijn een maat voor **gelijkenis**, niet voor **dekking**. Een hoge score betekent niet automatisch dat de leeruitkomst het examenonderdeel volledig afdekt.
- Kijk ook naar wat **net naast** de formulering valt: uitspraken die dicht bij het thema liggen maar door de huidige tekst niet geraakt worden. Is dat een bewuste keuze of een omissie? Leg dit voor aan de gebruiker.

### C.5 Zelfstandigheid vergelijken en samenvoegen

Zet de teksten "Verantwoordelijkheid en zelfstandigheid" van de betrokken kerntaken naast elkaar en vergelijk op minimaal deze dimensies:

| Dimensie | Opleiding A | Opleiding B |
|---|---|---|
| Basishouding (zelfstandig of onder begeleiding) | | |
| Overleg- en afstemmomenten (met wie, wanneer, op wiens initiatief) | | |
| Verantwoordelijkheid (waarvoor is de deelnemer verantwoordelijk) | | |
| Beslissingsbevoegdheid (wat mag de deelnemer zelf beslissen, wat niet) | | |
| Professionalisering en reflectie (apart werkproces of impliciet) | | |

Formuleer op basis hiervan een **synthese**: een zelfstandigheidsniveau dat voor beide opleidingen recht doet aan de brondossiers en bruikbaar is als gemeenschappelijk uitgangspunt, ook als de formulering in de dossiers zelf niet identiek is.

### C.6 Kennis, vaardigheden en gedrag ordenen, met toetsing op betekenis

Orden de kennis-, vaardigheids- en gedragsitems uit de betrokken kerntaken per thema. Gebruik in de kolom **Relatie** altijd een van deze woorden (geen symbolen of emoji):

| Relatie | Betekenis |
|---|---|
| **Overlap** | Zelfde betekenis en zelfde niveau |
| **Gedeeltelijke overlap** | Zelfde domein of thema, maar andere diepgang of functie |
| **Schijnoverlap** | Zelfde term of woord, maar een andere betekenis in elk dossier |
| **Uniek A** | Komt alleen voor bij opleiding A |
| **Uniek B** | Komt alleen voor bij opleiding B |

**Sjabloon:**

| Thema | Opleiding A | Opleiding B | Relatie |
|---|---|---|---|
| ... | ... | ... | Overlap / Gedeeltelijke overlap / Schijnoverlap / Uniek A / Uniek B |

**Schijnoverlap** is de belangrijkste valkuil bij het samenvoegen van kwalificaties: eenzelfde woord (bijvoorbeeld "markt", "kwaliteit", "plan" of "concept") kan in twee vakgebieden een wezenlijk andere lading hebben. Neem zulke termen nooit over als "gedeelde kennis" zonder de volledige brontekst te lezen.

**Gebruik van de uitkomst:**

- **Overlap** (en delen van **gedeeltelijke overlap**) vormt de stevigste basis voor gezamenlijk aangeboden leerstof.
- **Uniek A**, **Uniek B** en de uit elkaar getrokken **schijnoverlap**-items blijven apart per opleiding.

---

## Deel D: Aandachtspunten en valkuilen

Benoem deze punten in het antwoord wanneer ze spelen:

- **Geldigheid van dossiers**: controleer diplomeren_tot altijd tegen de huidige datum voordat een leeruitkomst wordt vastgesteld. Een verlopen dossier levert een leeruitkomst op die niet meer ingezet kan worden.
- **Instroomstatus**: is inschrijven_tot verstreken, dan is de leeruitkomst alleen nog bruikbaar voor lopende cohorten, niet voor nieuwe instroom.
- **Validatie door examencommissies**: een inhoudelijk geconstrueerde overlap (op basis van aanvulling of gelijkenis) is geen automatisch geldige koppeling in een examenplan. Laat de onderbouwing, en zeker de schijnoverlap-items, formeel valideren door de betrokken examencommissies voordat de leeruitkomst wordt vastgesteld.
- **Leeruitkomst versus gedeeld leertraject**: dit zijn twee aparte beslissingen. Een leeruitkomst geldt altijd zelfstandig per kwalificatie. Of twee of meer opleidingen vervolgens hetzelfde leertraject, vak of dezelfde module volgen (eventueel met gemengde groepen) is een didactische keuze, geen inhoudelijke noodzaak.
- **Scores zijn indicatief, geen bewijs**: elke gelijkenisscore uit het register (bij vergelijken, overlap zoeken of een concept toetsen) helpt sneller zoeken, maar garandeert geen inhoudelijke dekking. Lees de volledige brontekst voordat je een conclusie trekt.
- **Dossierherziening**: is een kwalificatiedossier herzien, gebruik dan `sbb_bewaking` om te zien welke eerder vastgelegde leeruitkomsten steunen op gewijzigde of verdwenen uitspraken.

---

## Opbouw van het antwoord

Lever bij een nieuwe of herschreven leeruitkomst:

1. **De leeruitkomst**: doorlopende tekst in de je-vorm.
2. **Tuning-verantwoording**: tabel met per element (werkwoord, type, onderwerp, standaard, context) welk deel van de tekst het invult.
3. **Bronnen**: per gebruikte uitspraak de dossiernaam, hoofdstukcode (bijvoorbeeld B1-K1-W2), crebonummer(s) en diplomeren_tot.
4. **Zelfstandigheid**: welk niveau is gekozen en waarop dat is gebaseerd (C.5).
5. **Wat net naast valt**: uitspraken die de tekst niet raakt, met de vraag of dat bewust is (C.4).
6. **Aandachtspunten**: relevante punten uit Deel D, zoals geldigheid of validatie door de examencommissie.

Bij een vergelijking van opleidingen komen daar de tabellen uit C.5 en C.6 bij.

---

## Bronnen

- SBB Kwalificatieregister (kerntaken, werkprocessen, kennis en vaardigheden, gedrag, complexiteit en zelfstandigheid per kwalificatiedossier).
- Ontwerpkaders Leeruitkomsten, versie 1.0, november 2016 (NHL Stenden Innovation Lab).
- Kwaliteitseis Tuning-proof (NHL Stenden Innovation Lab).
- Beschrijven van leeruitkomsten (Hogeschool Utrecht, Toetsing).
