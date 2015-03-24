### Concept

EvaP uses a modular system for assembling questionnaires for the evaluation of a course. With this approach, it is easy to add new course types and at the same time allows comparing courses of different types due to shared questionnaires. The user is free to choose any topic when composing a new questionnaire, it does not need to be tied to a specific course type.

An alternative would have been to determine the questionnaires for a course strictly by its course type. This proved to be too inflexible and difficult to maintain for mixed course types like a lecture with a project.

### Questionnaire types

There are two questionnaire types:
* Course questionnaires refer to a course in general, e.g. teaching materials and contents. 
* Contributor questionnaires refer to a contributor, e.g. a lecturer or teaching assistant.
* Personenfragebögen beziehen sich auf einen Dozenten, z.B. Professor, Übungsleiter, Tutor. 

Each questionnaire has a title and one or more questions.

Each course can have multiple course questionnaires assigned and to each contributor of a course, a different set of contributor questionnaires can be assigned (see [[Assignment | Questionnaires: Assignment]])


### Question types

There are three question types:
* Likert questions measure agreement/disagreement on a scale from 1 (complete agreement) to 5 (complete disagreement)
* Grade questions are similar to likert questions but use school grades from 1 (best) to 5 (worst) instead of agreement levels
* Comment questions which can be answered in a text field. These comments are reviewed by staff users before publishing.

For likert and grade questions there is also the option to select a "no answer" field when evaluating. This might lead students to spend less thoughts on their answers, but was considered necessary nonetheless, because TODO.



Jeder Fragebögen hat einen Titel je Sprache und eine oder mehr Fragen.

Jede Lehrveranstaltung kann mehrere Sachfragebögen haben und jedem Mitwirkenden können ein andere Auswahl an Personenfragebögen zugeteilt werden (siehe [[Zuordnung | Questionnaires: Assignment]]). Jeder Fragebogen kann (und sollte) von mehreren Lehrveranstaltungen genutzt werden.


### Questionnaire attributes

* Attributes that are shown to lecturers and staff users to help with [[questionnaire assignment | Questionnaires: Assignment]].
  * Name: A short name describing the main use of the questionnaire, e.g. "Lecture - teaching material"
  * Description: A tooltip that is shown during assignment.
* Informationen für die Evaluierungsansicht
  * Öffentlicher Name/Titel: Titel für den Fragebogenblock, wie er den Studenten angezeigt wird
  * Einleitung: Erster erklärender Satz im Fragebogenblock
* Interne Attribute
  * Sortierindex: Gibt die Sortierreihenfolge vor. Damit können beispielsweise generelle Kommentarfragen an das untere Ende der Seite geschoben werden. Höhere Nummern werden weiter nach unten sortiert.
  * Personenfragebogen: Nur wenn der Haken gesetzt ist, lässt sich der Fragebogen einer Person in der [[Zuordnung | Questionnaires: Assignment]] zuordnen.
  * Obsolet: Verbirgt den Fragebogen in der Auswahlliste.


### Verwaltung von Fragebögen

* Fragebögen können nur gelöscht werden, wenn sie nicht verwendet werden
* Wurden Fragebögen in einer Evaluierung verwendet (d.h. es gibt abgegebene Stimmen), können sie nicht mehr geändert werden.
* Um verwendete Fragebögen zu ändern für eine neue Evaluierung kann man die alten einfach kopieren und anpassen.