# 📖 Projektdokumentation: Social-Media-Agent für Dr. Martens
**Projekt:** Semesterprojekt im Kurs GenAI & Web Analytics (gwa26)  
**Autor:** Lukas Henschel  
**Stand:** 11. November 2026 (Wird bei jedem Projektschritt automatisch aktualisiert)  
**Repository:** [github.com/spookyLuki1012/gwa26-agent-henschel](https://github.com/spookyLuki1012/gwa26-agent-henschel)

---

## 1. Executive Summary & Beratungs-Perspektive

### Warum dieser Aufbau? (Das „Context-First“-Prinzip für KI-Agenten)
Wenn Unternehmen KI-Agenten einführen, scheitern viele an generischen, ungenauen Ergebnissen („Halluzinationen“). Ein professioneller Agent benötigt ein klares Fundament aus **Kontext**, **Regelwerk** und **Messbarkeit**.

Dieses Projekt demonstriert den Best-Practice-Aufbau eines spezialisierten KI-Marketing-Agenten für **Dr. Martens**:
* **Keine Halluzinationen:** Der Agent darf nur auf geprüfte, belegbare Fakten aus dem Kontext zugreifen.
* **Messbarer Geschäftswert (ROI):** Die Arbeit des Agenten ist direkt an eine konkrete Stufe im Marketing-Funnel (AARRR-Framework) gekoppelt und wird über klare KPIs gemessen.
* **Skalierbare Architektur:** Von einfachen Markdown-Kontextdateien über Versionskontrolle mit Git bis hin zu einer interaktiven Web-App mit dem **Google Agent Development Kit (ADK)** und **Streamlit**.

---

## 2. Der Business Case (Dr. Martens)

| Parameter | Ausprägung im Projekt | Erklärung & Begründung |
| :--- | :--- | :--- |
| **Unternehmen** | Dr. Martens | Ikonische D2C-Schuh- und Lifestylemarke mit hohem Wiedererkennungswert (AirWair-Sohle, gelbe Rahmennaht). |
| **AARRR-Funnel-Stufe** | **Acquisition (Neukundengewinnung)** | Der Agent setzt ganz oben im Trichter an, um neue Interessenten über Social Media auf die Marke aufmerksam zu machen. |
| **Konkrete Aufgabe** | 3 Instagram-Posts pro Woche | Wöchentliche Erstellung von suchoptimierten Reels-Skripten und Karussell-Folien zu Styling, Pflege und Einlauf-Tipps. |
| **Primäre Kennzahl (KPI)** | Profilaufrufe & neue Follower je Woche | Gibt sofort messbares Feedback, ob die Content-Strategie wirkt und neue Reichweite generiert. |
| **Zielpersona** | Maya (22 Jahre, Studentin) | Sucht langlebige, authentische Schuhe, scheut aber das schmerzhafte Einlaufen neuer Lederstiefel. |
| **Markenton (Tone of Voice)** | Rebellisch, authentisch, selbstbewusst | Spiegelt die traditionsreiche Subkultur-DNA von Dr. Martens wider. Keine weichgespülte Werbesprache. |

---

## 3. Ordner- & Architekturstruktur

```text
gwa26-agent-henschel/
├── .gitignore               # Schützt sensible Daten (.env API-Keys, .venv) vor dem Upload
├── AGENTS.md                # Das „Gehirn“: System-Prompt, Aufgabenbeschreibung & 5 feste Regeln
├── PROJEKT_DOKUMENTATION.md # Diese Master-Dokumentation (wird laufend aktualisiert)
├── kontext/                 # Die Wissensbasis des Agenten (Single Source of Truth)
│   ├── aarrr-stufe.md       # Definition von Stufe (Acquisition), Aufgabe & Kennzahl
│   ├── marke.md             # Markentonalität und belegbare Fakten mit Quellenangaben
│   ├── positionierung.md    # Markenkern & USP in einem prägnanten Satz
│   ├── unternehmen.md       # Angebot, Produktpalette, Preisrahmen & offizielle Quellen
│   ├── ziele.md             # Konkrete quantitative Zielsetzung & Maßnahmen
│   └── zielgruppe.md        # Detailliertes Buyer-Persona-Profil (Maya)
└── ergebnisse/              # Ausgabeordner für alle vom Agenten erstellten Inhalte
    └── .gitkeep             # Hält den Ordner in Git aktiv, bis Ergebnisse generiert werden
```

### Warum die Wissensbasis aufgeteilt ist:
In der Unternehmensberatung nennt man das **Separation of Concerns**: Ändern sich Preise oder Produkte, wird nur `unternehmen.md` angepasst. Ändert sich die Kampagnenausrichtung, wird nur `ziele.md` aktualisiert. Der Agent bleibt stabil, weil er modular aufgebaut ist.

---

## 4. Die 5 Kernregeln des Agenten (`AGENTS.md`)

In `AGENTS.md` sind die unverhandelbaren Leitplanken für das KI-Modell verankert:
1. **Deutsch als Ausgabesprache:** Konsistente Kundenansprache für den DACH-Markt.
2. **Strikte Faktenbindung:** Der Agent darf nur Fakten aus dem Ordner `kontext/` nutzen. Fehlt eine Information, muss er zwingend *„Annahme:“* voranstellen.
3. **Markenkonformität:** Striktes Einhalten des Markentons aus `kontext/marke.md` (rebellisch, authentisch, selbstbewusst).
4. **Schreibschutz für das Setup:** Ergebnisse werden ausschließlich neu im Ordner `ergebnisse/` angelegt. Bestehende Systemdateien fasst der Agent nicht eigenmächtig an.
5. **Deutsche Währungs- und Zahlenkonventionen:** Beträge immer in EUR mit Komma (z. B. `199,00 EUR`), passend für den lokalen E-Commerce.

---

## 5. Bisherige Meilensteine (Changelog)

### Phase 1: Konzeption & Initialisierung (Abgeschlossen ✅)
* **Projektdefinition:** Wahl von Dr. Martens als echtes D2C-Unternehmen mit Fokus auf Social-Media-Acquisition.
* **Context Engineering:** Vollständige Ausarbeitung aller 6 Kontextdateien (`unternehmen.md`, `zielgruppe.md`, `positionierung.md`, `aarrr-stufe.md`, `marke.md`, `ziele.md`) ohne Platzhalter oder eckige Klammern.
* **Versionskontrolle (Git):** Initialisierung des Repositories mit geschütztem `main`-Branch und Bereitstellung der `.gitignore`.
* **GitHub Backup & Collaboration:**
  * Privates Repository unter `spookyLuki1012/gwa26-agent-henschel` erstellt und erfolgreich synchronisiert.
  * Dozent (`kirenz`) als offizieller Collaborator für die Bewertung autorisiert.
* **Toolchain & Tech-Stack vorbereitet:**
  * Python 3.9 & virtuelle Umgebung eingerichtet.
  * **Google ADK (`google-adk`)** und **`google-genai`** installiert.
  * Schneller Paketmanager **`uv`** (v0.13.7) integriert.
  * Web-Frontend-Framework **`streamlit`** (v1.50.0) einsatzbereit installiert.

---

## 6. Ausblick & Roadmap (Nächste Semester-Schritte)

```
[Phase 1: Fundament] ✅  -->  [Phase 2: Content-Agent] ⏳  -->  [Phase 3: Web-App & Frontend] ⏳
 • Kontext & Regeln            • Erster Prompt-Lauf            • Google ADK Anbindung
 • Git & GitHub Setup          • 3 Posts in ergebnisse/        • Streamlit UI mit React-Power
 • Tech-Stack (uv, venv)       • Qualitätsprüfung              • Live-Deployment
```

1. **Termin 5 (Erster Agenten-Auftrag):**  
   Dem Agenten wird der erste Prompt erteilt, um basierend auf `kontext/` 3 wöchentliche Instagram-Beiträge zu erstellen und im Ordner `ergebnisse/` abzulegen.
2. **Spätere Termine (Frontend & Google ADK):**  
   Entwicklung eines Python-basierten User Interfaces mit **Streamlit** (das unter der Haube auf React-Komponenten setzt), worüber Marketing-Teams ohne Programmierkenntnisse neue Beiträge per Knopfdruck anfordern, anpassen und exportieren können.

---

## 7. Spickzettel für Präsentationen & Beratungsgespräche

Wenn dich jemand fragt, wie das Projekt aufgebaut ist, kannst du es in 3 Sätzen erklären:
> *„Wir haben hier einen spezialisierten Marketing-Agenten für Dr. Martens aufgebaut, der über ein modulares Context-Engineering gesteuert wird. Statt generischer Texte erstellt der Agent markenkonforme Instagram-Inhalte für die Funnel-Stufe Acquisition, gemessen an wöchentlichen Profilaufrufen. Das gesamte System ist versioniert über Git und wird im nächsten Schritt über das Google ADK und Streamlit in eine interaktive Web-Anwendung überführt.“*
