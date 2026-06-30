---
week: 4
title: Meetmoment Week 4 — Samenwerken via GitHub
passScore: 70
questions:
  - id: w4q1
    question: Wat is een collaborator op GitHub?
    options:
      - Iemand die een eigen kopie (fork) van jouw repository maakt
      - Iemand die schrijfrechten heeft op jouw repository en daarin kan pushen
      - Een automatisch gegenereerde back-up van je code
      - Een branch in je repository
    correct: 1
    explanation: Een collaborator heeft schrijfrechten op jouw repository en werkt direct in dezelfde codebase — anders dan bij een fork.

  - id: w4q2
    question: Waar voeg je een collaborator toe aan een GitHub-repository?
    options:
      - Code → Branches
      - Settings → Collaborators → Add people
      - Issues → Assignees
      - Profile → Access
    correct: 1
    explanation: Via Settings → Collaborators → Add people stuur je een uitnodiging naar de GitHub-gebruiker.

  - id: w4q3
    question: Wat is de juiste volgorde van de samenwerkworkflow?
    options:
      - Commit → pull → push → aanpassen
      - Pull → aanpassen → commit → push
      - Push → aanpassen → pull → commit
      - Aanpassen → push → commit → pull
    correct: 1
    explanation: Altijd eerst pullen zodat je de nieuwste versie hebt, dan aanpassen, committen en pushen.

  - id: w4q4
    question: Wat doet een pull?
    options:
      - Je lokale commits naar GitHub sturen
      - De nieuwste commits van GitHub naar je laptop halen
      - Een nieuwe repository aanmaken
      - Een collaborator uitnodigen
    correct: 1
    explanation: Een pull haalt de laatste wijzigingen van de online repository naar jouw lokale kopie.

  - id: w4q5
    question: Wanneer ontstaat een merge conflict?
    options:
      - Als je een bestand verwijdert
      - Als twee mensen dezelfde regel in hetzelfde bestand hebben aangepast
      - Als je vergeet te committen
      - Als je repository private is
    correct: 1
    explanation: Een merge conflict ontstaat als Git twee verschillende versies van dezelfde regel ziet en niet automatisch kan kiezen welke hij moet bewaren.

  - id: w4q6
    question: Hoe markeert Git een merge conflict in een bestand?
    options:
      - Met een rood kruis in de bestandsnaam
      - Met speciale markers zoals <<<<<<<, ======= en >>>>>>>
      - Door het bestand te verwijderen
      - Door een e-mail te sturen
    correct: 1
    explanation: Git voegt conflictmarkers toe aan het bestand. Alles tussen <<<<<<< en ======= is jouw versie; tussen ======= en >>>>>>> is de versie van GitHub.

  - id: w4q7
    question: Wat moet je doen nadat je een merge conflict hebt opgelost in het bestand?
    options:
      - De repository opnieuw clonen
      - De conflictmarkers verwijderen, opslaan, committen en pushen
      - Alleen opslaan — Git regelt de rest automatisch
      - Een nieuwe branch aanmaken
    correct: 1
    explanation: Na het oplossen verwijder je de markers, sla je het bestand op en maak je een nieuwe commit. Daarna push je naar GitHub.

  - id: w4q8
    question: Wat is het verschil tussen een fork en een collaborator?
    options:
      - Er is geen verschil
      - Bij een fork werk je in een eigen kopie; bij een collaborator werk je in dezelfde repository
      - Een fork geeft schrijfrechten; een collaborator heeft alleen leesrechten
      - Een collaborator maakt altijd een fork aan
    correct: 1
    explanation: Bij een fork heb je een eigen, losgekoppelde kopie. Als collaborator werk je direct in de originele repository van de eigenaar.
---
