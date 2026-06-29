---
title: "Toets Praktijk — CSS Grid"
passScore: 70
questions:
  - id: p1
    question: Welk CSS-snippet maakt een grid met 3 gelijke kolommen?
    preview:
      css: ".demo { display: grid; grid-template-columns: repeat(3, 1fr); gap: 4px; } .demo > div { background: #818cf8; padding: 12px; color: white; text-align: center; }"
      html: "<div class=\"demo\"><div>1</div><div>2</div><div>3</div></div>"
    options:
      - "display: flex; flex-direction: row;"
      - "display: grid; grid-template-columns: repeat(3, 1fr);"
      - "display: grid; grid-template-rows: 3;"
      - "float: left; width: 33%;"
    correct: 1
    explanation: "repeat(3, 1fr) maakt drie gelijke kolommen."

  - id: p2
    question: In onderstaand grid welk element staat linksboven?
    preview:
      css: ".demo { display: grid; grid-template-columns: 1fr 1fr; grid-template-areas: \"a b\" \"c d\"; gap: 4px; } .a { grid-area: a; background: #4f46e5; } .b { grid-area: b; background: #6366f1; } .c { grid-area: c; background: #818cf8; } .d { grid-area: d; background: #a5b4fc; } .demo > div { padding: 16px; color: white; text-align: center; font-weight: bold; }"
      html: "<div class=\"demo\"><div class=\"a\">A</div><div class=\"b\">B</div><div class=\"c\">C</div><div class=\"d\">D</div></div>"
    options:
      - B
      - A
      - C
      - D
    correct: 1
    explanation: "A heeft grid-area: a en staat in de eerste cel linksboven."

  - id: p3
    question: Welke property ontbreekt om dit een grid te maken?
    preview:
      css: ".demo { grid-template-columns: 1fr 1fr; gap: 8px; } .demo > div { background: #10b981; padding: 12px; color: white; }"
      html: "<div class=\"demo\"><div>1</div><div>2</div></div>"
    options:
      - gap
      - "display: grid"
      - grid-template-rows
      - "position: relative"
    correct: 1
    explanation: "Zonder display: grid worden de andere properties niet toegepast als grid."

  - id: p4
    question: Welk item spant over 2 kolommen?
    preview:
      css: ".demo { display: grid; grid-template-columns: 1fr 1fr 1fr; grid-template-areas: \"wide wide side\"; gap: 4px; } .wide { grid-area: wide; background: #7c3aed; } .side { grid-area: side; background: #a78bfa; } .demo > div { padding: 16px; color: white; text-align: center; }"
      html: "<div class=\"demo\"><div class=\"wide\">Breed</div><div class=\"side\">Smal</div></div>"
    options:
      - Het smalle item
      - Het brede item (wide)
      - Beide items
      - Geen van beide
    correct: 1
    explanation: '"wide wide side" laat het wide-gebied 2 kolommen beslaan.'

  - id: p5
    question: Hoeveel kolommen heeft dit grid?
    preview:
      css: ".demo { display: grid; grid-template-columns: repeat(4, 1fr); gap: 4px; } .demo > div { background: #f59e0b; padding: 8px; color: white; text-align: center; font-size: 12px; }"
      html: "<div class=\"demo\"><div>1</div><div>2</div><div>3</div><div>4</div></div>"
    options:
      - "2"
      - "3"
      - "4"
      - "6"
    correct: 2
    explanation: "repeat(4, 1fr) definieert 4 kolommen."

  - id: p6
    question: Welke grid-template-areas hoort bij deze layout (header bovenaan over volle breedte)?
    preview:
      css: ".demo { display: grid; grid-template-columns: 1fr 1fr; grid-template-areas: \"head head\" \"left right\"; gap: 4px; } .head { grid-area: head; background: #4f46e5; } .left { grid-area: left; background: #818cf8; } .right { grid-area: right; background: #a5b4fc; } .demo > div { padding: 12px; color: white; text-align: center; }"
      html: "<div class=\"demo\"><div class=\"head\">H</div><div class=\"left\">L</div><div class=\"right\">R</div></div>"
    options:
      - '"head left" "right right"'
      - '"head head" "left right"'
      - '"left head" "right head"'
      - '"head" "left" "right"'
    correct: 1
    explanation: 'De header moet twee kolommen beslaan: "head head".'

  - id: p7
    question: Welke CSS geeft 2 kolommen op een productgrid?
    preview:
      css: ".demo { display: grid; grid-template-columns: repeat(2, 1fr); gap: 6px; } .demo > div { background: #06b6d4; padding: 16px; color: white; text-align: center; }"
      html: "<div class=\"demo\"><div>P1</div><div>P2</div><div>P3</div><div>P4</div></div>"
    options:
      - "grid-template-columns: repeat(2, 1fr);"
      - "grid-template-columns: 2;"
      - "grid-template-rows: repeat(2, 1fr);"
      - "columns: 2;"
    correct: 0
    explanation: "repeat(2, 1fr) maakt precies 2 gelijke kolommen."

  - id: p8
    question: Wat is de functie van gap in dit grid?
    preview:
      css: ".demo { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; } .demo > div { background: #ec4899; padding: 12px; color: white; }"
      html: "<div class=\"demo\"><div>A</div><div>B</div></div>"
    options:
      - Padding binnen de items
      - Ruimte tussen de grid-items
      - Buitenmarge van de container
      - Border-radius
    correct: 1
    explanation: gap bepaalt de ruimte tussen rijen en kolommen van items.

  - id: p9
    question: Welk item staat in de rechterkolom van de bovenste rij?
    preview:
      css: ".demo { display: grid; grid-template-columns: 1fr 1fr; gap: 4px; } .demo > div { padding: 14px; color: white; text-align: center; } .demo > div:nth-child(1) { background: #ef4444; } .demo > div:nth-child(2) { background: #22c55e; }"
      html: "<div class=\"demo\"><div>Rood</div><div>Groen</div></div>"
    options:
      - Rood
      - Groen
      - Beide
      - Geen
    correct: 1
    explanation: "Items vullen cellen in volgorde: eerste item links, tweede rechts."

  - id: p10
    question: Welke responsive aanpak is correct voor minder kolommen op kleinere schermen?
    options:
      - "@media (max-width: 600px) { .grid { grid-template-columns: 1fr; } }"
      - ".grid { columns: 1; }"
      - "@media (max-width: 600px) { .grid { display: block; } }"
      - "grid-template-columns: auto;"
    correct: 0
    explanation: Media queries met aangepaste grid-template-columns is de standaard aanpak.
---
