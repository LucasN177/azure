# CLAUDE.md – Lernmaterialien AZ-104 (Microsoft Azure Administrator)

Dieser Ordner enthält Lernmaterialien zur Vorbereitung auf die Prüfung **AZ-104: Microsoft Azure Administrator**.
Pro prüfungsrelevantem Kapitel gibt es genau **eine Markdown-Datei**. Diese Datei beschreibt, wie die Dateien zu befüllen sind.

---

## 1. Ziel der Materialien

Jede Kapiteldatei soll so aufgebaut sein, dass man das Thema **ohne weitere Quellen verstehen, im Azure Portal wiederfinden und in der Prüfung anwenden** kann. Der Fokus liegt auf:

- **Inhalte** – was ist der Dienst / das Feature, wofür wird es genutzt?
- **Zusammenhänge** – wie hängt das Thema mit anderen Diensten und Kapiteln zusammen?
- **Beispiele** – konkrete, realistische Szenarien (wie sie auch in Prüfungsfragen vorkommen).
- **Azure Portal** – wo genau findet man die Einstellungen (Navigationspfade)?
- **CLI / PowerShell** – die wichtigsten Befehle für die Verwaltung.
- **Prüfungsrelevanz** – typische Fallstricke, Limits, Abgrenzungen und Fragen.

---

## 2. Ordnerstruktur

Die Struktur folgt den fünf Domänen des offiziellen Study Guides (Gewichtung in Klammern):

```
AZ-104/
├── CLAUDE.md
├── 00-pruefungsueberblick.md
├── 01-identitaeten-und-governance/        (20–25 %)
├── 02-speicher/                           (15–20 %)
├── 03-compute/                            (20–25 %)
├── 04-netzwerk/                           (15–20 %)
└── 05-monitoring-und-wartung/             (10–15 %)
```

**Namenskonvention:** `NN-thema-in-kleinbuchstaben.md` (zweistellige Nummer, Bindestriche, keine Umlaute im Dateinamen).
Neue Kapitel nur anlegen, wenn sie im offiziellen Study Guide vorkommen. Nummerierung fortlaufend halten.

**Sonderfall `00-pruefungsueberblick.md`:** Folgt nicht dem Kapitel-Aufbau, sondern enthält Prüfungsformat (Dauer, Fragetypen, Bestehensgrenze, Labs), die Domänen mit Gewichtung, ein verlinktes Inhaltsverzeichnis aller Kapitel mit Status (⬜ offen / 🟨 in Arbeit / ✅ fertig) sowie allgemeine Lernstrategie und Prüfungstipps.

---

## 3. Pflicht-Aufbau jeder Kapiteldatei

Jede Kapiteldatei verwendet **genau diese Abschnitte in dieser Reihenfolge**. Abschnitte, die für ein Thema nicht passen, bleiben mit einem kurzen Hinweis („Für dieses Thema nicht relevant") stehen, damit alle Dateien einheitlich sind.

```markdown
# <Kapitelnummer> <Kapiteltitel>

> **Domäne:** <Name der Domäne> · **Gewichtung:** <x–y %>
> **Study-Guide-Punkte:** <wörtliche Skill-Punkte aus dem offiziellen Study Guide, englisch>
> **Stand:** <Monat Jahr>

## Lernziele
- 3–6 Stichpunkte: „Nach diesem Kapitel kann ich …"

## Überblick
Kurze Einordnung (5–10 Sätze): Was ist es, welches Problem löst es, wann nutzt man es?

## Kernkonzepte
Die wichtigsten Begriffe und Funktionsweisen, gegliedert mit `###`-Unterüberschriften.
Fachbegriffe beim ersten Auftreten fett und mit englischem Originalbegriff.

## Zusammenhänge
- Wie spielt das Thema mit anderen Diensten zusammen?
- Verweise auf verwandte Kapitel als relative Links, z. B. [RBAC](../01-identitaeten-und-governance/03-rbac-zugriffsverwaltung.md)
- Wo sinnvoll ein Mermaid-Diagramm (```mermaid) zur Visualisierung.

## Vergleichstabellen
Abgrenzung ähnlicher Optionen (z. B. LRS vs. ZRS vs. GRS, NSG vs. ASG vs. Azure Firewall,
Availability Set vs. Availability Zone). Spalten: Option | Eigenschaft | Einsatzzweck | Einschränkungen.

## Azure Portal
Wo findet man das Feature? Navigationspfade immer im Format:
**Portal > Dienst > Ressource > Menüpunkt > Einstellung**
Zusätzlich: welche Felder beim Erstellen wichtig sind und welche Einstellungen
nach der Erstellung **nicht mehr änderbar** sind.

## Azure CLI & PowerShell
Die wichtigsten Befehle als Codeblöcke (```bash für az, ```powershell für Az-Module),
jeweils mit einem Satz Erklärung. Platzhalter in spitzen Klammern: <resource-group>.

## Praxisbeispiel
Ein durchgängiges, realistisches Szenario Schritt für Schritt
(z. B. „Die Firma Contoso möchte …"). Gerne mit Portal- und CLI-Variante.

## Limits & wichtige Zahlen
Prüfungsrelevante Grenzwerte, Standardwerte, Aufbewahrungsfristen, SKUs.

## Prüfungstipps & Fallstricke
- Typische Fangfragen, häufige Verwechslungen, „Wenn in der Frage X steht, ist Y die Antwort".
- Mit ⚠️ markieren, was besonders oft falsch gemacht wird.

## Selbsttest
5–10 Fragen im Prüfungsstil (Multiple Choice oder Szenario).
Lösungen jeweils in einem einklappbaren Block:
<details><summary>Lösung</summary>Antwort + kurze Begründung</details>

## Weiterführende Links
Nur offizielle Quellen (Microsoft Learn, Azure-Dokumentation).
```

---

## 4. Stil- und Qualitätsregeln

- **Sprache:** Deutsch. Azure-Fachbegriffe, Dienstnamen und Portal-Menüpunkte bleiben **englisch** (so wie sie im Portal und in der Prüfung erscheinen), z. B. „Resource Group", „Access Control (IAM)", „Soft delete".
- **Aktuelle Namen verwenden:** z. B. *Microsoft Entra ID* (nicht mehr „Azure Active Directory"). Den alten Namen beim ersten Auftreten in Klammern nennen, da er in älteren Fragen vorkommen kann.
- **Fachliche Korrektheit vor Vollständigkeit:** Nur Inhalte aufnehmen, die gegen Microsoft Learn / die Azure-Dokumentation geprüft sind. Bei Unsicherheit nachrecherchieren statt raten. Limits und Preise ändern sich – deshalb das Feld **Stand** im Kopf pflegen.
- **Prüfungsfokus:** Inhalte am offiziellen Study Guide ausrichten (<https://learn.microsoft.com/credentials/certifications/resources/study-guides/az-104>). Themen außerhalb des Study Guides höchstens kurz als Kontext erwähnen.
- **Lesbarkeit:** Kurze Absätze, Stichpunkte, Tabellen. Keine Textwüsten. Fett nur für Schlüsselbegriffe.
- **Beispiele:** Fiktive Firmennamen wie *Contoso*, *Fabrikam*, *Northwind*. Keine echten Subscription-IDs, Schlüssel, Kennwörter oder Kundendaten.
- **Code:** Befehle müssen syntaktisch korrekt und mit aktueller Az CLI / Az PowerShell lauffähig sein.
- **Querverweise:** Großzügig zwischen Kapiteln verlinken, damit Zusammenhänge sichtbar werden. Links relativ halten.
- **Umfang:** Richtwert 300–800 Zeilen pro Kapitel. Lieber präzise als aufgebläht.

---

## 5. Vorgehen beim Befüllen eines Kapitels

1. Den passenden Abschnitt im offiziellen Study Guide lesen und die Skill-Punkte in den Kopf der Datei übernehmen.
2. Inhalte anhand von Microsoft Learn recherchieren (Learning Paths zu AZ-104 + Produktdokumentation).
3. Datei nach dem Pflicht-Aufbau (Abschnitt 3) befüllen.
4. Prüfen: Sind alle Study-Guide-Punkte abgedeckt? Stimmen Portal-Pfade, Befehle und Limits?
5. Querverweise zu anderen Kapiteln ergänzen (auch in den bereits befüllten Nachbarkapiteln).
6. In `00-pruefungsueberblick.md` den Status des Kapitels aktualisieren.
7. Committen und pushen (siehe Abschnitt 6).

---

## 6. Git-Workflow

- **Immer direkt auf `main` committen und pushen.** Keine Feature-Branches, keine Pull Requests.
- Nach jeder abgeschlossenen Änderung (z. B. ein befülltes Kapitel) sofort committen und `git push origin main` ausführen.
- Commit-Messages auf Deutsch, Format: `AZ-104: <Kapitel/Bereich> – <was wurde gemacht>`
  Beispiel: `AZ-104: 02-speicher/03-blob-storage – Kapitel befüllt`
- Das Git-Repository-Root liegt eine Ebene höher (`azure/`). Commits auf Dateien in `AZ-104/` beschränken, sofern nicht anders gewünscht.
