### Concept

EvaP uses a modular system for assembling questionnaires for the evaluation of a course. With this approach, it is easy to add new course types and at the same time allows comparing courses of different types due to shared questionnaires. The user is free to choose any topic when composing a new questionnaire, it does not need to be tied to a specific course type.

An alternative would have been to determine the questionnaires for a course strictly by its course type. This proved to be too inflexible and difficult to maintain for mixed course types like a lecture with a project.

### Questionnaire types

There are two questionnaire types:
* Course questionnaires refer to a course in general, e.g. teaching materials and contents. 
* Contributor questionnaires refer to a contributor, e.g. a lecturer or teaching assistant.

Contributor questionnaires cannot be assigned to courses and vice versa.

Each questionnaire has a title and one or more questions.

Each course can have multiple course questionnaires assigned and to each contributor of a course, a different set of contributor questionnaires can be assigned (see [[Assignment | Questionnaires: Assignment]])


### Question types

There are three question types:
* Likert questions measure agreement/disagreement on a scale from 1 (complete agreement) to 5 (complete disagreement)
* Grade questions are similar to likert questions but use school grades from 1 (best) to 5 (worst) instead of agreement levels
* Comment questions can be answered in a text field. These comments are reviewed by staff users before publishing.

For likert and grade questions there is also the option to select a "no answer" field when evaluating. This might lead students to spend less thoughts on their answers, but was considered necessary nonetheless, because TODO.


### Questionnaire attributes

* Attributes that are shown to lecturers and staff users to help with [[questionnaire assignment | Questionnaires: Assignment]]:
  * Name: A short name describing the main use of the questionnaire, e.g. "Lecture - teaching materials"
  * Description: A tooltip that is shown during assignment to provide a more detailed description of the questionnaire's contents.
* Attributes that are visible to students:
  * Public name/title: The title will be the headline of the questionnaire as shown to students.
  * Introduction: A short text shown below the headline that explains/introduces the questionnaire.
* Internal attributes:
  * Sorting index: Higher numbers make the questionnaire appear farther down the page. Useful to e.g. move general comment questions to the bottom of the page.
  * Is for contributors: See "Questionnaire types" section above.
  * Obsolete: Hides the questionnaire in questionnaire selection widgets.


### Questionnaire management

 * Questionnaires can be deleted and edited only if they are not used for any course.
 * To change existing questionnaires for use in a new evaluation, staff users can copy the existing one and then modify the copy.
