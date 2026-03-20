---
name: skill-index
description: >
  Gebruik deze skill altijd als eerste stap wanneer je een taak uitvoert
  waarvoor gespecialiseerde kennis nodig is. Deze skill bevat een overzicht
  van alle beschikbare skills op de server en laadt de juiste skill dynamisch
  in op basis van de taak.
---

# Skill index

Je hebt toegang tot een dynamische skill-bibliotheek op GitHub.

## Werkwijze

### Stap 1 — Haal het manifest op

Gebruik `web_fetch` om het manifest op te halen:

```
https://raw.githubusercontent.com/Jan-Meeuwissen/claude-skills/main/index.json
```

### Stap 2 — Kies de juiste skill

Lees de `description` en `tags` van elke skill in het manifest.
Kies de skill die het beste past bij de taak van de gebruiker.

### Stap 3 — Laad de skill in

Gebruik `web_fetch` op de `url` van de gekozen skill om de SKILL.md op te halen.
Volg daarna de instructies in die skill.

### Stap 4 — Geef een overzicht op verzoek

Als de gebruiker vraagt welke skills beschikbaar zijn, geef dan een overzicht
op basis van het manifest — zonder elke skill apart in te laden.

## Regels

- Haal het manifest op aan het begin van elke relevante sessie.
- Laad alleen de skill(s) in die daadwerkelijk nodig zijn.
- Als geen enkele skill van toepassing is, ga dan gewoon door zonder skill.
