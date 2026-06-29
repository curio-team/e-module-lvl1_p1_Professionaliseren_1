# E-module Template

Een startpunt voor interactieve e-modules, gebouwd met [`@curio-sd/e-module-builder`](https://github.com/curio-team/e-module-builder).

Dit template bevat een volledig uitgewerkt voorbeeld over **CSS Grid**
in de `content/` map. Verwijder of vervang die inhoud om je eigen module
te maken.

## Snel starten

1. Gebruik dit repository als template (klik **Use this template** op GitHub).
    * Kies de [`curio-lesmateriaal` organisatie](https://github.com/curio-lesmateriaal)
    als eigenaar.
    * Kies een naam als: `e-module-lvl{level}_p{periode}_{Naam}`, bijv.: `e-module-lvl1_p2_Inlogsystemen`.

2. Deze e-modules werken met GitHub Pages. Ga in de instellingen van je nieuwe
    repository naar **Settings → Pages** en stel de **Source** in op **GitHub Actions**.

    > [!NOTE]
    > De eerste GitHub workflow run zal falen, omdat GitHub Pages nog niet is ingesteld.

3. Installeer de afhankelijkheden:

   ```bash
   npm install
   npm run dev
   ```

4. Open [http://localhost:5173](http://localhost:5173) in je browser.

5. Pas de inhoud in de `content/` map aan — zie [Content bewerken](#content-bewerken).

6. Als laatste stap is het netjes om de README aan te passen. Haal alles omtrent de template weg en leg kort uit waar de e-module over gaat.

## E-module schrijven met AI

Zodra je repository klaarstaat, kun je een AI-agent (zoals Claude Code, GitHub Copilot of Cursor) de `content/` map laten vullen. Voeg je bronbestanden toe aan de repository (of sleep ze in de chat) en gebruik een van de onderstaande prompts als startpunt. Pas de cursieve onderdelen aan voor jouw situatie.

> [!TIP]
> Gebruik bij voorkeur de **Plan Mode** van de AI-agent voordat deze aan het werk gaat. In Plan Mode stelt de agent eerst een plan op dat jij kunt controleren en bijsturen — zonder dat er al bestanden worden aangemaakt of gewijzigd. In Claude Code schakel je dit in met `/plan`. Zo voorkom je dat de agent een verkeerde richting inslaat die je daarna moet terugdraaien.

### Scenario 1 — Bestaand Word document omzetten

Gebruik dit als je één Word-document hebt met de module-inhoud en dat wilt omzetten naar het e-module formaat.

> Please help rewrite our current Word document (*lvl1_p2_module_Inlogsystemen_v1.docx*) into our `content/` folder as a module for '*Inlogsystemen (in PHP)*', which is a Dutch e-module. The current `content/` is just an example (CSS Grid), which can go. The README explains more on how to write this e-module. The Word document might be missing elements that are required for the e-module — write those. Ensure the e-module works independently. For turning in assignments you may direct to Itslearning, which is where students turn in assignments for feedback by the teacher.

### Scenario 2 — Meerdere bronbestanden samenvoegen

Gebruik dit als je meerdere versies of gerelateerde documenten hebt (bijv. een oud Word-document, een conceptversie, slides of aantekeningen) en daar één nieuwe e-module van wilt maken.

> Please create a new Dutch e-module for '*Inlogsystemen (in PHP)*' in our `content/` folder. I'm providing multiple source documents: *module_v1.docx (original), module_v2_draft.docx (partial rewrite), slides_week3.pdf*. The current `content/` is just an example (CSS Grid) and can be removed. Use the README for the required file structure and frontmatter fields. Merge the best parts from all sources, resolve any contradictions by keeping the most recent or most complete version, and fill in any gaps required by the e-module format. Make sure every week has theory, a quiz, exercises, and an assignment. Students submit assignments via Itslearning.

## Commando's

| Commando | Omschrijving |
| --- | --- |
| `npm run dev` | Start de ontwikkelserver op `localhost:5173` |
| `npm run build` | Productie-build naar `dist/` |
| `npm run preview` | Preview van de `dist/` build lokaal |

## Content bewerken

Alleen de `content/` map hoef je te bewerken. De rest wordt automatisch gegenereerd.

```text
content/
  module.md             ← module-metadata (naam, weken, taal, oefenmodus)
  week1/
    exercises/          ← oefeningen
      _meta.md          ← oefening-metadata (week, titel, kleur)
      #.md              ← oefening 1, 2, 3, ...
    theory.md           ← theorie (YAML frontmatter met sections[])
    quiz.md             ← tussentoets vragen
    assignment.md       ← inleveropdracht
  week2/ … weekN/       ← zelfde structuur
  assessments/
    theory-assessment.md      ← eindtoets theorie (optioneel)
    practical-assessment.md   ← eindtoets praktijk (optioneel)
```

### `content/module.md`

```yaml
---
name: Naam van je module
subtitle: E-module
weeks: 4
language: nl
exerciseMode: interactive   # of: external
description: Korte omschrijving van de module.
youtube: https://www.youtube.com/watch?v=...
logoAlt: Alternatieve tekst voor het module-logo
algemeen:
  - Ik kan ...
---
```

| Veld | Verplicht | Omschrijving |
| ---- | --------- | ------------ |
| `name` | ja | Naam van de module |
| `weeks` | ja | Aantal weken (bepaalt welke `weekN/` mappen worden verwerkt) |
| `exerciseMode` | ja | `interactive` (Monaco editor) of `external` (link naar extern) |
| `language` | nee | Taal van de UI, standaard `nl` |
| `subtitle` | nee | Getoond onder de titel |
| `description` | nee | Korte omschrijving van de module |
| `youtube` | nee | URL van een intro-video |
| `logoAlt` | nee | Alternatieve tekst voor het module-logo |
| `algemeen` | nee | Algemene leeruitkomsten toegevoegd aan de checklist |

### `content/weekN/theory.md`

YAML frontmatter + Markdown body. De body ondersteunt standaard Markdown,
syntax-highlighted codeblokken en custom elementen (zie
[Custom elementen in Markdown](#custom-elementen-in-markdown)).

```yaml
---
week: 1
title: Titel van de week
goal: Wat de student aan het einde van deze week kan.
accent: indigo
summary: Korte samenvatting getoond op de startpagina.
leeruitkomsten:
  - Ik kan ...
---

Markdown-inhoud hier...
```

### `content/weekN/quiz.md`

```yaml
---
title: Tussentoets Week 1
passScore: 70
questions:
  - id: q1
    question: Vraag?
    options:
      - Antwoord A
      - Antwoord B
    correct: 1
    explanation: Uitleg waarom dit correct is.
---
```

### `content/weekN/assignment.md`

De Markdown **body** wordt gesplitst op een lege regel: de eerste alinea
wordt de `case`, de rest de opdrachtomschrijving.

```yaml
---
week: 1
title: Bouw een pagina-layout
subtitle: Praktische opdracht
deliverables:
  - Een werkende HTML/CSS pagina
criteria:
  - Grid wordt gebruikt voor de totale layout
maxPoints: 10
tips:
  - Begin met de grid-container
---

Beschrijving van de case.

Instructies voor de opdracht.
```

### `content/weekN/exercises/_meta.md`

```yaml
---
week: 1
title: CSS Grid oefeningen
color: indigo
mode: interactive   # optioneel, overschrijft exerciseMode voor deze set
---
```

### `content/weekN/exercises/N.md`

Elk bestand is één oefening. Het YAML-frontmatter bevat de metadata;
de Markdown **body** wordt gebruikt als oefeninhoud.

**Tekst-oefening met Markdown body (aanbevolen voor rijke inhoud):**

```markdown
---
id: 1
difficulty: 1
title: Kolommen
type: text
---

Maak een grid met **twee gelijke kolommen** met `grid-template-columns`.

## Tips

- Gebruik `repeat(2, 1fr)` voor gelijke kolommen.
- `fr` staat voor _fractional unit_.
```

**Tekst-oefening gekoppeld aan theoriepagina's (optioneel):**

Gebruik `linked_theory` om theoriepagina's te koppelen. Een uitschuifbaar paneel
verschijnt rechts met een tabblad per week, zodat studenten de theorie kunnen
raadplegen zonder de oefening te verlaten.

```yaml
---
id: 3
type: text
title: Kolommen
linked_theory:
  - week1
  - week2
---
```

**Interactieve oefening (Monaco editor):**

```yaml
---
type: interactive
title: Voeg een gap toe
starterHtml: "<div class='grid'>…</div>"
starterCss: ".grid { display: grid; }"
solution: ".grid { display: grid; gap: 16px; }"
---
```

**Externe oefening (link naar extern):**

```yaml
---
type: external
title: Grid Garden
url: https://cssgridgarden.com
---
```

### `content/assessments/theory-assessment.md` en `practical-assessment.md`

Zelfde structuur als `quiz.md`. Praktijkvragen mogen een `preview: {css, html}`
veld bevatten voor een live CSS-preview bij de vraag.

## Custom elementen in Markdown

Theoriepagina's ondersteunen de volgende custom blok-elementen in Markdown:

| Element | Doel |
| ------- | ---- |
| `<x-callout>` | Notitieblok. Voeg `type="warning"` toe voor waarschuwingen. |
| `<x-card title="…">` | Inhoudskaart met een titel. |
| `<x-compare>` / `<x-compare-item title="…">` | Kolommen naast elkaar. |
| `<x-nav label="…">` | Navigatielinks onderaan (één Markdown-link per regel). |

Voorbeeld:

```markdown
<x-callout type="warning">
Let op: alleen **directe kinderen** van de grid-container worden grid-items.
</x-callout>

<x-compare>
<x-compare-item title="Flexbox — één richting">

Gebruik voor componenten: navigatiebalken, knoprijen.

</x-compare-item>
<x-compare-item title="Grid — twee richtingen">

Gebruik voor volledige pagina-layouts.

</x-compare-item>
</x-compare>
```

## Voorbeeld: CSS Grid

De `content/` map in dit template bevat een uitgewerkt voorbeeld van een
4-weken module over CSS Grid. Je kunt dit gebruiken als referentie voor
de structuur en opmaak van je eigen content.

## Publiceren (GitHub Pages)

Push naar `main` — de GitHub Actions workflow bouwt automatisch en publiceert naar GitHub Pages.

Zorg dat je in de repo-instellingen **Settings → Pages → Source: GitHub Actions** hebt ingesteld.

## Techniek

* **Builder:** [`@curio-sd/e-module-builder`](https://github.com/curio-team/e-module-builder)
* **Bundler:** Vite 6
* **Styling:** Tailwind CSS v4
* **Code-editor:** Monaco Editor
* **Deployment:** GitHub Pages via GitHub Actions
