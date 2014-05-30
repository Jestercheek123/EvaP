### People

- Responsible for the evaluation system are **the student representatives**/*der Fachschaftsrat*. A For convenience reasons the student representatives are also called (the) **FSR** for short (adopted from the representative's name at Hasso Plattner Insitute). A member of the FSR is called **student representative**/*FSR-Mitglied*. They work as administrators of the system and have full edit rights for users, courses and questionnaires.
- All people who are added to have teaching roles in a course (lecturers, tutors, etc.) are called **contributors**/*Mitwirkende*.
- At every time one of the contributors of a course is the **person responsible for the course**/*Lehrveranstaltungs-Verantwortlicher*. This role is assigned by the student representatives.
- Every contributor can get assigned **edit rights**/*Bearbeitungsrechte* for a course by any person who already has these edit rights for this very course and thereby becomes an **editor**/*Bearbeiter*. The responsible person always has edit rights.
- **Delegates**/*Stellvertreter* are people who are assigned to other people. A delegate has the combined edit rights for courses of all people he or she is **representing**.
- A **student**/*Student* is a person enrolled in a course.
- Students who are enrolled in a course are called **participants**/*Teilnehmer* of that course.
- Students who took part in the evaluation of a course are called **voters**/*Abstimmende*.
- Participants who did not yet take part in the evaluation of a course are called **due participants**/*ausstehende Teilnehmer*.
- Any person using the system at any time is called a **user**/*Benutzer*.
- Users without Kerberos credentials need a **login key**/*Anmeldeschlüssel* to log in.

### Courses
(Note: we didn't choose "class" because it's a keyword in python)

- Every single teaching instance is called a **course**/*Lehrveranstaltung*.
- A course is always part of a **semester**/*Semester* that describes when the course took place.
- Amongst others, courses consist of:
	- A **course name**/*Lehrveranstaltungsname*
	- A **course type**/*Lehrveranstaltungstyp* decribing the kind of course (e.g. lecture, seminar, project)
	- A **degree**/*Studiengang* (i.e. Bachelor or Master)
	- An **evaluation period**/*Evaluierungszeitraum* in which the course is available for evaluation
	- Questionnaires that are assigned to the course.
	- The current **state**/*Zustand* of the course (see [[Evaluation States]])

### Questionnaires

- Each **questionnaire**/*Fragebogen* has a **name**/*Name* by which it can be referenced.
- A questionnaire consists of one or multiple **questions**/*Fragen*.
- To submit a questionnaire during the evaluation process each question must have exactly one **answer**/*Antwort*.
- An answer can either be given on a **Likert scale**/*Likert-Skala* or in a **free text field**/*Freitext-Feld*.
- A possible answer is also rating **no answer**/*keine Angabe* respectively submitting an empty text field.
- Questionnaires have a **questionnaire type**/*Fragebogentyp* defining whether it's used to evaluate courses (**course questionnaire**/*Lehrveranstaltungs-Fragebogen*) or contributors (**contributor questionnaire**/*Personenfragebogen*).

### Data

- The information which courses are taught, what name, type, degree and responsible person they have and which students are enrolled in them is called **enrollment data**/*Belegungsdaten*.