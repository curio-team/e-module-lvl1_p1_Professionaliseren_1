# Versiebeheer — Professionaliseren Unit 1

Een interactieve e-module over **versiebeheer** voor de opleiding Software Developer (niveau 1), gebouwd met [`@curio-sd/e-module-builder`](https://github.com/curio-team/e-module-builder).

In deze module van 3 weken leren studenten hoe software developers hun bestanden organiseren en de verschillende versies van hun code beheren:

- **Week 1 — Bestanden, folders en een mappenstructuur:** wat bestanden, bestandsextensies en folders zijn, en het opzetten van een nette mappenstructuur voor schoolwerk (inclusief OneDrive).
- **Week 2 — Git en GitHub:** kennismaken met Git, GitHub en repositories; een repository forken en clonen naar de eigen laptop.
- **Week 3 — Code beheren via Git:** zelf een repository maken, code committen met logische titels en pushen naar GitHub.

> [!NOTE]
> Een vierde week (*Samenwerken via Git*) wordt later toegevoegd. In `content/module.md` staat `weeks: 3`; verhoog dit naar `4` zodra `content/week4/` is geschreven.

Studenten leveren hun opdrachten in via **Itslearning**, waar de docent het werk nakijkt en feedback geeft.

## Snel starten

1. Installeer de afhankelijkheden en start de ontwikkelserver:

   ```bash
   npm install
   npm run dev
   ```

2. Open [http://localhost:5173](http://localhost:5173) in je browser.

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
  week1/ … week3/
    theory.md           ← theorie (YAML frontmatter + Markdown body)
    quiz.md             ← meetmoment (tussentoets) vragen
    assignment.md       ← inleveropdracht
    exercises/
      _meta.md          ← oefening-metadata (week, titel, kleur)
      N.md              ← oefening 1, 2, 3, ...
    images/             ← screenshots die in theory.md gebruikt worden
  assessments/
    theory-assessment.md      ← eindtoets theorie
    practical-assessment.md   ← praktische eindopdracht
```

### Afbeeldingen

Screenshots staan per week in `content/weekN/images/` en worden in `theory.md` aangeroepen met een **relatief** pad, bijvoorbeeld:

```markdown
![Beschrijving](images/git-installer.png)
```

De builder kopieert deze automatisch naar de juiste plek en herschrijft het pad. Gebruik dus geen pad dat met `/` of `..` begint.

### Oefeningen

De oefeningen zijn van het type `text`: praktische taken die de student op de eigen laptop uitvoert (mappen maken, Git installeren, forken, clonen, committen, pushen). Elk bestand bevat een YAML-frontmatter met `id`, `difficulty`, `title` en `type: text`; de Markdown-body is de oefeninhoud. Met `linked_theory` kun je theoriepagina's naast een oefening tonen.

## Custom elementen in Markdown

Theoriepagina's ondersteunen de volgende custom blok-elementen:

| Element | Doel |
| ------- | ---- |
| `<x-callout>` | Notitieblok. Voeg `type="warning"` toe voor waarschuwingen. |
| `<x-card title="…">` | Inhoudskaart met een titel. |
| `<x-compare>` / `<x-compare-item title="…">` | Kolommen naast elkaar. |
| `<x-nav label="…">` | Navigatielinks onderaan (één Markdown-link per regel). |

## Publiceren (GitHub Pages)

Push naar `main` — de GitHub Actions workflow bouwt automatisch en publiceert naar GitHub Pages. Zorg dat je in de repo-instellingen **Settings → Pages → Source: GitHub Actions** hebt ingesteld.

## Techniek

* **Builder:** [`@curio-sd/e-module-builder`](https://github.com/curio-team/e-module-builder)
* **Bundler:** Vite 6
* **Styling:** Tailwind CSS v4
* **Deployment:** GitHub Pages via GitHub Actions
