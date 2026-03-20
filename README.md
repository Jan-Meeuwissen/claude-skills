# Claude Skills — Jan Meeuwissen

Skills library voor Claude, gehost op GitHub.

## Structuur

```
claude-skills/
├── index.json                         # Manifest van alle beschikbare skills
├── skills/
│   ├── index/
│   │   └── SKILL.md                   # Index skill (altijd geladen in Claude)
│   └── schrijfstijl-beleid/
│       └── SKILL.md                   # Schrijfstijl voor ROC Nijmegen
└── .github/
    └── workflows/
        └── validate.yml               # Automatische validatie bij elke push
```

## Een skill toevoegen

1. Maak een nieuwe map aan onder `skills/`:
   ```bash
   mkdir skills/naam-van-skill
   ```

2. Maak een `SKILL.md` aan met frontmatter:
   ```markdown
   ---
   name: naam-van-skill
   description: >
     Wanneer moet Claude deze skill inzetten?
   ---

   # Inhoud van de skill
   ...
   ```

3. Voeg de skill toe aan `index.json`.

4. Push naar GitHub:
   ```bash
   git add .
   git commit -m "skill: naam-van-skill toegevoegd"
   git push
   ```

De GitHub Action valideert automatisch of alles klopt.

## Raw URLs

Bestanden zijn direct op te halen via:
```
https://raw.githubusercontent.com/Jan-Meeuwissen/claude-skills/main/index.json
https://raw.githubusercontent.com/Jan-Meeuwissen/claude-skills/main/skills/NAAM/SKILL.md
```
