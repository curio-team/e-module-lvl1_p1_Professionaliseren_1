---
week: 4
title: Samenwerken via GitHub
goal: je kunt een klasgenoot toevoegen als collaborator en samen code committen, pushen en een merge conflict oplossen
summary: Werk voor het eerst samen aan één repository — voeg een collaborator toe, pull wijzigingen op en los een merge conflict op.
leeruitkomsten:
  - Ik weet wat een GitHub collaborator is
  - Ik kan een collaborator toevoegen aan mijn repository
  - Ik kan samen met een klasgenoot aan code werken via mijn Git-tool
  - Ik kan commits maken en pushen naar een gedeelde repository
  - Ik weet wat een merge conflict is en hoe ik het oplos
---

## Waar gaat deze week over?

Tot nu toe heb je altijd alleen aan jouw eigen repository gewerkt. Maar software developers werken vrijwel altijd **samen** — meerdere mensen aan dezelfde code. Deze week leer je hoe dat werkt via GitHub.

<x-callout>

**Aan het einde van deze week** weet je wat een collaborator is, kun je iemand toegang geven tot jouw repository, werk je voor het eerst samen aan één gedeelde codebase en weet je hoe je een merge conflict herkent en oplost.

</x-callout>

## 4.1 Wat is een collaborator?

Een **collaborator** is iemand die schrijfrechten heeft op jouw repository. Dat betekent dat die persoon code kan pushen naar jouw repository — net alsof het de zijne of hare is.

Dit is anders dan een **fork**. Bij een fork maakt iemand een eigen kopie van jouw repository. Bij een collaborator werken jullie allebei aan **dezelfde** repository.

<x-card title="Fork vs. collaborator">

- **Fork** — je maakt een eigen kopie; wijzigingen komen niet automatisch terug in het origineel.
- **Collaborator** — je werkt samen in één repository; alle commits zijn direct zichtbaar voor iedereen.

</x-card>

## 4.2 Een collaborator uitnodigen

Je voegt een collaborator toe via de instellingen van je repository op GitHub.

1. Open je repository op [github.com](https://github.com/).
2. Klik op **Settings** (rechtsboven in de repository).
3. Ga in het linkermenu naar **Collaborators**.
4. Klik op **Add people**.
5. Zoek op de GitHub-gebruikersnaam of het e-mailadres van je klasgenoot.
6. Klik op **Add [naam] to this repository**.

![Collaborator toevoegen via Settings → Collaborators](images/collaborator-toevoegen.png)

Je klasgenoot ontvangt nu een uitnodiging — via e-mail én als melding op GitHub.

## 4.3 De uitnodiging accepteren

De uitgenodigde persoon moet de uitnodiging eerst accepteren voordat hij of zij toegang heeft.

1. Open de e-mail van GitHub met het onderwerp *"[naam] has invited you to collaborate"*.
2. Klik op **View invitation** en daarna op **Accept invitation**.

Of via GitHub zelf: klik op het belletje (notificaties) rechtsboven en zoek de uitnodiging.

![Uitnodiging accepteren op GitHub](images/uitnodiging-accepteren.png)

Na het accepteren kan de collaborator de repository clonen en code pushen.

<x-callout type="warning">

**Let op:** clone de repository van je klasgenoot naar een **nieuwe, aparte folder** op je laptop. Zet hem niet in een bestaande Git-repository.

</x-callout>

## 4.4 De samenwerkworkflow

Zodra jullie allebei toegang hebben tot de repository, is er één gouden vuistregel:

<x-card title="Altijd eerst pullen">

**Pull → aanpassen → commit → push**

Begin elke werksessie met een **pull**. Zo haal je de nieuwste versie van de code op en voorkom je problemen.

</x-card>

Waarom is dit zo belangrijk? Als jouw klasgenoot een commit heeft gepusht terwijl jij aan het werken was, wijkt jouw lokale versie af van de versie op GitHub. Als je dan probeert te pushen, weigert GitHub dat — jij bent namelijk *achter* op de online versie.

## 4.5 Wijzigingen ophalen met een pull

Een **pull** haalt de nieuwste commits van GitHub naar je laptop. Je doet dit in je Git-tool.

<x-compare>
<x-compare-item title="Pull met GitKraken">

![Een pull uitvoeren in GitKraken](images/pull-gitkraken.png)

Klik op de **Pull**-knop in de werkbalk bovenaan GitKraken.

</x-compare-item>
<x-compare-item title="Pull met GitHub Desktop">

![Een pull uitvoeren in GitHub Desktop](images/pull-github-desktop.png)

Klik op **Fetch origin** (of **Pull origin** als er nieuwe commits zijn) in de werkbalk bovenaan GitHub Desktop.

</x-compare-item>
</x-compare>

Na een succesvolle pull zie je de commits van je klasgenoot in je commitgeschiedenis staan.

## 4.6 Wat is een merge conflict?

Soms lukt een pull niet zomaar. Dat gebeurt als jullie allebei **dezelfde regel** in **hetzelfde bestand** hebben aangepast. Git weet dan niet welke versie hij moet bewaren — dit heet een **merge conflict**.

Git markeert het conflict direct in het bestand:

```
<<<<<<< HEAD
<title>Muziekbibliotheek van Anna</title>
=======
<title>Muziekbibliotheek van Bo</title>
>>>>>>> origin/main
```

- Het stuk tussen `<<<<<<< HEAD` en `=======` is **jouw versie** (lokaal).
- Het stuk tussen `=======` en `>>>>>>>` is **de versie van GitHub** (van je klasgenoot).

<x-callout type="warning">

Een merge conflict is geen fout — het is Git die om jouw hulp vraagt. Je lost het op door zelf te kiezen welke versie je wilt bewaren.

</x-callout>

## 4.7 Een merge conflict oplossen

Het oplossen van een merge conflict gaat in vijf stappen.

1. **Open het bestand** met het conflict in je code-editor (bijv. VS Code).
2. **Zoek de conflictmarkers** (`<<<<<<<`, `=======`, `>>>>>>>`).
3. **Kies welke versie je wilt houden** — of combineer ze als dat logisch is.
4. **Verwijder alle markers** (de regels met `<<<<<<<`, `=======` en `>>>>>>>`).
5. **Sla het bestand op**, maak een nieuwe **commit** en **push**.

<x-compare>
<x-compare-item title="Conflict zien in GitKraken">

![Een merge conflict in GitKraken](images/conflict-gitkraken.png)

GitKraken markeert bestanden met een conflict met een oranje uitroepteken. Klik op het bestand om het te openen in de ingebouwde conflictoplosser.

</x-compare-item>
<x-compare-item title="Conflict zien in GitHub Desktop">

![Een merge conflict in GitHub Desktop](images/conflict-github-desktop.png)

GitHub Desktop toont een melding dat er conflicten zijn. Klik op **Open in Visual Studio Code** (of je eigen editor) om het conflict handmatig op te lossen.

</x-compare-item>
</x-compare>

Na het oplossen commit je het resultaat met een logische titel zoals *"merge conflict opgelost"* en push je naar GitHub.

## 4.8 Onthoud voor nu het volgende

<x-card title="De drie regels van samenwerken">

- **Voeg je klasgenoot toe als collaborator** via Settings → Collaborators.
- **Pull altijd eerst** voordat je begint met werken.
- **Bij een merge conflict**: open het bestand, kies de juiste versie, verwijder de markers en commit + push.

</x-card>

Volgende week leer je meer over branches — een techniek om nog veiliger samen te werken zonder elkaars werk te verstoren.

<x-nav label="Klaar met de theorie?">
[Oefeningen](/pages/week4-oefeningen.html)
[Meetmoment](/pages/week4-meetmoment.html)
[Inleveropdracht](/pages/week4-inleveropdracht.html)
</x-nav>
