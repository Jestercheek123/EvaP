## Ziele der Evaluierung

Bei der Neuentwicklung der Evaluierungsplattform hat sich der Fachschaftsrat folgende Ziele ergeben:

* Anonymität
* Vergleichbarkeit der Ergebnisse (zwischen Veranstaltungen eines Semesters, aber auch zwischen ähnlichen LV über mehrere Semester hinweg)
* Verbesserung der Lehre
* Bedienbarkeit
* Wartbarkeit
* Transparenz des Evaluierungsprozesses für alle Beteiligten
* Zuverlässigkeit (keine 500er mehr!) 
* Der Prozess erzeugt aussagekräftige Ergebnisse.

## Allgemeine Anforderungen

Im Vorfeld der Neuentwicklung haben wir uns folgende Anforderungen überlegt.

* Jeder Teilnehmer einer Lehrveranstaltung („Evaluierende“, nicht nur HPI-Studenten) hat die Möglichkeit, diese anonym zu evaluieren
* Evaluierende können nur LVs bewerten, die sie belegt haben (Authentifizierung: Nutzer können nicht für andere Nutzer abstimmen)
* Die Auswertung der Evaluierung lässt keine Rückschlüsse auf individuelle Stimmenabgaben zu
* Evaluierende haben pro LV nur eine „Stimme“, d.h. sie können den Fragebogen nur einmal ausfüllen
* LV-Evaluierungen mit zu geringer Beteiligung (derzeit weniger als 5 abgegebene Stimmzettel) werden nicht veröffentlicht => eigentlich auf Frage-Basis notwendig
* Der Evaluierungszeitraum liegt vor Erbringung der letzten Prüfungsleistung einer LV. Dadurch soll vermieden werden, dass sich Studenten für eine verhauene Klausur rächen. Evaluierungen sind nur in diesem Zeitraum durch die Studenten möglich.  
    
Aussagekräftige Ergebnisse erreichen wir vermutlich durch:
        
* Möglichst hohe Beteiligung => Verlosung, Erinnerungs-Emails zu Beginn des jeweiligen Evaluierungszeitraums
* Fragebögen passen zur LV und lassen sich über die Jahre optimieren und für die konkrete LV anpassen: 
  * Fragebögen sind so gestaltet, dass der Dozent hilfreiches Feedback aus den Antworten entnehmen kann 
  * und dass die Qualität verschiedener Lehrveranstaltungen miteinander verglichen werden kann. 
* Für eine hohe Beteiligung sollte es organisatorisch möglichst einfach sein, seine Stimme abzugeben und die Ergebnisse einzusehen. Kerberos-Anmeldung vermeidet Registrierungsprozess. Idealerweise sollten sich auch externe Studenten beteiligen können 
* Die **Administration des Prozesses** sollte möglichst reibungslos und vorhersehbar ablaufen
  * Automatische Auswertung der Ergebnisse, um Faktor Mensch auszuschließen
  * Belegungsdaten lassen sich vollständig und fehlerfrei ins Evaluierungssystem einpflegen
  * Nachvollziehbarkeit bei Fehlverhalten, frühzeitiges Aufdecken von Problemen

## Anforderungen an die Software

* **Sicherheit**, d.h. Anmeldedaten wie Passwörter dürfen nur verschlüsselt übertragen werden
* **Authorisierung**, d.h. Nutzer können nur Aktionen ausführen, für die sie die Rechte besitzen entsprechend ihrer Rollen (Student, Dozent, Fachschaftsrat)
* **Anonymität**, d.h. nach Abgabe des Bewertungsbogens ist es technisch nicht mehr möglich, von einer abgegebenen Bewertung auf deren Urheber zu schließen
* **Internationalisierung**, d.h. alle wichtigen Bereiche der Anwendung (Navigation und Fragebögen) sind mindestens in Englisch und Deutsch umgesetzt
* **Wartbarkeit**
  * Änderungen am System sind mit geringem Aufwand (Dokumentation, Continuous Integration) und ohne Risiko (Test-System!) möglich
  * Erwartete Änderungen sind:
    * neue Versionen der verwendeten Bibliotheken, Betriebssystem, Software
    * andere Fragebögen
    * Änderung des umgebenden Systems (z.B. Kerberos, Domäne, Belegungsverwaltung) 
* Der Import der Belegungsinformationen sollte weniger fehleranfällig sein.
* Das Evaluierungssystem integriert sich in die Systemlandschaft
  * Import der Belegungsdaten => Abspraceh mit der Universitätsverwaltung
  * Authentifizierung über Kerberos
* Wie wird externen Studenten ermöglicht, zu evaluieren?
* Allgemeine Benutzungsrichtlinien
  * in allen Feldern, in denen ein Login bzw. ein Name eingegeben werden soll, gibt es eine Auto-Vervollständigung

## Stakeholder und ihre Interessen

Für die Evaluierung gibt es folgende Stakeholder:

* Fachschaftsrat
* Universitätsverwaltung
* Studierende / Teilnehmer von Lehrveranstaltungen
* Dozenten
* Entwickler der Evaluierungsplattform

Ihre Mitwirkung wird im folgenden genauer beschrieben.

### Fachschaftsrat

Der Fachschaftsrat ist für die Durchführung und Administration der Evaluierung verantwortlich und ist sozusagen die Steuerzentrale des Prozesses.

Die Evaluierung ist eigentlich ein Routine-Prozess, erforderte bisher jedoch viel Kommunikation und manuelle Fehlerkorrektur. Jeder neue FSR muss sich wieder einarbeiten. Deshalb möchte der FSR mit der Evaluierung so wenig administrativen und Einarbeitungs- Aufwand wie möglich haben. Ein aufwändiges Beschaffen der Kurs-Informationen per E-Mail kosteten bisher sehr viel Zeit und der FSR würde sich natürlich lieber um die Interessen der Studierenden kümmern.

### Universitätsverwaltung

Die Universitätsverwaltung verwaltet die Belegungsdaten der Studierenden. Diese sind notwendig für die Durchführung der Evaluierung, damit jeder Student nur das evaluiert, was er auch belegt hat. Die Liste der Belegungen stellt die Universitätsverwaltung nach Ablauf der Belegungsfrist dem Fachschaftsrat auf Nachfrage zur Verfügung.

### Studierende / Teilnehmer von Lehrveranstaltungen

Die Studierenden werden jedes Semester aufgefordert, ihre belegten Lehrveranstaltungen zu evaluieren. Wenn die Ergebnisse öffentlich sind, haben viele eine Interesse an den Noten. Die Bewertung der Veranstaltungen vergangener Semester kann außerdem Entscheidungskritierum für die Belegung von Wahlveranstaltungen im neuen Semester sein.

### Dozenten

Dozenten führen Lehrveranstaltungen durch und interessieren sich im Laufe des Semesters und am Ende für Feedback. Damit die Fragebögen dem jeweiligen Typ der LV angemessen sind und alle beteiligten Personen berücksichtigen, sind die Dozenten aufgefordert, bei der Einstellung des Fragebogens mitzuwirken. Natürlich haben die Dozenten besseres zu tun, als diese Fragebögen zu erstellen, deshalb sollte der Aufwand so gering wie möglich sein. Es gibt auch Dozenten, für die die Evaluierung nur ein zusätzliches unnötiges Übel darstellt, da sie bisher keinen Nutzen aus den Ergebnissen ziehen konnten (z.B. Pflichtveranstaltung und jedes Jahr das gleiche Murren der Studenten).

Es gibt unterschiedliche Konstellationen von Dozenten. In der Regel ist eine Person (ein Professor oder Lehrbeauftragter) hauptverantwortlich für eine Lehrveranstaltung, d.h. er oder sie taucht in den Belegungsdaten als Dozent auf. Meist gibt es jedoch mehr Personen (z.B. Übungsleiter, Tutoren, weitere Professoren, wissenschaftliche Mitarbeiter), die an einer Lehrveranstaltung (in unterschiedlichem Maße) mitwirken und ebenfalls evaluiert werden können. 

Eine Besonderheit stellen auch **Softskills-Veranstaltungen und Vorlesungen von externen Dozenten** dar. Die Dozenten dieser Kurse werden meist von einem regulären Lehrbeauftragten beauftragt, der zwar nicht bei der LV mitwirkt und somit schlecht evaluiert werden kann, jedoch an den Ergebnissen interessiert ist. Externe Dozenten haben meist keine Kerberos-Zugangsdaten und benötigen daher eine andere Anmeldemöglichkeit, um z.B. den Evaluierungszeitraum einstellen und ihre Evaluierungsergebnisse einsehen zu können.


## Ablauf der Evaluierung - Grobüberblick

Im Folgenden wird der Ablauf der Evaluierung mit EvaP beschrieben.

* Zu Beginn des Semesters belegen die Studierenden ihre Lehrveranstaltungen. Die Belegungsfristen liegen meist Anfang November bzw. Anfang Mai. 
* Der FSR stellt ggf. neue Fragebögen ins EvaP-System ein.
* Sobald die Belegungen für die meisten Veranstaltungen vorliegen, erbittet der Fachschaftsrat beim Studiensekretariat die Belegungsliste in einem speziellen Format. Die Excel-Tabelle wird von den Admins um die Login-Namen angereichert.
* Der FSR überlegt sich den Standard-Evaluierungszeitraum, da dieser beim folgenden Import angegeben werden muss
* Vor dem Import in EvaP ist eine manuelle Kontrolle der Belegungsdaten empfehlenswert, da sich oft kleine Fehler einschleichen, die sich nach dem Import nur schwer korrigieren lassen. Beim Importieren der Belegungsdaten werden dann gleichzeitig neue Nutzer angelegt und die Belegungslisten erstellt.
* Der FSR weist die Fragebögen den entsprechenden LV-Typen zu, manuelle Korrekturen an einzelnen Veranstaltungen sind im Nachhinein möglich. Der FSR stellt sicher, dass jeder Veranstaltung ein Dozent zugewiesen ist, der auch auf die Veranstaltung zugreifen kann.
* Die Veranstaltungen werden freigegeben, sodass die eingestellten Dozenten und deren Stellvertreter die Lehrveranstaltungen bearbeiten können (Benachrichtigung per E-Mail). Dabei kontrollieren sie den Evaluierungszeitraum, fügen sie weitere Dozenten mit ihren Rollen (=Personenfragebögen) zu und können die vorausgewählten Fragebögen korrigieren. Wenn sie alle Änderungen bestätigt haben, überprüft der FSR diese nochmal. Anschließend gibt der FSR sie zur Evaluierung frei.
* Während des Evaluierungszeitraums können die Studierenden die Fragebögen ausfüllen. Dafür erhalten sie vom FSR oder dem EvaP-System Erinnerungen per E-Mail.
* Nach Ende des Evaluierungszeitraums zensiert der FSR die Kommentare.
* Sobald die Noten für die Lehrveranstaltungen vorliegen, können die einzelnen Evaluierungsergebnisse veröffentlicht werden.
* Wenn alle Ergebnisse vorliegen, wird eine tabellarische Übersicht der Ergebnisse exportiert und archiviert / ausgehangen.
* Abschließend kann der FSR 3 Gewinner ziehen, die einen kleinen Preis dafür erhalten, dass sie alle ihre Veranstaltungen evaluiert haben.

[[/Files/EvaP-Domain-Process.png]]

[[Evaluation Process as BPMN|/Files/Evaluierung_BPMN.pdf]]

Grundsätzlich stehen die Beteiligten einer Lehrveranstaltung meist erst nach Ende der Belegungsfrist fest und werden im Verwaltungssystem des Studienreferats nicht erfasst. Unter EvaJ wurden alle "Hauptdozenten" vom FSR persönlich angesprochen und gebeten, die weiteren Dozenten zu nennen. Im EvaP-System nehmen die Dozenten diesen Schritt selbst vor. Dadurch erhofft sich der FSR weniger Arbeit und vollständigere Daten. Dies stellt die Größte Änderung im Vergleich zu EvaJ dar. 

Problematisch ist derzeit noch die Zuordnung der Fragebögen. Diese hat im WS 2011/12 nicht reibungslos funktioniert und der FSR musste noch viel manuell nachkorrigieren. Mit einem CheatSheet und einer verständlicheren Fragebogen-Sammlung erhoffen wir uns weniger Notwendigkeit für Nachkorrekturen.