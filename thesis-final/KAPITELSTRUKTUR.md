# Kapitelstruktur - Bachelorarbeit Final

**Status:** ✅ OPTIMIERT & FINAL (2026-09-02)

---

## 1. Einleitung

### 1.1 Motivation und Problemstellung

- Warum sind Scheduling-Algorithmen schwer zu verstehen?
- Defizite in der bestehenden Vermittlung

### 1.2 Zielsetzung der Arbeit

- Entwicklung einer interaktiven Webapp für Scheduling-Visualisierung
- Fokus auf präemptive Verfahren

### 1.3 Thematische Ausrichtung und Abgrenzung

- Scope der Arbeit
- Was wird behandelt, was nicht

### 1.4 Vorgehensweise und Aufbau der Arbeit

- Struktur der BA
- Logischer Aufbau Kapitel für Kapitel

### 1.5 Leitgedanke der Arbeit

- Übergeordnete Philosophie/Ansatz

---

## 2. Grundlagen

### 2.1 Betriebssysteme und Prozessverwaltung

- Grundkonzepte Prozess, Zustand, Kontext

### 2.2 CPU-Scheduling in Betriebssystemen

- Rolle des Schedulers
- Warum Scheduling wichtig ist

### 2.3 Präemptive versus nicht-präemptive Scheduling-Verfahren

- Unterschiede und Konsequenzen

### 2.4 Betrachtete Scheduling-Algorithmen

- **2.4.1** Last Come First Served (LCFS)
- **2.4.2** Round Robin (RR)
- **2.4.3** Strict Priority
- **2.4.4** Multilevel Feedback Queue (MLFQ)

### 2.5 Kennzahlen und Einordnungskriterien

- **2.5.1** Wartezeit
- **2.5.2** Durchlaufzeit (Turnaround Time)
- **2.5.3** Reaktionszeit
- **2.5.4** Ergänzende Kennzahlen (Kontextwechsel, Präemptionen, Auslastung)

### 2.6 Stand der Forschung zu Scheduling-Visualisierungen

- Verwandte Tools und Ansätze
- Klassifikation & Vergleich

---

## 3. Anforderungsanalyse

### 3.1 Zielgruppe und Einsatzkontext

- Wer nutzt die Webapp? (Studierend, Dozierende, Lehrende)
- In welchen Szenarien?

### 3.2 Funktionale Anforderungen

- Prozess-Eingabe und Konfiguration
- Simulationssteuerung (Step, Play, Reset)
- Algorithmus-Auswahl
- Metriken-Ausgabe (Tabellen, Diagramme)
- Vergleichsfunktionen

### 3.3 Didaktische Anforderungen

- Lernzielerreichung
- Verständlichkeit und Nachvollziehbarkeit
- Progressives Lernen (einfach → komplex)

### 3.4 Interaktions- und Usability-Anforderungen

- Intuitive Bedienung
- Responsive Design
- Barrierefreiheit (WCAG 2.1)

### 3.5 Technische Qualitätsziele

- Korrektheit der Simulation
- Performance
- Wartbarkeit (TypeScript, Vue 3)
- Testbarkeit

### 3.6 Nicht-Ziele und Randbedingungen

- Was wird explizit nicht implementiert
- Technische und zeitliche Grenzen

---

## 4. Systementwurf

### 4.1 Entwurfsprinzipien

- **Separation of Concerns:** Logik ↔ Visualisierung
- **Determinismus:** Reproduzierbare Simulationen
- **Modularität:** Unabhängige Komponenten
- **Erweiterbarkeit:** Neue Algorithmen einfach hinzufügbar

### 4.2 Gesamtarchitektur und Schichtenmodell

- **Frontend Layer** (Vue-Komponenten)
- **State Management** (Composition API)
- **Simulation Engine** (Core Logic)
- **Data Model** (Prozesse, Queues, Events)

**→ KOMPONENTENDIAGRAMM GEHÖRT HIER HIN**

### 4.3 Domänenmodell und Datenflüsse

- Datenstrukturen (Process, Queue, Scheduler)
- Event-Flow und State-Transitions
- Beispiel-Szenario Durchlauf

### 4.4 Interaktionsmodell für den Lernprozess

- Benutzer-Interaktionen (Klick, Eingabe)
- Feedback-Loops
- Visualisierungs-Updates in Echtzeit

### 4.5 Begründung zentraler Designentscheidungen

- Warum Vue.js 3 und nicht React/Angular?
- Warum TypeScript?
- Warum GSAP für Animationen?
- Trade-offs und Alternativen

---

## 5. Implementierung

### 5.1 Technologie-Stack und Projektstruktur

- Vue 3 (Composition API), TypeScript, Vite
- Projektstruktur und Dateiorganisation
- Build-Pipeline, Hot Module Replacement

### 5.2 Umsetzung des Simulationskerns

- Scheduler-Klasse, Queue-Datenstrukturen
- Simulation-Loop (Tick, Events)
- State Management mit Composition API

### 5.3 Umsetzung der Scheduling-Strategien

- **Generische Scheduler-Schnittstelle**
- Implementierung: LCFS, RR, Strict Priority, MLFQ
- Algorithmus-spezifische Parameter

### 5.4 Umsetzung der Visualisierung

- **5.4.1** Fokusansicht (Gantt-Diagramm, Stack-Anzeige)
- **5.4.2** Vergleichsübersicht (Timeline-Vergleich)
- **5.4.3** Bewertungsmatrix (Kennzahlen-Tabelle)

### 5.5 Umsetzung der Interaktionsmechanismen

- Playback-Steuerung (Start, Pause, Step, Reset)
- Geschwindigkeit/Zoom
- Szenario-Wechsel
- Export von Metriken

### 5.6 Szenario-Management inkl. Import/Export

- JSON-Format für Szenarien
- CRUD-Operationen (New, Load, Save, Delete)
- Seed-Szenarien + Scenario Generator

### 5.7 Technische Herausforderungen und Lösungen

- Performance bei vielen Prozessen
- Renderoptimierung
- TypeScript Type-Safety
- Testing und CI/CD

---

## 6. Qualitätssicherung

### 6.1 Teststrategie und Testaufbau

- Unit Tests (Vitest)
- Integration Tests
- Accessibility Tests (axe)

### 6.2 Abgesicherte Kernfunktionen und Testfälle

- **6.2.1** Deterministik und Reproduzierbarkeit
  - Gleiches Szenario → gleiche Ergebnisse
- **6.2.2** Verfahrensspezifische Korrektheit
  - RR: Quantum-Einhaltung
  - LCFS: LIFO-Ordnung
  - Strict Priority: Priority-Respekt
  - MLFQ: Queue-Promotionen/Demotionen
- **6.2.3** Validierung von Eingaben und Zuständen

### 6.3 Grenzen der Testabdeckung

- Was wird nicht getestet
- Warum (Zeit, Komplexität)

### 6.4 Nachvollziehbarkeit der Ergebnisse im Produktkontext

- Können Nutzer die Ergebnisse verstehen?
- Kann man einen Fehler nachvollziehen?

---

## 7. Ergebnis und Produktpräsentation

### 7.1 Überblick über das entwickelte Endprodukt

- Live-Demo-Link
- Was funktioniert, was nicht

### 7.2 Nutzerfluss und Bedienablauf

- Typical User Journey
- Schritt-für-Schritt-Ablauf

### 7.3 Produktdarstellung mit Screenshots

- Startbildschirm
- Szenario laden/erstellen
- Simulation laufen lassen
- Metriken vergleichen

### 7.4 Soll-Ist-Abgleich der Anforderungen

- Verfolgungstabelle: Anforderung → implementiert?
- Begründung für unerfüllte Anforderungen (falls welche)

### 7.5 Ergebnisbetrachtung und Einordnung

- Wird das Lernziel erreicht?
- Qualität der Visualisierung
- Benutzerfreundlichkeit subjektiv

---

## 8. Fazit und Ausblick

### 8.1 Zusammenfassung der Ergebnisse

- Was wurde erreicht
- Kurzer Rückblick auf die Arbeit

### 8.2 Kritische Reflexion und Grenzen

- Stärken der Webapp
- Schwächen/Verbesserungspotenzial
- Lernprozess während der Arbeit

### 8.3 Ausblick

- Zukünftige Features
- Weiterführende Forschung
- Potenzielle Einsätze in Lehre/Forschung

---

## 9. Anhang

- Zusätzliche Diagramme (ggf. detaillierte Klassendiagramme)
- Use-Case-Tabellen
- Auszüge aus dem Code (wichtige Algoritmen)
- Screenshot-Galerie

---

## Literaturverzeichnis

✅ **Finale bib.bib-Version** mit 10 hochwertigen Quellen

---

**Prüfer-Hinweis:** Das Komponentendiagramm sollte in Kapitel 4.2 eingefügt werden.
