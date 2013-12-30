### Berechnung der Gesamtnote und der Teilnoten

Eine Teilnote wird aus dem Durchschnitt aller für diese Frage abgegebenen Stimmen berechnet.
Die Gesamtnote besteht zu 50% aus dem Durchschnitt aller Teilnoten von Sachfragebögen und zu 50% aus aus dem Durchschnitt aller Gesamtnoten der einzelnen zu evaluierenden Personen.


### Online-Version: Sichtbarkeit der Kommentare

Kommentare auf Sach-Fragebögen können von allen Personen eingesehen werden, welche in der Liste der zu Bewertenden Lehrveranstaltungsbetreuer eingetragen sind. Auch deren Vertreter sind zur Einsicht berechtigt. (TODO Verify)

Kommentare zu Personenfragebögen können nur von den zu kommentierenden Personen sowie deren Vertretern eingesehen werden.

Mitglieder des Fachschaftsrates haben zu Zensurzwecken die Möglichkeit alle Kommentare einzusehen.

### Druck-Version

Zum Ausdruck bietet EvaP einen Excel-Export, welcher alle veröffentlichten Noten-Ergebnisse tabellarisch darstellt. 

Enthalten sind für alle Likert-Fragen die Durchschnittsnoten und die Standardabweichung. Nicht veröffentlicht sind hier die Kommentare. Im Studenten-Export finden sich nur Frageergebnisse mit ausreichender Repräsentativität (siehe unten) (TODO verify). Im GF-Export sind alle Ergebnisse vorhanden.
Die Ergebnisse von Personenfragen werden pro Frage zusammengefasst, d.h. alle Antworten zu Übungsleitern gehen in ein Ergebnis, die Antworten zu Dozenten jeweils ebenso. Siehe auch Abschnitt zu Gesamtnote. (TODO: Verify)

### Wer darf was sehen

Anmerkungen:
* Diese Tabelle bezieht sich auf eine Lehrveranstaltung. Verantwortliche und Mitwirkender dieser Lehveranstaltungen sind für andere Lehrveranstaltungen nur "allgemeiner Nutzer".
* Die "Verantwortlicher"-Spalte bezieht sich natürlich auch ausf dessen Stellvertreter.
* "ja, 20%" bedeutet "ja, falls mindestens 20% der Teilnehmer diese Frage beantwortet haben"

Form                  | allgemeiner Nutzer | Verantwortlicher | Mitwirkender | Export  | GF-Export | FSR
----------------------|--------------------|------------------|--------------|---------|-----------|----
#Belegungen, #Antworten, Gesamtnote | ja   | ja               | ja           | nur Gesamtnote und # abgegebener Fragebögen (TODO) | siehe "Export" | ja
Antworten auf Likertfragen     | ja, 20%   | ja               | ja           | ja, 20% | ja        | ja
Kommentare - Sachfragebögen    | nein      | ja               | ja           | nein    | nein      | ja
Kommentare - Personenfragebögen aller Mitwirkenden | nein | ja| nein         | nein    | nein      | ja
Kommentare - Personenfragebögen über sich selbst | - | ja     | ja           | -       | -         | -



### Der Repräsentativitätsschwellwert

tl;dr: Das Ergebnis einer Likert-Frage wird veröffentlicht, wenn mindestens 20% der Teilnehmer diese Frage beantwortet haben

Im alten System wurden Evaluierungsergebnisse einer Lehrveranstaltung nur dann für die Studenten veröffentlicht, wenn mindestens fünf Fragebögen abgesendet wurden. Ziel war, dass nur aussagekräftige /repräsentative Ergebnisse veröffentlicht werden, außerdem sollte so die Anonymität der abstimmenden besser gewährleistet werden. Leider ist es häufiger vorgekommen, dass auch unvollständig ausgefüllte Fragebogen abgesendet und gewertet wurden. So wurden beispielsweise bei einem Seminar 6 Fragebögen abgeschickt, aber nur 1 Stimme pro Frage erfasst. Im alten System gab es auch keine Möglichkeit, sich bei einer Frage explizit zu enthalten – sobald das Häkchen irgendwo gesetzt war, konnte man es nicht mehr rausnehmen.

In EvaP wird die Repräsentativität nicht mittels der abgesandten Fragebogen, sondern mittels der Stimmen pro Frage für jede einzelne Frage entschieden. Außerdem liegt die Grenze nicht mehr bei 5 Personen, sondern 20% der Teilnehmer. Das heißt, die Auswertung einer Likert-Frage wird dann vom System veröffentlicht, wenn mindestens 20% der Teilnehmer die Frage beantwortet haben („keine Angabe“-Stimmen zählen nicht). Das kann dazu führen, dass einige Fragen veröffentlicht werden, andere jedoch nicht. Nicht veröffentlichte Fragen erscheinen in der Web-Detailansicht mit dem Fragetext und dem Hinweis, dass das Ergebnis aufgrund der Beteiligung nicht veröffentlicht werden konnte.

Zusätzlich wird im Ergebnis angezeigt, wie viele Stimmen insgesamt für eine Frage abgegeben wurden, damit man ein grobes Gefühl für die Repräsentativität des Ergebnisses bekommt und ggf. offline statistische Auswertungen veranlassen kann. Dadurch ergibt sich auch die Anzahl der „Keine-Antwort“- Stimmen, denn für eine Veranstaltung wird angegeben, wie viele Stimmzettel insgesamt abgegeben wurden, sowie wie viele Studenten das Fach belegt haben. Wenn eine Frage von vielen Studenten mit „keine Angabe“ bewertet wurde, könnte das ein Hinweis darauf sein, dass sie zur Lehrveranstaltung nicht gut gepasst hat.

Haben insgesamt zu wenig Studenten abgestimmt, werden folglich nur die Fragen, aber keine Noten veröffentlicht.