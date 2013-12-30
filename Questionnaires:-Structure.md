### Konzeptionelles Design

Wir haben in EvaP ein Baukastensystem umgesetzt, bei dem die Evaluation einer Lehrveranstaltung aus Fragebögen besteht. Dadurch lässt sich das System leicht auf neue Veranstaltungsarten erweitern und ermöglicht trotzdem eine Vergleichbarkeit der Lehrveranstaltungen durch gemeinsam benutzte Fragebögen. Die semantische Gestaltung der Fragebögen ist dabei völlig offen und nicht auf beispielsweise Vorlesung-, Übungs- und Seminarfragebögen beschränkt.

Alternativ hätten wir - wie im alten System EvaJ - einer Veranstaltung auch Typen zuordnen können, die die Fragebögen eindeutig bestimmen. Allerdings erwies sich das System als zu unflexibel, da es häufig Mischformen von Lehrveranstaltungen gibt (Vorlesung mit Projekt) und es umständlich und schlecht wartbar wäre, alle denkbaren Lehrveranstaltungstypkombinationen aufzulisten.

### Fragebögenvarianten

Es gibt zwei Fragebogentypen:
* Sachfragebögen beziehen sich allgemein auf eine Lehrveranstaltung, z.B. auf die Lehrmittel und den Inhalt. 
* Personenfragebögen beziehen sich auf einen Dozenten, z.B. Professor, Übungsleiter, Tutor. 

Jeder Fragebögen hat einen Titel je Sprache und eine oder mehr Fragen.

Jede Lehrveranstaltung kann mehrere Sachfragebögen haben und jedem Mitwirkenden können ein andere Auswahl an Personenfragebögen zugeteilt werden (siehe [[Zuordnung]]). Jeder Fragebogen kann (und sollte) von mehreren Lehrveranstaltungen genutzt werden.

### Fragetypen

Es gibt zwei Fragetypen:
* Likert-Fragen, die Zustimmung/Ablehnung auf einer Skala von 1 (volle Zustimmung) bis 5 (volle Ablehnung) ermitteln.
* Kommentar-Fragen, auf die man in einem Textfeld antworten kann. Diese Kommentare werden vom FSR zensiert.

Wir haben uns entschieden auch ein "keine Angabe"-Feld anzubieten. Das verleitet den Abstimmenden zwar möglicherweise dazu, sich nicht ausreichend Gedanken zu machen, ist aber notwendig. (TODO: Begründung)

### Attribute eines Fragebogens

Es gibt folgende Informationen in englischer und deutscher Sprache.

* Verwaltungsinformationen werden den Dozenten und dem FSR angezeigt, um die [[Zuordnung der Fragebögen]] zu ermöglichen.
  * Name: Ein zusammengesetzter Name, der angibt, wofür der Fragebogen hauptsächlich genutzt wird, z.B. Vorlesung2 - Lehrmittel.
  * Beschreibung: Tooltips, die während der Zuordnung angezeigt werden.
* Informationen für die Evaluierungsansicht
  * Öffentlicher Name/Titel: Titel für den Fragebogenblock, wie er den Studenten angezeigt wird
  * Einleitung: Erster erklärender Satz im Fragebogenblock
* Interne Attribute
  * Sortierindex: Gibt die Sortierreihenfolge vor. Damit können beispielsweise generelle Kommentarfragen an das untere Ende der Seite geschoben werden. Höhere Nummern werden weiter nach unten sortiert.
  * Personenfragebogen: Nur wenn der Haken gesetzt ist, lässt sich der Fragebogen einer Person in der [[Zuordnung]] zuordnen.
  * Obsolet: Verbirgt den Fragebogen in der Auswahlliste.


### Verwaltung von Fragebögen

* Fragebögen können nur gelöscht werden, wenn sie nicht verwendet werden
* Wurden Fragebögen in einer Evaluierung verwendet (d.h. es gibt abgegebene Stimmen), können sie nicht mehr geändert werden. (TODO: is this true?)
* Um verwendete Fragebögen zu ändern für eine neue Evaluierung kann man die alten einfach kopieren und anpassen.