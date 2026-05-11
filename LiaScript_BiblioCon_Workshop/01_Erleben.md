<!--
author:   Sebastian Zug, André Dietrich, Anja Hawlitschek und Anja Schulz

email:    sebastian.zug@informatik.tu-freiberg.de

version:  0.1.0

language: de

narrator: Deutsch Male

mode:     Presentation

date:     22/05/2026

comment:  Demo-Modul für den Hands-on Lab "Interaktive OER für die
          Bibliothekspraxis – Lernmaterialien mit LiaScript kollaborativ
          erstellen" auf der Bibliocon 2026 (Freitag, 22.05.2026).
          Ein durchgängig interaktives Mini-Modul zur Erkundung.

repository: https://github.com/SebastianZug/Bibliocon2026

attribute: LiaScript im Bibliotheksalltag
           von Sebastian Zug, André Dietrich,
           Anja Hawlitschek und Anja Schulz
           ist lizenziert unter [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

import:   https://github.com/LiaTemplates/Pyodide

link:     ../style.css

-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/SebastianZug/Bibliocon2026/main/Friday-Workshop/Demo/Bibliothekspraxis.md)

# LiaScript im Bibliotheksalltag

> <h2>Phase 1 des OER BiblioCon-Workshops</h2>
>
> <div style="height: 2.5em;"></div>
>
> <h4>Prof. Dr. Sebastian Zug, TU Bergakademie Freiberg.</h4>
> <h4>Dr. Anja Hawlitschek, Otto-von-Guericke-Universität Magdeburg</h4>
> <h4>Dr. Anja Schulz, Hochschuldidaktik Sachsen</h4>
>
> <h4>22. Mai 2026</h4>

--------------------------------------------


> [!CAUTION]
> Links prüfen!

## Motivation

Dieses Modul ist Ihr **erster Kontakt** mit einem fertigen LiaScript-Kurs. Es enthält drei inhaltliche Miniaturen aus dem Bibliotheksalltag — jede führt **Kernfeature** von LiaScript ein:

1. **Datenkompetenz**
2. **Metadaten**
3. **Recherchekompetenz**

> **Aufgabe während der nächsten 20 Minuten**
>
> Gehen Sie die Seiten durch, probieren Sie alle interaktiven Elemente aus und notieren Sie sich drei Dinge:
>
> - Was hat Sie überrascht?
> - Welches Element würden Sie in Ihrer eigenen Schulung einsetzen?
> - Was möchten Sie im Tutorial-Teil unbedingt lernen?
> - Was hat vielleicht anders funktioniert als erwartet?

> [!TIP]
> Klicken Sie rechts unten auf den Pfeil nach rechts, um auf die nächste Seite zu blättern. alternativ können Sie auch die Pfeiltaste auf Ihrer Tastatur verwenden.

## Bedienung

> [!CAUTION]
> Der Screenshot wird noch mit Grafiken angreichert, um die wichtigsten Bedienelemente zu markieren. 

![Screenshot](https://github.com/LiaPlayground/Bibliocon2026/blob/main/LiaScript_BiblioCon_Workshop/images/LiaScript_screenshot_raw.png?raw=true)

## Konzept

Die drei Miniaturen sollen einen Eindruck vermitteln, wie LiaScript die Wissensvermittlung unterstützt. Jeder Abschnitt fokussiert dabei einen anderen Aspekt:

| Abschnitt          | Fokus                                                                                       |
| ------------------ | ------------------------------------------------------------------------------------------- |
| Metadaten          | *von abstrakten Definition zu multimodalen Inhalten* - Wissensvermittlung ohne Medienbrüche |
| Datenkompetenz     | *von Daten zum Code* - Integrierte Programmierumgebungen                                    |
| Recherchekompetenz | *von Visualisierungen zu Quizzen* - Interktive Wissensüberprüfung                           |

## 1. Metadaten

> [!TIP]
> **Definition** Metadaten sind beschreibende Daten *über* einen bibliografischen Datensatz — Titel, Autor, Verlag, Schlagwort. Aber wie genau werden diese Daten strukturiert, damit sie von Menschen und Maschinen verstanden werden? Und wie sieht das in der Praxis aus?

> [!NOTE]
> **Worauf Sie in diesem Abschnitt achten sollten:** Sie begegnen demselben Sachverhalt gleich in *drei verschiedenen Darstellungen* — Video, eingebettete Spezifikationsseite und Code-Block. Alle drei liegen auf *dieser* Seite. Das ist gemeint, wenn LiaScript verspricht, *Wissensvermittlung ohne Medienbrüche* zu ermöglichen: keine Tab-Wechsel, keine Tool-Sprünge, kein Kontextverlust.

### Einstieg per Video

Bevor wir in die Details gehen, ein kurzer Überblick zum Thema:

> [!NOTE]
> Sie müssen das Video nicht komplett anschauen, es dient als Einstieg und der Illustration.

!?[Metadaten Einführungsvideo](https://www.youtube.com/watch?v=5HJVfp5c0kE)

### Abstraktion und Strukturierung 

Offenbar ist es nicht genug, einfach nur Label für Titel, Autor und Verlag zu definieren. Es braucht eine Systematik, damit die Daten von verschiedenen Bibliotheken in derselben Weise interpretiert werden können. 

> [!NOTE]
> Die nachfolgende, eingebettete Seite zeigt die offizielle Definition des Dublin-Core-Elements `creator` — ein Beispiel dafür, wie ein standardisiertes Schema die Interpretation von Metadaten erleichtert.

<iframe src="https://web.archive.org/web/2024/https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/creator/" width="100%" height="500" style="border: 1px solid #ccc; border-radius: 4px;"></iframe>

> **Mini-Aufgabe:** Scrollen Sie in der Spezifikation oben bis zum Eintrag **"Equivalent Property"**. Dort ist `dc:creator` mit einer Property aus einem *anderen* Vokabular formal gleichgesetzt — wie heißt sie, und aus welchem Vokabular kommt sie?

{{1}}
> **Auflösung:** `dc:creator` ist äquivalent zu `foaf:maker` — einer Property aus dem **FOAF**-Vokabular ("Friend of a Friend"), das Personen und ihre Werke im Web beschreibt.
> 
> **Warum das wichtig ist:** Im offenen Web existieren mehrere Vokabulare für ähnliche Konzepte (Dublin Core, FOAF, schema.org, BIBFRAME …). Damit Daten aus verschiedenen Welten zusammenfließen können, deklarieren die Vokabulare explizit, wann zwei Begriffe *dasselbe* meinen. Genau diese Äquivalenzen sind das Rückgrat von Linked Data — und einer der Gründe, warum kontrollierte Vokabulare in Bibliotheken über das eigene Katalogsystem hinaus wirken.

### Beispiel für einen Dublin-Core-Datensatz

Beschrieben als Dublin-Core-Datensatz sieht dieser Kurs so aus:

```xml
<head profile="http://dublincore.org/documents/dcq-html/">
  <title>LiaScript im Bibliotheksalltag</title>
  <link rel="schema.DC"      href="http://purl.org/dc/elements/1.1/"/>
  <link rel="schema.DCTERMS" href="http://purl.org/dc/terms/"/>

  <meta name="DC.title"       content="LiaScript im Bibliotheksalltag"/>
  <meta name="DC.creator"     content="Zug, Sebastian"/>
  <meta name="DC.creator"     content="Dietrich, André"/>
  <meta name="DC.contributor" content="Hawlitschek, Anja"/>
  <meta name="DC.contributor" content="Schulz, Anja"/>
  <meta name="DC.publisher"   content="BiblioCon 2026, TU Bergakademie Freiberg"/>
  <meta name="DC.date"        content="2026-05-22"/>
  <meta name="DC.type"        scheme="DCTERMS.DCMIType" content="InteractiveResource"/>
  <meta name="DC.format"      content="text/markdown (LiaScript)"/>
  <meta name="DC.language"    content="de"/>
  <meta name="DC.subject"     content="Open Educational Resources"/>
  <meta name="DC.subject"     content="Bibliothekspraxis"/>
  <meta name="DC.subject"     content="Datenkompetenz; Metadaten; Recherchekompetenz"/>

  <meta name="DCTERMS.audience"       content="Bibliothekarinnen und Bibliothekare"/>
  <meta name="DCTERMS.educationLevel" content="Berufliche Fortbildung"/>
  <meta name="DCTERMS.license"        scheme="DCTERMS.URI"
        content="https://creativecommons.org/licenses/by-sa/4.0/"/>
  <meta name="DCTERMS.source"         content="https://github.com/SebastianZug/Bibliocon2026"/>
  <meta name="DCTERMS.hasVersion"     content="0.1.0"/>
</head>
```

> **Lesart:** Jedes `<meta name="DC.xxx">`-Element ist eine maschinenlesbare Aussage über diesen Kurs — eingebettet in den HTML-Header der Seite, lesbar für Suchmaschinen, OER-Repositorien und Linked-Data-Werkzeuge. Genau diese Form von Metadaten macht ein Lernmaterial als *Open Educational Resource* im Web auffindbar, zitierbar und nachnutzbar.

> [!TIP]  
> Klicken Sie rechts oben in der Ecke auf das **i-Icon** (ℹ️), um die Metadaten dieses Kurses in einer übersichtlichen Darstellung zu sehen.

## 2. Datenkompetenz

> [!TIP]  
> ... (engl. Data Literacy) ist die Fähigkeit, Daten auf kritische Art und Weise zu sammeln, zu verwalten, zu bewerten, zu analysieren und zu interpretieren. Sie umfasst zudem die Fähigkeit, mit Daten zu kommunizieren und sie zu nutzen, um fundierte Entscheidungen zu treffen

> [!NOTE]
> **Worauf Sie in diesem Abschnitt achten sollten:** Der Abschnitt zeigt, wie LiaScript die Integration von Code und Daten in Lernmaterialien ermöglicht — und damit die Vermittlung von Datenkompetenz unterstützt. 

### Ausleihen als interaktives Diagramm

Verschaffen wir uns zunächst einen Überblick - ein fiktives Beispiel aus einer Bibliothek, das die Anzahl der Ausleihen und Vormerkungen pro Monat zeigt. Nutzen Sie die Stapel am rechten SPaltenrand um die Daten zu sortieren und bestimmen Sie, in welchem Monat es die meisten Ausleihen gab.

<!-- data-type="barchart" -->
| Monat | Ausleihen | Vormerkungen |
| ----- | ---------:| ------------:|
| Jan   |      1240 |           95 |
| Feb   |      1180 |          102 |
| Mär   |      1320 |          110 |
| Apr   |      1450 |          135 |
| Mai   |      1610 |          128 |
| Jun   |      1555 |          140 |

> [!TIP]  
> Noch einfacher geht es mit dem integrierten Diagrammgenerator: klicken Sie auf den Button Balkendiagramm über der Tabelle, um die Daten visuell zu erkunden. Finden Sie die in der Werkzeugleiste unter dem Diagramm die Möglichkeit, die Daten gleich zu bearbeiten?

### Darf es ein bisschen Code sein?

> [!TIP]
> Manchmal reicht es nicht, Daten zu visualisieren - wir wollen auch Kennzahlen berechnen, um die Daten zu interpretieren. In diesem Beispiel wollen wir die Vormerkungsquote berechnen - also den Anteil der Vormerkungen an den Ausleihen pro Monat. 
>
> Wir haben Ihnen den Code schon vorgegeben, Sie müssen lediglich die Zeile zur Berechnung der Vormerkungsquote einkommentieren und das kleine Beispiel neu ausführen. Probieren Sie es aus!

**Klicken Sie auf den Play-Button** (▶) im Code-Block:

```python        python_example.py
import pandas as pd

# hier werden die Daten als DataFrame angelegt - eine tabellarische 
# Datenstruktur, # die in Python häufig verwendet wird
daten = pd.DataFrame({
    "Monat":        ["Jan", "Feb", "Mär", "Apr", "Mai", "Jun"],
    "Ausleihen":    [ 1240,  1180,  1320,  1450,  1610,  1555],
    "Vormerkungen": [   95,   102,   110,   135,   128,   140]
})

# Berechne die Vormerkungsquote als neue Spalte
# Löschen Sie das Kommentarzeichen (#) am Anfang der nachfolgenden Zeile, 
# um die Berechnung der neuen Spalte zu aktivieren
# daten["Vormerkungsquote"] = daten["Vormerkungen"] / daten["Ausleihen"]
print(daten)
```
@Pyodide.eval


## 3. Recherchekompetenz — Boole'sche Operatoren

> [!TIP]  
> Recherchekompetenz ist eines der klassischen Schulungsthemen in Bibliotheken — und eines der am schwersten greifbaren. Wir machen es hier konkret: Sie bekommen einen überschaubaren Datenbestand, und der Klick auf ein Venn-Diagramm zeigt, welche Treffer eine Boole'sche Anfrage tatsächlich liefert.

> [!NOTE]
> **Worauf Sie in diesem Abschnitt achten sollten:** Im abschließenden Themenfeld dokumentieren wir die Quizformate, die Liascript abbildet um Lernstandserfassungen zu ermöglichen. 

### Ein Mini-Datenbestand

Stellen Sie sich vor, eine Fachdatenbank hätte nur die folgenden zehn Treffer zu Ihrer Schulungsrecherche. Jeder Titel ist mit keinem, einem oder beiden der Schlagworte **Informationskompetenz (IK)** bzw. **Berufsbildung (BB)** verknüpft.

| #   | Titel                                                                                             |  IK  |  BB  |
| ---:| ------------------------------------------------------------------------------------------------- |:----:|:----:|
|  1  | *Informationskompetenz in Universitätsbibliotheken*                                               |  ✓   |      |
|  2  | *Suchkompetenz und Recherche-Training*                                                            |  ✓   |      |
|  3  | *Open Access und wissenschaftliche Informationskompetenz*                                         |  ✓   |      |
|  4  | *Digitale Informationskompetenz an Schulen*                                                       |  ✓   |      |
|  5  | *Informationskompetenz für Auszubildende in technischen Berufen*                                  |  ✓   |  ✓   |
|  6  | *Recherchetraining im dualen Berufsausbildungssystem*                                             |  ✓   |  ✓   |
|  7  | *Digitale Kompetenzen in der beruflichen Weiterbildung — Schwerpunkt Informationskompetenz*       |  ✓   |  ✓   |
|  8  | *Curriculumentwicklung in der Berufsausbildung*                                                   |      |  ✓   |
|  9  | *Duale Berufsausbildung im Wandel*                                                                |      |  ✓   |
| 10  | *Qualitätsstandards in der beruflichen Bildung*                                                   |      |  ✓   |

> Recherchekompetenz bedeutet hier, die Schlagworte so zu kombinieren, dass spezifische Treffermengen bereitgstellt werden. Die drei wichtigsten Operatoren sind `AND`, `OR` und `NOT` — sie entsprechen den Schnitt-, Vereinigungs- und Differenzmengen in der Mengenlehre.

| Operator | Bedeutung                           | Wirkung auf Treffermenge | Im Datensatz oben       |
|:--------:| ----------------------------------- |:------------------------:|:------------------------|
|  `AND`   | **Beide** Begriffe müssen vorkommen | verkleinert              | 3 Treffer (5, 6, 7)     |
|  `OR`    | **Mindestens einer** muss vorkommen | vergrößert               | 10 Treffer (alle)       |
|  `NOT`   | Begriff **darf nicht** vorkommen    | verkleinert              | 4 bzw. 3 Treffer        |

> Kleiner Merksatz: **AND ist streng, OR ist großzügig, NOT ist wählerisch.**

### Venn-Diagramm zum Datensatz

Das Diagramm visualisiert, wie sich die zehn Titel auf die drei Schnittbereiche verteilen:

<svg class="boole-venn" viewBox="0 0 440 270" xmlns="http://www.w3.org/2000/svg" style="max-width: 620px; display: block; margin: 0 auto;">
  <defs>
    <mask id="notB">
      <rect width="100%" height="100%" fill="white"/>
      <circle cx="260" cy="140" r="85" fill="black"/>
    </mask>
    <mask id="notA">
      <rect width="100%" height="100%" fill="white"/>
      <circle cx="180" cy="140" r="85" fill="black"/>
    </mask>
    <clipPath id="inA">
      <circle cx="180" cy="140" r="85"/>
    </clipPath>
  </defs>

  <text x="110" y="35" text-anchor="middle" font-size="13" fill="#2c3e50" font-weight="bold">Informationskompetenz</text>
  <text x="330" y="35" text-anchor="middle" font-size="13" fill="#2c3e50" font-weight="bold">Berufsbildung</text>

  <circle cx="180" cy="140" r="85" fill="#3498db" fill-opacity="0.5" mask="url(#notB)"/>
  <circle cx="260" cy="140" r="85" fill="#9b59b6" fill-opacity="0.7" clip-path="url(#inA)"/>
  <circle cx="260" cy="140" r="85" fill="#e74c3c" fill-opacity="0.5" mask="url(#notA)"/>

  <circle cx="180" cy="140" r="85" fill="none" stroke="#2c3e50" stroke-width="2" pointer-events="none"/>
  <circle cx="260" cy="140" r="85" fill="none" stroke="#2c3e50" stroke-width="2" pointer-events="none"/>

  <text x="115" y="145" text-anchor="middle" font-size="13" font-weight="bold" fill="#1a5490" pointer-events="none">IK NOT BB</text>
  <text x="220" y="145" text-anchor="middle" font-size="13" font-weight="bold" fill="#5b2c6f" pointer-events="none">IK AND BB</text>
  <text x="325" y="145" text-anchor="middle" font-size="13" font-weight="bold" fill="#922b21" pointer-events="none">BB NOT IK</text>

  <text x="220" y="255" text-anchor="middle" font-size="12" fill="#7f8c8d" pointer-events="none">IK OR BB = alle drei Bereiche zusammen</text>
</svg>

> [!TIP]  
> Die folgenden Aufgaben prüfen Ihr Verständnis am gleichen Datensatz — und zeigen gleichzeitig drei verschiedene LiaScript-Quizformate: **Einfachauswahl**, **Zahleneingabe** und **Mehrfachauswahl**. Jede Aufgabe hat einen ausklappbaren Hinweis (`?`) und eine einklappbare Lösung.

**Aufgabe 1 — Welcher Bereich entspricht welcher Anfrage?** *(Einfachauswahl)*

Welcher Bereich des Venn-Diagramms zeigt Titel, die mit *beiden* Schlagworten verknüpft sind?

- [( )] Der blaue Bereich (links)
- [(X)] Der violette Schnittbereich (Mitte)
- [( )] Der rote Bereich (rechts)
- [( )] Alle drei Bereiche zusammen
- [[?]] Hinweis: "Mit beiden Schlagworten" entspricht der Anfrage `IK AND BB`. AND meint immer den *Schnitt* zweier Mengen.

<details>
<summary><strong>Lösung anzeigen</strong></summary>

Der violette Schnittbereich. Drei Titel haben in der Tabelle beide Häkchen gesetzt:

- 5 · *Informationskompetenz für Auszubildende in technischen Berufen*
- 6 · *Recherchetraining im dualen Berufsausbildungssystem*
- 7 · *Digitale Kompetenzen in der beruflichen Weiterbildung — Schwerpunkt Informationskompetenz*

</details>

**Aufgabe 2 — Treffer zählen.** *(Zahleneingabe)*

Wie viele Titel aus dem Datensatz liefert die Anfrage `IK OR BB`?

[[10]]

- [[?]] Hinweis: OR ist großzügig — es reicht, wenn *eines* der beiden Schlagworte gesetzt ist. Schauen Sie in die Tabelle: gibt es überhaupt einen Titel, der *gar kein* Häkchen hat?

<details>
<summary><strong>Lösung anzeigen</strong></summary>

**Alle zehn.** In diesem konstruierten Datensatz hat jeder Titel mindestens eines der beiden Schlagworte gesetzt — es gibt keinen "leeren" Eintrag. Das `OR` umfasst hier also den gesamten Bestand.

</details>

**Aufgabe 3 — Eine Kollegin braucht Beratung.** *(Mehrfachauswahl)*

Eine Kollegin sucht Bücher zur *Berufsbildung*, die *keinen* Informationskompetenz-Bezug haben. Welche Aussagen treffen zu?

- [[X]] Die passende Anfrage lautet `BB NOT IK`.
- [[X]] Sie liefert 3 Treffer.
- [[ ]] Sie liefert mehr Treffer als `IK NOT BB`.
- [[ ]] `BB NOT IK` und `BB AND NOT IK` liefern unterschiedliche Treffermengen.
- [[X]] Sie entspricht im Diagramm dem roten Bereich, der nicht mit dem blauen überlappt.
- [[?]] Hinweis: Lesen Sie das Diagramm als "BB ohne den Schnitt mit IK" — der rote Teil ohne den violetten.

<details>
<summary><strong>Lösung anzeigen</strong></summary>

Richtig sind die erste, zweite und fünfte Aussage. Die drei Treffer:

- 8 · *Curriculumentwicklung in der Berufsausbildung*
- 9 · *Duale Berufsausbildung im Wandel*
- 10 · *Qualitätsstandards in der beruflichen Bildung*

Zu den Distraktoren:

- `IK NOT BB` liefert **4** Treffer — also *mehr*, nicht weniger als `BB NOT IK`.
- `BB NOT IK` und `BB AND NOT IK` sind logisch äquivalent — das explizite `AND NOT` ändert nichts am Ergebnis.

</details>

## Und wer nutzt das?

> **Ein reales Beispiel:** Ferenz *et al.* (2024) beschreiben auf der NFDI4Energy-Konferenz einen LiaScript-Kurs zum Forschungsdaten­management, der produktiv beim Energie-Forschungszentrum Niedersachsen im Einsatz ist — und der u. a. ein Erklärvideo der Universität Gent einbindet, statt eines neu zu drehen.
>
> [Kurs öffnen](https://liascript.github.io/course/?https://raw.githubusercontent.com/NFDI4Energy/EFZN_rdm/master/README.md) · [Repository](https://github.com/NFDI4Energy/EFZN_rdm)

{{2}} Wie so etwas entsteht — und wie Sie selbst solche Kurse bauen und in die Community einbringen — schauen wir uns in den folgenden drei Phasen des Workshops an.

> Ihre drei Notizen aus der Einstiegs-Aufgabe kommen jetzt zum Einsatz:
>
> - Was hat Sie überrascht?
> - Was wollen Sie nachbauen?
> - Was möchten Sie vertiefen?