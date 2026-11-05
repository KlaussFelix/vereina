# Baukasten-Konzept: Fester Kern und wählbare Module

**Stand:** 05.11.2026
**Status:** Grundsatzentscheidung getroffen (Kern + Module). Details sind ein Entwurf.

**Bezug:** [Anforderungen an vereina](2026-11-05-anforderungen-vereina.md). Die Kennungen
(MIT-01, BEI-02 …) verweisen auf dieses Dokument.

---

## 1. Die Idee

vereina ist ein **Baukasten**. Jeder Verein wählt aus einem Katalog die Module, die er braucht,
und bekommt so „seine“ App. Technisch bleibt es **eine Anwendung**: Oberfläche und Funktionen
richten sich nach der Auswahl, eigene Apps oder Programmversionen pro Verein gibt es nicht.

**Warum:**
- **Weniger ist einfacher.** Vereine sehen nur, was sie nutzen (Leitprinzipien P1, P2).
- **Leichter Einstieg.** „Fangt mit der Helferplanung fürs Sommerfest an“ ist eine kleinere Hürde
  als eine komplette Umstellung.
- **Ersetzen oder ergänzen, beides geht.** Ein Verein, der schon eine Vereinsverwaltung nutzt,
  lässt z. B. Beiträge und Finanzen weg und nutzt vereina für die Organisation. Damit ist die
  offene Frage 3 aus den Anforderungen beantwortet.
- **Datensparsamkeit.** Es werden nur die Daten erhoben, die die eingeschalteten Module brauchen.
- **Schrittweise Entwicklung.** Schon die erste Version ist vollständig, nur mit wenigen Modulen.

**Das Risiko:** Wenn alles abwählbar ist, zerfällt vereina wieder in Einzeltools unter einem Dach.
Das Prinzip „Daten nur einmal erfassen“ (P4) lebt von gemeinsamen Daten. Deshalb gibt es einen
**festen Kern**, den jeder Verein hat.

---

## 2. Der feste Kern

Der Kern ist **immer aktiv und bewusst klein**. Er enthält die gemeinsamen Daten und Dienste, auf
denen alle Module aufbauen.

| Kern-Baustein | Inhalt | Anforderungen |
| --- | --- | --- |
| **Vereinsprofil** | Stammdaten des Vereins und Merkmale (e. V., gemeinnützig, Jugendarbeit, Dachverband …) | PFL-01 |
| **Personen und Gruppen** | Minimale Personendaten (Name, Kontakt), Gruppen und Abteilungen, Import/Export | Teil von MIT-01, MIT-07 |
| **Rollen und Rechte** | Ämter und Funktionen mit Rechten bis auf Feldebene; **Amtsübergabe als Rechteübertragung** | DSG-01, WIS-01 |
| **Benachrichtigungen** | Ein Dienst für alle Kanäle: App, E-Mail, Druck/Brief (SMS optional) | KOM-02 |
| **Aufgaben und Erinnerungen** | Aufgaben mit Zuständigkeit, Frist, Erinnerung und Übergabe. Module erzeugen hier ihre Aufgaben (z. B. „Vorstandswechsel anmelden“, „Protokoll schreiben“). | AUF-02 |
| **Dateiablage** | Gemeinsame Ablage, die alle Module nutzen (Belege, Protokolle, Satzung) | Teil von WIS-03 |
| **Datenschutz-Grundlagen** | Einwilligungen, Auskunft, Löschfristen, Verzeichnis der Verarbeitungstätigkeiten aus der Modulauswahl | DSG-02 bis DSG-05 |
| **Modulverwaltung** | Module ein- und ausschalten, auf Vereins- und Abteilungsebene | – |
| **Schnittstelle (API)** | Export und Datenzugriff für externe Tools | NF-08 |

**Begründung für Aufgaben im Kern:** „Lästiges abgeben können“ ist der Grundgedanke von vereina.
Fast jedes Modul erzeugt Aufgaben oder Fristen. Ein gemeinsamer Aufgabendienst sorgt dafür, dass
alles an einer Stelle landet („Meine Aufgaben“) und übergeben werden kann.

**Wichtig:** Ein Verein, der „keine Mitglieder dokumentieren“ will, verzichtet auf das Modul
Mitgliederverwaltung (Bankdaten, Beitragsgruppen, Status). Personen mit Name und Kontakt gibt es
trotzdem, weil Helferplanung, Kommunikation und Aufgaben sie brauchen.

---

## 3. Der Modulkatalog

| # | Modul | Was es bringt | Anforderungen | Benötigt |
| --- | --- | --- | --- | --- |
| M1 | **Mitgliederverwaltung** | Ausführliche Stammdaten, Online-Beitritt, Selbstpflege, Statuswechsel, Austritt, Jubiläen, Willkommensstrecke | MIT-02 bis -06, -08, OEF-01, OEF-04 | – |
| M2 | **Beiträge und SEPA** | Beitragsberechnung, automatischer Beitragslauf, Mandate, Zahlungsabgleich, Mahnwesen | BEI-01 bis -06 | M1 |
| M3 | **Finanzen und Belege** | Belege per Foto, Kassenbuch, Auswertungen, Kassenprüfung, Export für Steuerberater | FIN-01 bis -08, VGT-01 | – |
| M4 | **Spenden** | Zuwendungsbestätigungen, Aufwandsspenden, Spendenformular | SPE-01 bis -04 | M3 |
| M5 | **Kommunikation** | Nachrichten an Zielgruppen, Chat, Lesebestätigung, Umfragen, Newsletter | KOM-01, -03 bis -06 | – |
| M6 | **Termine und Anwesenheit** | Termine, Zu-/Absage mit Nachhaken, Kalender-Abo, Anwesenheit, Fahrgemeinschaften, Terminfindung | TER-01 bis -06 | – |
| M7 | **Aufgabenbörse und Engagement** | Aufgaben zum Übernehmen, Amtsbeschreibungen, Vertretungen, Pflicht- und Ehrenamtsstunden, Wertschätzung | AUF-01, -03 bis -07 | – |
| M8 | **Helfer und Veranstaltungen** | Helferschichten, Mitbringlisten, Veranstaltungsvorlagen mit Rückwärtsplanung, Tickets | VER-01 bis -06 | – |
| M9 | **Gremien und Versammlungen** | MV-Assistent, Anträge, Anwesenheit und Stimmrecht, Abstimmungen, Protokoll, Beschlussregister, Umlaufbeschlüsse | GRE-01 bis -08 | – |
| M10 | **Pflichten und Fristen** | Pflichtenkalender aus dem Vereinsprofil, Rechtsänderungen, Vorbereitung von Steuererklärung und Registeranmeldung | PFL-02 bis -07 | – |
| M11 | **Wissen und Übergabe** | Übergabe-Checklisten, Handbuch je Amt, Vereinsgedächtnis, Vertragsübersicht | WIS-02 bis -06 | – |
| M12 | **Qualifikationen und Kinderschutz** | Lizenzen mit Ablauf, Führungszeugnis-Workflow, Kinderschutzkonzept | QUA-01 bis -04 | – |
| M13 | **Vergütungen und Pauschalen** | Pauschalen-Wächter, Übungsleiter-Abrechnung, Vorlagen für Vereinbarungen | VGT-02 bis -04 | M3 |
| M14 | **Ressourcen** | Belegungsplan, Inventar, Schlüsselbuch, Wartungstermine | RES-01 bis -04 | – |
| M15 | **Förderung und Verbände** | Bestandserhebung, Fördermittel-Akte, Verwendungsnachweis | FOE-01 bis -03 | – |
| M16 | **Kurse und Angebote** | Kurse für Nichtmitglieder, Probetraining, Einmalzahlungen | OEF-03, OEF-05, BEI-07 | – |
| M17 | **Website-Bausteine** | Einbettbare Termine, Angebote und Beitrittsformular für die eigene Website | OEF-02 | – |

**KI-Assistenz** ist kein eigenes Modul, sondern eine **zuschaltbare Querschnittsfunktion**
(KI-01 bis KI-05). Sie wirkt in den Modulen (Protokollentwurf in M9, Belegerkennung in M3 …) und
kann vom Verein komplett abgeschaltet werden, z. B. aus Datenschutzgründen.

---

## 4. Wie Module zusammenspielen

Es gibt zwei Arten von Beziehungen:

### 4.1 „Benötigt“ (harte Abhängigkeit)
Ein Modul funktioniert ohne ein anderes nicht. Beim Einschalten fragt vereina nach:
„*Spenden benötigt Finanzen und Belege. Mit einschalten?*“

| Modul | benötigt |
| --- | --- |
| M2 Beiträge und SEPA | M1 Mitgliederverwaltung |
| M4 Spenden | M3 Finanzen und Belege |
| M13 Vergütungen und Pauschalen | M3 Finanzen und Belege |

### 4.2 „Ergänzt“ (Verknüpfung, die automatisch aufleuchtet)
Beide Module funktionieren allein. Sind beide aktiv, entsteht ein Zusatznutzen. **Genau das
unterscheidet vereina von Einzeltools.**

| Wenn aktiv … | … und … | … dann |
| --- | --- | --- |
| M8 Helfer | M7 Aufgabenbörse | Helferschichten zählen auf die Pflichtstunden |
| M6 Termine | M13 Vergütungen | Übungsleiter-Abrechnung direkt aus der Anwesenheit |
| M6 Termine | M15 Förderung | Teilnehmerzahlen fließen in Verwendungsnachweise |
| M9 Gremien | M10 Pflichten | Nach einer Wahl entsteht automatisch „Vorstandswechsel anmelden“ |
| M9 Gremien | M11 Wissen | Nach einer Wahl entsteht automatisch die Übergabe-Checkliste |
| M8 Veranstaltungen | M3 Finanzen | Die Festtagskasse landet in der richtigen Sphäre |
| M2 Beiträge | M4 Spenden | Spenden und Beiträge werden zusammen abgeglichen |
| M12 Qualifikationen | M6 Termine | Warnung, wenn eine Trainingsgruppe mit Kindern keine Person mit gültigem Führungszeugnis hat |
| M1 Mitglieder | M15 Förderung | Bestandserhebung direkt aus den Mitgliederdaten |

---

## 5. Zwei Ebenen: Verein und Abteilung

**Regel:** Der Vorstand legt fest, welche Module dem Verein **zur Verfügung stehen**. Jede
Abteilung wählt daraus, was sie **selbst nutzt**. Eine Abteilung kann nichts einschalten, was der
Verein nicht freigegeben hat.

Nicht jedes Modul passt auf beide Ebenen:

| Ebene | Module |
| --- | --- |
| **Nur vereinsweit** | M2 Beiträge, M4 Spenden, M9 Gremien (Mitgliederversammlung), M10 Pflichten, M15 Förderung |
| **Pro Abteilung wählbar** | M5 Kommunikation, M6 Termine und Anwesenheit, M7 Aufgabenbörse, M8 Helfer und Veranstaltungen, M14 Ressourcen, M16 Kurse |
| **Zu klären** | M3 Finanzen (eigene Abteilungskassen?), M12 Qualifikationen, M13 Vergütungen |

Beispiel: Die Fußballabteilung nutzt Termine mit Anwesenheit, die Theatergruppe nur Termine und
Helferschichten.

---

## 6. Ein- und Ausschalten

### 6.1 Einschalten
- Das Modul ist sofort nutzbar und hat sinnvolle Voreinstellungen (NF-04).
- Harte Abhängigkeiten werden abgefragt (Kapitel 4.1).
- Neue Verknüpfungen werden kurz erklärt („*Neu: Helferschichten zählen jetzt auf eure
  Pflichtstunden.*“).
- Das Verzeichnis der Verarbeitungstätigkeiten wird automatisch ergänzt.

### 6.2 Ausschalten
Beim Abschalten dürfen keine Daten unbemerkt verloren gehen. Vorschlag:

1. **Hinweis vorab:** Welche Daten betroffen sind und welche anderen Module davon abhängen.
2. **Export anbieten** (z. B. als Excel/PDF).
3. **Daten ruhen** zunächst ausgeblendet. Beim Wiedereinschalten sind sie wieder da.
4. **Löschung nach einer Frist**, sofern keine Aufbewahrungspflicht besteht.
5. **Ausnahme Aufbewahrungspflichten:** Finanzdaten und Belege dürfen nicht vorzeitig gelöscht
   werden (Belege 8 Jahre, Bücher und Abschlüsse 10 Jahre, siehe R2 4.3). Sie bleiben lesbar
   archiviert, bis die Frist abgelaufen ist.

---

## 7. Einstieg: Vorschläge statt leerer Liste

Ein Katalog mit 17 Modulen kann überfordern. Darum gibt es zwei Hilfen:

### 7.1 Modulvorschläge aus dem Vereinsprofil

| Merkmal im Profil | Vorschlag |
| --- | --- |
| Eingetragener Verein | M9 Gremien, M10 Pflichten |
| Gemeinnützig, nimmt Spenden an | M3 Finanzen, M4 Spenden |
| Jugendarbeit | M12 Qualifikationen und Kinderschutz |
| Pflichtstunden laut Satzung | M7 Aufgabenbörse (Stundenerfassung) |
| Mitglied im Landessportbund / Dachverband | M15 Förderung und Verbände |
| Lizenzierte Übungsleiter, Pauschalen | M6 Termine und Anwesenheit, M13 Vergütungen |
| Feste und Veranstaltungen | M8 Helfer und Veranstaltungen |
| Eigenes Vereinsheim, Geräte | M14 Ressourcen |
| Schon eine andere Vereinsverwaltung im Einsatz | M1/M2/M3 weglassen, Fokus auf Organisation |

### 7.2 Startpakete
Vorkonfigurierte Auswahl als Ausgangspunkt, jederzeit änderbar. Beispiele:

| Startpaket | Module |
| --- | --- |
| **Organisation pur** (neben bestehender Verwaltung) | M5, M6, M7, M8, M10 |
| **Kleiner Verein komplett** | M1, M2, M3, M5, M6, M9, M10 |
| **Sportverein mit Abteilungen** | M1, M2, M3, M5, M6, M7, M8, M9, M10, M12, M13, M15 |
| **Förderverein** | M1, M2, M3, M4, M5, M9, M10 |

---

## 8. Architekturregeln

Damit der Baukasten sauber bleibt und später erweiterbar ist:

1. **Module sprechen nur über den Kern miteinander.** Kein Modul greift direkt auf die Daten
   eines anderen zu. Verknüpfungen (Kapitel 4.2) laufen über klar definierte Schnittstellen
   und Ereignisse (z. B. „Wahl abgeschlossen“, „Helferschicht bestätigt“).
2. **Jedes Modul funktioniert ohne die anderen.** Verknüpfungen sind Zusatznutzen, keine
   Voraussetzung (Ausnahme: harte Abhängigkeiten aus 4.1).
3. **Module bringen ihre Bedürfnisse selbst mit:** welche Daten sie brauchen, welche Rechte es
   gibt, welche Einträge sie zum Verzeichnis der Verarbeitungstätigkeiten beitragen und wie ihre
   Daten beim Abschalten behandelt werden.
4. **Später feiner schaltbar:** Module so bauen, dass einzelne Funktionen innerhalb eines Moduls
   später einzeln an- und abschaltbar werden können. Zum Start werden aber nur ganze Module
   geschaltet.

---

## 9. Für später: Plugin-System

**Idee:** Nicht nur vereina selbst, sondern auch andere bauen Module, z. B. ein Verband, ein
Entwickler oder ein Verein mit einem programmierenden Mitglied. Beispiele: Flugbuch für
Luftsportvereine, Parzellenverwaltung für Kleingärten, Notenarchiv für Musikvereine,
Schnittstelle zu DFBnet.

**Entscheidung:** Gute Idee, aber **bewusst nach hinten verschoben**.

**Was jetzt schon dafür getan wird:**
- Die Architekturregeln aus Kapitel 8 gelten auch für die eigenen Module. Wer sich an sie hält,
  baut von Anfang an „wie ein Plugin“, und ein Plugin-System lässt sich später nachrüsten.
- Die offene Schnittstelle (NF-08) erlaubt externen Tools schon vorher eine Anbindung.

**Was vor einem Plugin-System geklärt werden muss:**
- Sicherheit und Datenschutz: Rechte pro Plugin, Prüfung und Freigabe fremder Module.
- Qualität und Support: Wer hilft, wenn ein fremdes Plugin nicht funktioniert?
- Eine stabile, dokumentierte Schnittstelle mit Versionierung.

---

## 10. Offene Fragen

1. **Finanzen pro Abteilung:** Brauchen Abteilungen eigene Kassen bzw. Kostenstellen?
2. **Preismodell:** Preis pro Modul, nach Startpaketen oder pauschal? Ein Preis pro Modul liegt
   nahe, kann aber unübersichtlich werden (Leitprinzip P9).
3. **Zuschnitt des Kerns:** Gehört die Dateiablage wirklich in den Kern, oder reicht eine
   Ablage pro Modul?
4. **Startpakete:** Welche Pakete brauchen die ersten Zielvereine wirklich? (Klärung in den
   Gesprächen mit Vereinen)
