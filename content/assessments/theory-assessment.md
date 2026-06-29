---
title: "Toets Theorie — CSS Grid"
passScore: 70
questions:
  - id: t1
    question: Wat is een grid container?
    options:
      - Een direct kind van een grid element
      - "Het element met display: grid waarop het raster wordt gedefinieerd"
      - Een kolom in het grid
      - Een HTML-element met class="grid"
    correct: 1
    explanation: "De container is het element waarop je display: grid toepast en grid-template-* definieert."

  - id: t2
    question: Wat is het belangrijkste verschil tussen Flexbox en Grid?
    options:
      - Flexbox is ouder dan Grid
      - Flexbox werkt in één richting, Grid in twee richtingen (rijen én kolommen)
      - Grid werkt alleen op desktop
      - Flexbox kan geen gap gebruiken
    correct: 1
    explanation: "Flexbox = één dimensie. Grid = twee dimensies, ideaal voor pagina-layouts."

  - id: t3
    question: Welke property maakt een element een grid container?
    options:
      - "grid: on"
      - "display: grid"
      - "position: grid"
      - "layout: grid"
    correct: 1
    explanation: "display: grid activeert CSS Grid op het element."

  - id: t4
    question: "Wat doet grid-template-columns: 1fr 200px?"
    options:
      - Twee rijen van 1fr en 200px
      - Een flexibele kolom en een vaste kolom van 200px
      - 200 kolommen
      - Alleen padding instellen
    correct: 1
    explanation: 1fr neemt beschikbare ruimte, 200px is een vaste breedte.

  - id: t5
    question: Wat doet de gap property?
    options:
      - Ruimte tussen grid-items
      - Ruimte binnen een grid-item
      - De grootte van kolommen
      - De kleur van de grid-lijnen
    correct: 0
    explanation: gap (of row-gap / column-gap) bepaalt de ruimte tussen items.

  - id: t6
    question: Wat is grid-template-areas?
    options:
      - Een lijst van HTML-klassen
      - Een visuele manier om gebieden namen te geven met strings
      - Een JavaScript functie
      - Een media query
    correct: 1
    explanation: Met grid-template-areas teken je je layout met benoemde gebieden.

  - id: t7
    question: Hoe laat je een item over 2 kolommen spannen?
    options:
      - "width: 200%"
      - "grid-column: 1 / 3 of grid-area met twee kolommen in template-areas"
      - "float: left"
      - "position: absolute"
    correct: 1
    explanation: grid-column of een area die twee kolom-namen beslaat in template-areas.

  - id: t8
    question: "Wat doet repeat(4, 1fr)?"
    options:
      - 4 rijen van 1fr
      - 4 kolommen van gelijke flexibele breedte
      - Herhaal 4 keer de animatie
      - 4px gap
    correct: 1
    explanation: "repeat(4, 1fr) maakt 4 kolommen die de ruimte gelijk verdelen."

  - id: t9
    question: "Wat doet minmax(200px, 1fr)?"
    options:
      - Minimaal 200px, maximaal 1fr beschikbare ruimte
      - Exact 200px
      - Alleen op mobiel
      - Verbergt het element
    correct: 0
    explanation: minmax stelt een minimum en maximum in voor een track.

  - id: t10
    question: Wat is het verschil tussen auto-fit en auto-fill?
    options:
      - Geen verschil
      - auto-fit klapt lege tracks in, auto-fill behoudt ze
      - auto-fill werkt alleen in Firefox
      - auto-fit is voor rijen, auto-fill voor kolommen
    correct: 1
    explanation: "auto-fill vult met zoveel mogelijk kolommen; auto-fit laat items de ruimte vullen."

  - id: t11
    question: Waarom gebruik je geen floats voor pagina-layout?
    options:
      - Floats zijn deprecated
      - Floats zijn bedoeld voor tekstomloop, niet voor structurele layouts
      - Floats werken niet in Chrome
      - Floats zijn trager dan Grid
    correct: 1
    explanation: "Floats zijn oorspronkelijk voor tekstomloop; Grid is gemaakt voor layouts."

  - id: t12
    question: Wat is een grid item?
    options:
      - De container zelf
      - Een direct kind van de grid container
      - Elk element op de pagina
      - Alleen div-elementen
    correct: 1
    explanation: Alleen directe kinderen van de container worden grid items.

  - id: t13
    question: "Wat doet grid-area: header?"
    options:
      - Maakt een header-element aan
      - Plaatst het item in het gebied met de naam 'header'
      - Verbergt het item
      - Stelt de hoogte in op header-grootte
    correct: 1
    explanation: grid-area koppelt een item aan een benoemd gebied uit grid-template-areas.

  - id: t14
    question: Hoe combineer je Grid met media queries?
    options:
      - Dat kan niet
      - Je past grid-template-columns aan binnen @media regels
      - Je vervangt Grid door Flexbox op mobiel
      - Media queries werken alleen met floats
    correct: 1
    explanation: Binnen media queries pas je grid-properties aan voor verschillende schermen.

  - id: t15
    question: Wat betekent fr als eenheid?
    options:
      - Fixed ratio
      - "Fraction — een deel van de beschikbare ruimte"
      - Frame rate
      - Full row
    correct: 1
    explanation: "fr staat voor fraction: een deel van de vrije ruimte in het grid."
---
