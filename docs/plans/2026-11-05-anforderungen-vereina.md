# Anforderungen an vereina: Was das Tool können muss

**Stand:** 05.11.2026
**Status:** Erster Entwurf. Die Anforderungen beruhen nur auf Recherche und müssen noch mit
Vereinen überprüft werden.

**Grundlage:**
- **R1:** [Marktrecherche: Bestehende Tools](../research/2026-11-05-bestehende-vereinssoftware.md)
- **R2:** [Entlastungspotenziale in der Vereinsarbeit](../research/2026-11-05-entlastungspotenziale-vereinsarbeit.md)

> **Baukasten:** vereina besteht aus einem festen Kern und wählbaren Modulen. Welche Anforderung
> zu welchem Kern-Baustein oder Modul gehört, steht im
> [Baukasten-Konzept](2026-11-05-baukasten-konzept.md). Die Ausbaustufen in Kapitel 5 sagen,
> **wann** etwas gebaut wird. Das Baukasten-Konzept sagt, **wo** es hingehört.

---

## 1. Worum es geht

Ein mittelgroßer Verein verbringt rund **6,5 Stunden pro Woche** mit Bürokratie (R2 §2.2), und nur
**24 %** der Organisationen finden genug Leute für Leitungsämter (R2 §1). Gleichzeitig sind die
bestehenden Tools vor allem eines: Verwaltungssoftware für den Vorstand, die oft als kompliziert
gilt und meist neben WhatsApp, Excel und weiteren Apps läuft (R1 §4.3).

Daraus folgt der Auftrag für vereina:

> **vereina nimmt Ehrenamtlichen Arbeit ab, verteilt den Rest auf viele Schultern und kennt die
> Regeln, damit Ehrenamtliche sie nicht kennen müssen.**

Das Tool muss deshalb drei Dinge leisten:

1. **Ablösen:** Routinearbeit automatisch erledigen (Beiträge, Bescheinigungen, Erinnerungen).
2. **Verteilen:** Aufgaben klein machen und abgebbar machen (Aufgabenbörse, Helfer, Rollen).
3. **Führen:** Pflichten und Fristen kennen und rechtzeitig daran erinnern (Pflichtenkalender).

---

## 2. Leitprinzipien (gelten für jede Funktion)

| # | Prinzip | Was das konkret heißt | Herkunft |
| --- | --- | --- | --- |
| P1 | **Entlasten statt belasten** | Jede Funktion muss nachweislich Zeit sparen. Funktionen, die nur Pflege erzeugen, kommen nicht hinein. | README, R1 §4.3 |
| P2 | **Ohne Schulung bedienbar** | Ehrenamtliche ohne IT- und Buchhaltungswissen kommen allein zurecht. Fachbegriffe werden erklärt oder vermieden. | R1 §4.3, R2 §5.4 |
| P3 | **Die Regeln stecken im Tool** | Fristen, Pflichten und Rechtsstände (z. B. Pauschalen 2026) kennt die Software, und sie erklärt sie mit Quelle. | R2 §5.1 |
| P4 | **Daten nur einmal erfassen** | Mitglieder, Rollen, Termine und Geld bilden eine gemeinsame Datenbasis. Verteiler, Listen, Berichte und Nachweise entstehen daraus von selbst. | R2 §9, R1 §4.3 |
| P5 | **Datenschutz von sich aus richtig** | Datenschutz ist die größte Einzelbelastung. Das Tool arbeitet standardmäßig datenschutzkonform und erzeugt die Dokumentation nebenbei. | R2 §4.9 |
| P6 | **Arbeit verteilen, ohne Kontrolle zu verlieren** | Feine Rollen und Rechte: Jede Person sieht nur, was sie für ihre Aufgabe braucht. | R2 §5.3 |
| P7 | **Niemanden abhängen** | Es gibt eine mobile Nutzung für die Halle oder den Festplatz und Wege für Mitglieder ohne Smartphone oder E-Mail (Druck, Brief, SMS). | R2 §5.4, R1 (Konzertmeister) |
| P8 | **Mensch entscheidet** | Alles, was rechtlich wirkt oder nach außen geht, gibt ein Mensch frei. Das gilt auch für KI-Vorschläge. | R2 §5.2, §7 |
| P9 | **Bezahlbar für kleine Vereine** | Das Preismodell muss zu Vereinsbudgets passen. Gratis-Tarife der Konkurrenz sind oft so beschnitten, dass sie kaum nutzbar sind. | R1 §4.3, R2 §5.4 |
| P10 | **Nur einschalten, was man braucht** | Ein fester Kern ist immer da, alles andere sind Module, die Verein und Abteilungen selbst wählen. Was nicht eingeschaltet ist, taucht nicht auf und erhebt keine Daten. | [Baukasten-Konzept](2026-11-05-baukasten-konzept.md) |

---

## 3. Funktionale Anforderungen

**Stufen** (Vorschlag, siehe Kapitel 5):
**1** = Kern der ersten Version · **2** = Ausbau · **3** = später / optional
**★** = Abgrenzung zur Konkurrenz (laut R1 kaum am Markt vorhanden)

### 3.1 Mitgliederverwaltung

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| MIT-01 | Mitglieder mit Stammdaten, Beitragsgruppen, Familienmitgliedschaften und Abteilungen verwalten | 1 | R1 §4.1, R2 4.1 |
| MIT-02 | **Online-Beitrittsformular** mit SEPA-Mandat, Einwilligungen und digitaler Bestätigung, damit nichts mehr abgetippt werden muss | 1 | R2 4.1 |
| MIT-03 | **Selbstpflege** durch Mitglieder (Adresse, Bankverbindung, Einwilligungen) im Mitgliederbereich | 1 | R2 4.1 |
| MIT-04 | Automatische Statuswechsel nach Regeln (Altersgrenze, befristete Ermäßigung mit Nachweis-Erinnerung) | 2 | R2 4.1 |
| MIT-05 | Geführter Austritt: Frist prüfen, Bestätigung erzeugen, Löschfristen vormerken | 2 | R2 4.1 |
| MIT-06 | Jubiläen und Ehrungen automatisch pro Jahr auflisten | 2 | R2 4.1 |
| MIT-07 | Import aus und Export nach Excel/CSV, damit der Umstieg leicht fällt | 1 | R1 §6.1 |
| MIT-08 | Auswertungen und Listen auf Knopfdruck (Versammlung, Trainer, Zuschüsse) | 1 | R2 4.1 |

### 3.2 Beiträge, Zahlungen und Mahnwesen

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| BEI-01 | Beitragsberechnung nach Gruppen, Familien, anteiligen Zeiträumen, Abteilungs- und Aufnahmegebühren | 1 | R2 4.2 |
| BEI-02 | **Automatischer Beitragslauf**: Berechnung → Vorabankündigung per E-Mail → SEPA-Datei | 1 | R2 4.2 |
| BEI-03 | Mandatsverwaltung (Gläubiger-ID, Mandatsreferenz) | 1 | R2 4.2 |
| BEI-04 | Automatischer **Zahlungsabgleich** über eine Kontoanbindung | 2 | R2 4.2 |
| BEI-05 | Rücklastschriften: automatische Info an das Mitglied, Gebühr laut Beitragsordnung, Link zur Korrektur | 2 | R2 4.2 |
| BEI-06 | **Gestuftes, freundliches Mahnwesen**, damit der Kassenwart nicht persönlich nachhaken muss | 2 | R2 4.2 |
| BEI-07 | Einmalzahlungen (Veranstaltungen, Kurse, Kleidung) online, mit automatischer Verbuchung | 3 | R2 4.2, R1 (Spond, Vereinsplaner) |

### 3.3 Finanzen, Belege und Kassenprüfung

> ⚠️ **Hier widersprechen sich die beiden Recherchen.** R1 empfiehlt, auf eine *vollwertige
> Buchhaltung* zu verzichten (aufwendig, starke Konkurrenz). R2 stuft Buchhaltung als
> *hoch priorisiert* ein (häufig, schmerzhaft, das Kassenwart-Amt ist unbeliebt). Vorschlag:
> **Belege, Kasse und Auswertungen** übernimmt vereina selbst, für die **Buchhaltung im engeren
> Sinn** gibt es einen Export zu Fachsoftware (DATEV-Format).
>
> Durch den Baukasten ist die Frage **entschärft**: Finanzen sind ein eigenes Modul (M3), und
> Vereine mit bestehender Buchhaltung lassen es einfach weg. Offen bleibt, **wie weit das Modul
> reicht** (siehe Kapitel 7).

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| FIN-01 | **Belegerfassung per Foto** durch jede berechtigte Person, mit Texterkennung und Vorschlag für Kategorie und Sphäre | 2 | R2 4.3 |
| FIN-02 | Digitales Kassenbuch für Barkassen, auch mobil am Festtag, mit Kassensturz | 2 | R2 4.3 |
| FIN-03 | Einnahmen-Überschuss-Rechnung, Auswertung nach den vier Sphären und **Kassenbericht auf Knopfdruck** | 2 | R2 4.3 |
| FIN-04 | **Lesezugang für Kassenprüfer**: Buchungen und Belege sehen, abhaken, kommentieren, Prüfbericht erzeugen | 2 | R2 4.3 |
| FIN-05 | Ablage mit automatischen Aufbewahrungs- und Löschfristen | 2 | R2 4.3 |
| FIN-06 | Export für Steuerberater und Buchhaltungssoftware (z. B. DATEV-Format) | 2 | R1 §6.3 |
| FIN-07 | E-Rechnungen empfangen (XRechnung/ZUGFeRD), wo nötig auch ausstellen | 3 | R2 4.3 |
| FIN-08 | Warnung beim Überschreiten von Schwellen (z. B. Freigrenze 50.000 €) | 3 | R2 4.3, 4.5 |

### 3.4 Spenden

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| SPE-01 | **Zuwendungsbestätigungen automatisch** aus den Buchungen erzeugen (einzeln oder als Jahres-Sammelbestätigung), per E-Mail versenden, Doppel archivieren | 2 | R2 4.4 |
| SPE-02 | Warnung, wenn der Freistellungsbescheid für das Ausstellen nicht mehr gültig ist | 2 | R2 4.4 |
| SPE-03 | Geführter Ablauf für **Aufwandsspenden** mit Fristwächter | 3 | R2 4.4 |
| SPE-04 | Online-Spendenformular | 3 | R2 4.4 |

### 3.5 Kommunikation

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| KOM-01 | **Zielgruppen ergeben sich automatisch** aus Personen, Gruppen und Rollen im Kern (Abteilung, Mannschaft, Funktion, Eltern), auch ohne das Modul Mitgliederverwaltung; Ein- und Austritte aktualisieren die Verteiler | 1 | R2 4.10 |
| KOM-02 | Ein Kanal, mehrere Wege: App-Nachricht, E-Mail und **Druckversion für Mitglieder ohne Internet** | 1 | R2 4.10, R1 (Konzertmeister) |
| KOM-03 | Lesebestätigung bzw. Übersicht „Wer hat es noch nicht gesehen?“ | 2 | R2 4.10 |
| KOM-04 | Umfragen unter Mitgliedern | 1 | R2 4.10, R1 §5.2 |
| KOM-05 | Chat bzw. Gruppennachrichten als datenschutzkonforme Alternative zu WhatsApp-Gruppen | 2 | R2 4.10, R1 §4.3 |
| KOM-06 | Newsletter aus vorhandenen Inhalten zusammenstellen | 3 | R2 4.10 |

### 3.6 Termine, Training und Anwesenheit

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| TER-01 | Termine und Serientermine mit Zielgruppen | 1 | R1 §4.1, R2 4.11 |
| TER-02 | Zu- und Absagen mit **automatischem Nachhaken** bei fehlender Antwort | 1 | R2 4.11, R1 (Spond, SpielerPlus) |
| TER-03 | Kalender-Abo (iCal) für Mitglieder | 1 | R2 4.11, R1 (ClubDesk) |
| TER-04 | **Anwesenheit per Antippen**, daraus Statistik, Übungsleiter-Abrechnung und Zuschussnachweise | 2 | R2 4.11 |
| TER-05 | Fahrgemeinschaften anbieten und buchen | 3 | R2 4.11, R1 (SpielerPlus) |
| TER-06 | Terminfindung für Sitzungen ohne externe Umfragetools | 2 | R2 4.7 |

### 3.7 Aufgaben verteilen und Engagement ★

Diese Funktionen bilden den Kern des Grundgedanken „Lästiges abgeben können“. Laut R1 bietet das
kaum ein Tool.

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| AUF-01 | ★ **Aufgabenbörse**: kleine, klar beschriebene Aufgaben („Protokoll am 12.3.“, „Kuchen fürs Sommerfest“), die Mitglieder mit einem Klick übernehmen | 1 | R2 4.14, R1 §4.6 |
| AUF-02 | Aufgaben mit Zuständigkeit, Frist, Erinnerung und **Übergabe an eine andere Person** | 1 | R1 §4.6, R2 4.7 |
| AUF-03 | ★ Rollen- und Aufgabenbeschreibung je Amt (was gehört dazu, wie viel Zeit kostet es), damit die Hemmschwelle zur Übernahme sinkt | 2 | R2 4.14 |
| AUF-04 | Vertretungen festlegen („Wer springt ein, wenn der Kassenwart krank ist?“) | 2 | R2 4.14 |
| AUF-05 | ★ **Pflichtstunden**: erfassen, bestätigen, Saldo führen, Ersatzrechnung am Jahresende automatisch erstellen | 2 | R2 4.14, R1 (Vereinsflieger) |
| AUF-06 | ★ **Ehrenamtsstunden** sichtbar machen; Engagement-Nachweis bzw. Ehrenamtsbescheinigung automatisch erzeugen | 2 | R2 4.14, R1 §4.6 |
| AUF-07 | Wertschätzung: Übersicht „Wer hat dieses Jahr mitgeholfen?“, Danke-Nachrichten | 3 | R2 4.14 |

### 3.8 Veranstaltungen und Helferplanung

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| VER-01 | ★ **Helferschichten zum Selbsteintragen**, mit Erinnerungen und Tauschbörse; Anrechnung auf Pflichtstunden | 1 | R2 4.13, R1 §4.6 |
| VER-02 | Mitbring- und Kuchenlisten | 1 | R2 4.13 |
| VER-03 | ★ **Veranstaltungsvorlagen mit Rückwärtsplanung**: Datum eingeben, dann erscheint eine Checkliste mit Fristen (Gestattung, GEMA, Versicherung); die Vorlage vom Vorjahr lässt sich kopieren | 2 | R2 4.13 |
| VER-04 | Nachbereitung als Notiz an der Vorlage („Was machen wir nächstes Mal anders?“) | 2 | R2 4.13 |
| VER-05 | Anmeldung und Tickets mit Zahlung | 3 | R2 4.13 |
| VER-06 | Festtagskasse direkt in die Finanzen übernehmen, Sphäre vorbelegt | 3 | R2 4.13 |

### 3.9 Gremienarbeit: Mitgliederversammlung und Sitzungen

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| GRE-01 | **MV-Assistent**: Termin festlegen → Frist laut Satzung berechnen → Einladung mit Tagesordnung an alle (E-Mail bzw. Brief-Export) | 2 | R2 4.7 |
| GRE-02 | Online-Anträge mit Frist, die automatisch in die Tagesordnung übernommen werden | 2 | R2 4.7 |
| GRE-03 | Digitale Anwesenheitsliste mit Prüfung der Stimmberechtigung; Beschlussfähigkeit live | 2 | R2 4.7 |
| GRE-04 | Offene Abstimmungen, auch hybrid oder virtuell | 2 | R2 4.7, R1 (easyVerein, OpenSlides) |
| GRE-05 | **Protokollentwurf** aus Tagesordnung, Abstimmungsergebnissen und Stichpunkten | 2 | R2 4.7 |
| GRE-06 | **Beschlussregister**: alle Beschlüsse durchsuchbar, mit Datum, Gremium und Ergebnis | 2 | R2 4.7 |
| GRE-07 | Aufgaben direkt aus dem Protokoll zuweisen (verknüpft mit AUF-02) | 2 | R2 4.7 |
| GRE-08 | Umlaufbeschlüsse im Vorstand digital in Textform | 2 | R2 4.7 |

### 3.10 Pflichten und Fristen ★

Die zentrale Idee aus R2: Ein **Vereinsprofil** wird einmal ausgefüllt, daraus entsteht ein
individueller Pflichtenkalender.

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| PFL-01 | ★ **Vereinsprofil** (e. V., gemeinnützig, Dachverband, Jugendarbeit, Ausschank, Minijobs, Immobilie, Pflichtstunden …) | 1 | R2 §5.1 |
| PFL-02 | ★ **Pflichtenkalender**, der aus dem Profil automatisch erzeugt wird und Erinnerungen an die zuständige Rolle schickt | 1 | R2 §5.1, §6 |
| PFL-03 | Wiedervorlage, bis eine Pflicht erledigt ist (z. B. „Vorstandswechsel beim Vereinsregister angemeldet?“) | 1 | R2 4.8 |
| PFL-04 | Kurze Erklärung mit Quelle zu jeder Pflicht (Orientierung, keine Rechtsberatung) | 1 | R2 §5.2, §7 |
| PFL-05 | Hinweis „Was ist neu?“ bei Rechtsänderungen (z. B. höhere Pauschalen ab 2026) | 2 | R2 4.5 |
| PFL-06 | Steuererklärung vorbereiten: Auswertung nach Sphären über drei Jahre, **Tätigkeitsbericht** aus vorhandenen Daten | 3 | R2 4.5 |
| PFL-07 | Entwurf der Anmeldung beim Vereinsregister mit Checkliste der Anlagen | 3 | R2 4.8 |

### 3.11 Wissen sichern und Amtsübergabe ★

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| WIS-01 | ★ **Amtsübergabe als Rechteübertragung**: Die Rolle bekommt eine neue Person, und Daten, Vorgänge, Fristen und Dokumente bleiben erhalten | 1 | R2 4.17, R1 §4.6 |
| WIS-02 | Übergabe-Checkliste je Amt, die nach einer Wahl automatisch erzeugt wird (Bankvollmacht, Zugänge, Register) | 2 | R2 4.17 |
| WIS-03 | Dokumentenablage mit fester Struktur (Satzung mit Versionen, Ordnungen, Protokolle, Verträge, Bescheide) | 1 | R2 4.17, R1 §4.1 |
| WIS-04 | „Handbuch“ je Amt mit Abläufen, Ansprechpartnern und Jahreskalender, das bei der Nutzung mitwächst | 2 | R2 4.17 |
| WIS-05 | Suche über Beschlüsse, Protokolle und Veranstaltungsnotizen („Vereinsgedächtnis“) | 3 | R2 4.17 |
| WIS-06 | Vertragsübersicht mit Kündigungsfristen und Wiedervorlage | 3 | R2 4.18 |

### 3.12 Datenschutz

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| DSG-01 | **Rollen und Rechte bis auf Feldebene** (z. B. sieht ein Trainer nur seine Gruppe und nur die nötigen Felder) | 1 | R2 4.9, §5.3 |
| DSG-02 | Einwilligungen (Fotos, Veröffentlichung, Newsletter) je Mitglied, mit Filter „darf veröffentlicht werden“ | 1 | R2 4.9 |
| DSG-03 | **Verzeichnis der Verarbeitungstätigkeiten automatisch** aus den eingeschalteten Modulen erzeugen | 2 | R2 4.9 |
| DSG-04 | Auskunft nach Art. 15 DSGVO als Export auf Knopfdruck | 2 | R2 4.9 |
| DSG-05 | Automatische Löschung bzw. Anonymisierung nach Ablauf der Fristen | 2 | R2 4.9 |
| DSG-06 | Vorlagen für Datenschutzhinweise und Einwilligungstexte | 2 | R2 4.9 |

### 3.13 Qualifikationen und Kinderschutz

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| QUA-01 | Qualifikationsregister je Person (Lizenzen, Erste Hilfe, Jugendleiter-Card) mit Ablaufdatum und Erinnerung | 2 | R2 4.15 |
| QUA-02 | **Workflow für Führungszeugnisse**: Aufforderung → Einsicht dokumentieren (nur zulässige Felder) → Wiedervorlage nach 5 Jahren → automatische Löschung | 2 | R2 4.15 |
| QUA-03 | Übersicht „Wer darf mit Kindern arbeiten?“ | 2 | R2 4.15 |
| QUA-04 | Checkliste und Vorlagen für ein Kinderschutzkonzept; Ehrenkodex digital unterzeichnen | 3 | R2 4.15 |

### 3.14 Vergütungen und Auslagen

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| VGT-01 | **Auslagen-Workflow**: Foto + Betrag → Freigabe durch die zuständige Person → Überweisung oder Aufwandsspende | 2 | R2 4.6 |
| VGT-02 | **Pauschalen-Wächter**: Summe je Person und Jahr (Ehrenamt 960 €, Übungsleiter 3.300 €), Warnung vor Überschreiten, Erklärung der Person einholen | 2 | R2 4.6 |
| VGT-03 | Übungsleiter-Abrechnung aus der Anwesenheit (verknüpft mit TER-04) | 2 | R2 4.6 |
| VGT-04 | Vorlagen für Vereinbarungen zu Ehrenamt, Übungsleitung und Minijob | 3 | R2 4.6 |

### 3.15 Ressourcen

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| RES-01 | Belegungsplan für Hallen und Räume mit Konfliktprüfung | 3 | R2 4.12, R1 (easyVerein) |
| RES-02 | Inventar mit Foto, Standort und Wert; Ausleihe per QR-Code | 3 | R2 4.12 |
| RES-03 | Digitales Schlüsselbuch mit Erinnerung bei Austritt oder Amtswechsel | 3 | R2 4.12 |
| RES-04 | Wartungs- und Prüftermine im Pflichtenkalender | 3 | R2 4.12 |

### 3.16 Förderung und Verbände

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| FOE-01 | **Bestandserhebung auf Knopfdruck** im geforderten Format, mit Erinnerung an die Frist | 2 | R2 4.16 |
| FOE-02 | Fördermittel-Akte: Antrag, Bescheid, Auflagen, Fristen, zugeordnete Buchungen | 3 | R2 4.16 |
| FOE-03 | Verwendungsnachweis teilautomatisch zusammenstellen | 3 | R2 4.16 |

### 3.17 Mitgliedergewinnung, Kurse, Öffentlichkeit

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| OEF-01 | Automatische Willkommensstrecke für neue Mitglieder (Infos, Ansprechpartner, erste Mitmach-Aufgabe) | 2 | R2 4.20 |
| OEF-02 | **Einbettbare Bausteine** für die bestehende Vereinswebsite (Termine, Angebote, Beitrittsformular) statt eines eigenen Website-Baukastens | 2 | R2 4.21, R1 §6.3 |
| OEF-03 | Probetraining online buchbar | 3 | R2 4.20 |
| OEF-04 | Freiwillige, anonyme Austrittsbefragung | 3 | R2 4.20 |
| OEF-05 | Kurse für Nichtmitglieder mit Anmeldung, Warteliste und Zahlung | 3 | R2 4.22 |

### 3.18 KI-Unterstützung ★

In Vereinssoftware ist KI laut R1 kaum zu finden. Sie läuft immer als **Vorschlag, den ein Mensch
freigibt** (P8), und Mitgliederdaten gehen nicht ungeprüft an Dritte.

| ID | Anforderung | Stufe | Quelle |
| --- | --- | --- | --- |
| KI-01 | Textentwürfe: Einladungen, Nachrichten, Berichte, Newsletter | 2 | R2 §5.2, R1 §4.5 |
| KI-02 | Protokollentwurf aus Stichpunkten (verknüpft mit GRE-05) | 2 | R2 §5.2 |
| KI-03 | Belegerkennung und Vorschläge für die Buchung (verknüpft mit FIN-01) | 2 | R2 §5.2 |
| KI-04 | Fragen-Assistent zu Vereinsabläufen, **mit Quellenangabe** und klarer Kennzeichnung als Orientierung | 3 | R2 §5.2 |
| KI-05 | Suche im Vereinsgedächtnis in natürlicher Sprache | 3 | R2 §5.2 |

---

## 4. Nicht-funktionale Anforderungen

| ID | Anforderung | Quelle |
| --- | --- | --- |
| NF-01 | **Hosting in der EU** (besser in Deutschland); Auftragsverarbeitungsvertrag liegt fertig bereit | R1 §6.1, R2 4.9 |
| NF-02 | Funktioniert im Browser **und mobil**. Aufgaben in der Halle oder am Festplatz (Anwesenheit, Kasse, Helfer) laufen auf dem Smartphone. | R2 §5.4 |
| NF-03 | Mitglieder ohne App erreichbar: Zusagen und Zahlungen auch per E-Mail-Link, Inhalte als Druck oder Brief | R2 §5.4, R1 (Spond) |
| NF-04 | Einstieg in wenigen Minuten: Import, sinnvolle Voreinstellungen, kein Einrichtungsprojekt nötig | R1 §4.3 |
| NF-05 | Barrierearme Bedienung (gut lesbar, klare Sprache), weil viele Funktionsträger älter sind | R2 §5.4 |
| NF-06 | Revisionssichere Ablage für Finanzen und Beschlüsse | R2 4.3 |
| NF-07 | Gute Leistung auch zu Stoßzeiten, etwa beim Beitragslauf im Januar (bei WISO ein Kritikpunkt) | R1 §3 |
| NF-08 | Offene Schnittstellen (Export, API), damit Vereine nicht festsitzen. Laut einer Drittquelle hat easyVerein keine API. | R1 §3 |
| NF-09 | Ein einfaches, faires Preismodell, das auch für kleine Vereine nutzbar ist | R1 §4.3 |
| NF-10 | **Modularer Aufbau**: Module lassen sich auf Vereins- und Abteilungsebene ein- und ausschalten, ohne dass Daten unbemerkt verloren gehen. Module sprechen nur über den Kern miteinander. | [Baukasten-Konzept](2026-11-05-baukasten-konzept.md) §5, §6, §8 |

---

## 5. Vorschlag für Ausbaustufen

### Stufe 1: Kern („Ein Ort statt fünf Tools“)
Der feste Kern und die ersten Module. Die Module sind in Stufe 1 teilweise nur mit einem Teil ihrer
Funktionen enthalten.

**Fester Kern**
- Vereinsprofil (PFL-01)
- Personen, Gruppen und Import/Export (Teil von MIT-01, MIT-07)
- Rollen und Rechte mit Amtsübergabe (DSG-01, WIS-01)
- Benachrichtigungen über alle Kanäle, auch für Mitglieder ohne Internet (KOM-02)
- Aufgaben und Erinnerungen mit Übergabe (AUF-02)
- Dateiablage (WIS-03), Einwilligungen (DSG-02)

**Module**
- M1 Mitgliederverwaltung: Online-Beitritt, Selbstpflege, Listen (MIT-01 bis -03, -08)
- M2 Beiträge und SEPA: automatischer Beitragslauf (BEI-01 bis -03)
- M5 Kommunikation: automatische Zielgruppen, Umfragen (KOM-01, -04)
- M6 Termine: Zu-/Absage mit Nachhaken, Kalender-Abo (TER-01 bis -03)
- ★ M7 Aufgabenbörse (AUF-01)
- ★ M8 Helferschichten und Mitbringlisten (VER-01, -02)
- ★ M10 Pflichtenkalender (PFL-02 bis -04)

Damit ist schon in Stufe 1 das Startpaket „Organisation pur“ (Kern + M5, M6, M7, M8, M10) für
Vereine möglich, die bereits eine andere Verwaltung nutzen.

### Stufe 2: Ausbau („Geld, Gremien, Nachweise“)
Finanzen, Belege und Kassenprüfung, Spendenbescheinigungen, Mitgliederversammlung,
Pflichtstunden und Ehrenamtsstunden, Anwesenheit, Auslagen und Pauschalen,
Datenschutzdokumentation, Qualifikationen, Bestandserhebung, erste KI-Funktionen.

### Stufe 3: Später
Steuererklärung vorbereiten, Register-Entwürfe, Ressourcen und Inventar, Förderakte, Kurse,
Tickets, E-Rechnung, Fragen-Assistent.

**Begründung:** Stufe 1 deckt laut Priorisierungsmatrix in R2 §9 die Bereiche mit dem höchsten
Nutzen ab (Mitglieder, Beiträge, Kommunikation, Pflichtenkalender). Dazu kommen gleich die
Funktionen, mit denen sich vereina laut R1 vom Markt abhebt (Aufgaben, Helfer, Übergabe). Ohne
diese wäre vereina in Stufe 1 nur eine weitere Mitgliederverwaltung.

---

## 6. Was vereina bewusst nicht tut

| Bereich | Grund | Stattdessen | Quelle |
| --- | --- | --- | --- |
| Rechts- und Steuerberatung | Unzulässig, haftungsrelevant | Wissen mit Quellen, aufbereitete Unterlagen für Berater | R2 §7 |
| Notarielle Beglaubigung, Behördengenehmigungen | Gesetzlich anderen vorbehalten | Entwürfe, Checklisten, Fristen | R2 §7 |
| Website-Baukasten | Eigener Markt, viel Aufwand | Einbettbare Bausteine (OEF-02) | R1 §6.3 |
| Alarmierung / Einsatzplanung | Hochspezialisiert, sicherheitskritisch | Schnittstellen zu Divera & Co.; später ggf. Plugins von Dritten | R1 §6.3 |
| Fundraising-CRM | Eigener Markt | Einfache Spendenerfassung (SPE) | R1 §6.3 |
| Spielbetrieb, Ligen, Verbandssysteme (DFBnet, LIMS) | Gehören den Verbänden | Daten vorbereiten, Organisation rund ums Spiel; später ggf. Plugins von Dritten | R1 §6.3, R2 4.19 |
| Spezialfunktionen einzelner Vereinsarten (Flugbuch, Parzellen, Notenarchiv …) | Zu speziell für den Kernumfang | Später ggf. Plugins von Dritten ([Baukasten-Konzept](2026-11-05-baukasten-konzept.md) §9) | Baukasten-Konzept |
| Geheime elektronische Wahlen | Hohe Anforderungen an Rechtssicherheit | Zunächst nur offene Abstimmungen | R1 §6.3, R2 §7 |
| Entscheidungen und Verantwortung | Bleiben beim Vorstand | Vorbereiten, dokumentieren, nachhalten | R2 §7 |

---

## 7. Offene Entscheidungen

1. **Umfang des Finanzmoduls (M3):** Eigene vollständige Vereinsbuchhaltung, oder nur Belege,
   Kasse und Auswertungen mit Export zu Fachsoftware? Durch den Baukasten entschärft, weil Vereine
   das Modul weglassen können (siehe 3.3).
2. **Zielgruppe der ersten Version:** Welche Vereinsart und -größe kommt zuerst (kleiner
   Kulturverein, Sportverein mit Abteilungen, Förderverein, Kleingartenverein …)? Davon hängt
   z. B. ab, wie wichtig Pflichtstunden, Anwesenheit oder Spielbetrieb sind.
3. ~~**Rolle am Markt:** Komplettlösung oder Organisations-Tool?~~ **Entschieden:** beides, über
   den Baukasten. Vereine wählen Module und können Beiträge und Finanzen weglassen, wenn sie schon
   eine andere Verwaltung nutzen (siehe [Baukasten-Konzept](2026-11-05-baukasten-konzept.md)).
4. **Geschäftsmodell:** Gratis-Tarif, Preis pro Modul, nach Startpaketen, nach Mitgliedern oder
   pauschal, Transaktionsgebühren?
5. **Validierung:** Gespräche mit 5–10 Vereinen, bevor der Umfang von Stufe 1 festgelegt wird (R2 §10)
6. **Offene Fragen zum Baukasten** (Abteilungskassen, Dateiablage im Kern, Startpakete): siehe
   [Baukasten-Konzept](2026-11-05-baukasten-konzept.md) §10.
