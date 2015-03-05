*see [[Calculation of Results]] to learn how the grades for courses are calculated*

### Publishing Results

When publishing the results (moving them from the state *evaluated* to *published* by a staff user) the course is added to the list of published courses for the corresponding semester. This list can be found in the main menu.


### What gets published

The results of a course consist of overall values like the number of participants and voters, the total average and median grades as well as answers to multiple questionnaires. There are questionnaires about the course and questionnaires about the course's contributors.
The questionnaires may contain Likert questions, grading questions and free text questions.

Some users can see more detailed information within the results. Please note that any assigned delegate can also see the results if the represented person can see them (with the exemption of private text answers).
These are the different types of answers and the respective publishing levels:

Results                                                         | standard user | contributor           | responsible contributor | *export*         | *full export*   | staff
----------------------------------------------------------------|---------------|-----------------------|-------------------------|------------------|-----------------|------
#participants, #voters                                          | yes           | yes                   | yes                     | yes              | yes             | yes
total grades                                                    | yes*          | yes*                  | yes*                    | yes*             | yes             | yes
answers to Likert and grading questions about the course        | yes*          | yes*                  | yes*                    | yes*             | yes             | yes
answers to Likert and grading questions about contributors      | yes*          | yes*                  | yes*                    | yes, aggregated* | yes, aggregated | yes
answers to free text questions (comments) about the course      | no            | no                    | yes                     | no               | no              | yes
answers to free text questions (comments) about contributors    | no            | yes, about themselves | yes**                     | no               | no              | yes

\*) These results are only accessible if **both** of the following are true:

* the number of voters for the course is higher than or equal to ```MIN_ANSWER_COUNT``` (standard value: 2)
* the number of voters devided by the number of the course's participants is higher than or equal to ```MIN_ANSWER_PERCENTAGE``` (standard value: 20%)

The variables can be defined in the settings.

\**) Comments can be marked as private during the review process. Such comments can only be seen by the person about whom the comment was written (and by staff users). The responsible person and delegates can not see them.


Users can only access the results page if they can see at least a part of the results. Otherwise the results are not linked at the semester's result overview page.
Staff users can see all results in all stages and even if they haven't been published.


### Warnings

Warnings above a course are shown to staff and contributors if they open the results of a course that wasn't published.
Additionally all users see warnings next to single grades within a course if there was only a small number of answers based on which the grade was calculated.

#### Calculation of the warning thresholds

For each questionnaire type of a course a median value of the maximum number of voters is calculated.
The result tells for each type of questionnaire (lecturer, tutor, ...) that was used in this course, what the median value of the individual questionnaires' maximum number of participants is.

Results which are based on less than ```RESULTS_WARNING_PERCENTAGE``` (configurable in the settings, standard value: 50%) of the median value of the maximum number of voters for this questionnaire get a warning message displayed next to them.
Questionnaires where all questions would have a warning message just show one message on top.

*Example*: There are 3 lecturer questionnaires consisting of 2 questions each and they got this distribution of answers (the maximum is highlighted):

 - Lecturer 1:
  - Question 1: 5 answers
  - Question 2: **7 answers**
 - Lecturer 2:
  - Question 1: **2 answers**
  - Question 2: 1 answer
 - Lecturer 3:
  - Question 1: **6 answers**
  - Question 2: 5 answers

The median value for the lecturer questionnaire is now the median of 7, 2 and 6, which is 6.
50% of 6 is 3, so every question that got less than 3 answers will have a warning.
Because lecturer 2 has a maximum number of voters of 2, all of the questions would have a warning, so they are combined and displayed as one warning on top of the questionnaire.


### Exports

EvaP allows to export the results of semesters as Excel sheets. The export contains the overall values for the course (number of participants and voters, the total average and median grades) and the average grades and variance for Likert and grading questions. The grades for contributors are aggregated for all contributors of the same type.
The standard export contains the grades only if the thresholds explained in *What gets published* have been reached, whereas the full export always contains them.