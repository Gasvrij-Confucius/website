# Website Confuciusbuurt & Noorderhof-Noord Aardgasvrij

Deze handleiding is voor webredacteuren die de site beheren via GitHub.

## Hoe werkt het?

1. Je bewerkt of voegt bestanden toe in GitHub
2. Netlify detecteert de wijziging automatisch
3. De site wordt opnieuw gebouwd (~1-2 minuten)
4. Wijzigingen zijn live op de website: [confucius-en-noorderhof.netlify.app](https://confucius-en-noorderhof.netlify.app) 

## Mappenstructuur

```
content/                    ← HIER WERK JE
├── _index.md              ← Homepage tekst
├── contact.md             ← Contact pagina
├── faq.md                 ← Veelgestelde vragen
├── nieuws/                ← Nieuwsberichten
│   ├── _index.md          ← Intro tekst nieuwspagina
│   └── *.md               ← Individuele berichten
└── documenten/            ← Documenten/presentaties
    ├── _index.md          ← Intro tekst documentenpagina
    └── *.md               ← Individuele documenten

static/                     ← BESTANDEN (afbeeldingen, PDF's)
├── images/                ← Afbeeldingen
└── documenten/            ← PDF bestanden

layouts/                    ← NIET AANRAKEN (technisch)
hugo.toml                   ← Site instellingen (menu, titel)
```

---

## Content bewerken

### Bestaande pagina aanpassen

1. Navigeer naar het bestand (bijv. `content/faq.md`)
2. Klik op het **potlood-icoon** (rechtsboven)
3. Pas de tekst aan
4. Klik "Commit changes" (groene knop)
5. Wacht ~1-2 minuten, dan is het live

### Markdown opmaak

```markdown
# Grote kop
## Subkop
### Kleinere kop

Gewone tekst. **Vetgedrukt** en *cursief*.

- Opsomming punt 1
- Opsomming punt 2

1. Genummerde lijst
2. Tweede item

[Link tekst](https://example.com)

![Afbeelding alt tekst](/images/bestandsnaam.jpg)
```

---

## Nieuwsbericht toevoegen

1. Ga naar `content/nieuws/`
2. Klik "Add file" → "Create new file"
3. Bestandsnaam: `titel-van-bericht.md` (kleine letters, streepjes)
4. Plak deze template:

```markdown
---
title: "Titel van je bericht"
date: 2026-01-31
---

Hier schrijf je de inhoud van het nieuwsbericht.

### Tussenkopje

Meer tekst, eventueel met **vetgedrukt** of een [link](https://example.com).
```

5. Klik "Commit new file"

**Let op:** De `date` moet vandaag of in het verleden zijn, anders wordt het bericht niet getoond.

---

## Document/presentatie toevoegen

### Stap 1: Upload de PDF

1. Ga naar `static/documenten/`
2. Klik "Add file" → "Upload files"
3. Sleep je PDF naar het venster
4. Klik "Commit changes"

### Stap 2: Maak een pagina aan

1. Ga naar `content/documenten/`
2. Klik "Add file" → "Create new file"
3. Bestandsnaam: `titel-document.md`
4. Plak deze template:

```markdown
---
title: "Presentatie Buurtavond Februari 2026"
date: 2026-02-15
pdf: "/documenten/presentatie-feb-2026.pdf"
---

Korte beschrijving van het document.

## Belangrijkste punten

- Punt 1
- Punt 2
- Punt 3
```

5. Klik "Commit new file"

---

## Afbeelding toevoegen

### Uploaden

1. Ga naar `static/images/`
2. Klik "Add file" → "Upload files"
3. Sleep je afbeelding naar het venster
4. Klik "Commit changes"

### Gebruiken in een pagina

```markdown
![Beschrijving van de afbeelding](/images/bestandsnaam.jpg)
```

---

## Menu aanpassen

Het menu wordt beheerd in `hugo.toml`.

```toml
[[menu.main]]
  name = 'Home'
  url = '/'
  weight = 1
```

- `name` = Tekst in het menu
- `url` = Link (bijv. `/nieuws/`)
- `weight` = Volgorde (lager = eerder)

---

## Veelvoorkomende taken

| Taak | Waar | Bestand |
|------|------|---------|
| Homepage aanpassen | `content/` | `_index.md` |
| FAQ bewerken | `content/` | `faq.md` |
| Nieuwsbericht toevoegen | `content/nieuws/` | Nieuw `.md` bestand |
| Document toevoegen | `static/documenten/` + `content/documenten/` | PDF + `.md` bestand |
| Menu aanpassen | root | `hugo.toml` |

---

## Tijdlijn wijzigingen

| Actie | Tijd |
|-------|------|
| Bestand opslaan in GitHub | Direct |
| Netlify start build | ~10 seconden |
| Build voltooid | ~1 minuut |
| Live op website | ~1-2 minuten totaal |

Je kunt de voortgang volgen op [app.netlify.com](https://app.netlify.com) onder "Deploys".

---

## Problemen?

### Wijziging niet zichtbaar
- Wacht 2 minuten en ververs de pagina (Cmd+Shift+R)
- Check Netlify dashboard voor foutmeldingen

### Nieuwsbericht verschijnt niet
- Controleer of de `date` niet in de toekomst ligt
- Controleer of de bestandsnaam eindigt op `.md`

### Afbeelding laadt niet
- Controleer het pad (moet beginnen met `/images/`)
- Controleer of de bestandsnaam exact overeenkomt (hoofdlettergevoelig)

---

## Hulp

- Markdown uitleg: [markdownguide.org](https://www.markdownguide.org/basic-syntax/)
- Of vraag in de buurt-appgroep
