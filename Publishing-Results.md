*see [[Calculation of Results]] to learn how the grades for courses are calculated*

### Publishing Results

When publishing the results (moving them from the state *evaluated* to *published* by a staff user) the course is accessible from the results index page.


### What gets published

The results of a course consist of overall values like the number of participants and voters, the total average and median grades as well as answers to multiple questionnaires. There are general questionnaires about the course and questionnaires about the course's contributors.

Some users can see more detailed information within the results. Please note that any assigned delegate can also see the results if the represented person can see them (with the exemption of private text answers).
These are the different types of answers and the respective publishing levels:

Results                                        | standard user | contributor              | *export*          | staff
-----------------------------------------------|---------------|--------------------------|-------------------|------
#participants, #voters                         | yes           | yes                      | yes               | yes
average grade                                  | yes*          | yes*                     | yes*              | yes*
answers to rating questions about the course   | yes**         | yes**                    | yes**             | yes**
answers to rating questions about contributors | yes**         | yes**                    | yes, aggregated** | yes**
text answers about the course                  | no            | yes, if permission given | no                | yes
text answers about contributors                | no            | yes, about themselves*** | no                | yes

\* The average grade is only shown if the number of voters divided by the number of the course's participants is higher than or equal to ```VOTER_PERCENTAGE_NEEDED_FOR_PUBLISHING_AVERAGE_GRADE``` (standard value: 20%)

\**) These results are only visible if the number of voters for the course is higher than or equal to ```VOTER_COUNT_NEEDED_FOR_PUBLISHING_RATING_RESULTS``` (standard value: 2)

The variables can be defined in the settings.

\***) Text answers can be marked as private during the review process. Such answers can only be seen by the person about whom the comment was written (and by staff users). Delegates can not see them.


Users can only access the results page if they can see at least a part of the results. Otherwise the results are not linked at the semester's result overview page.
Staff users can see all results in all stages and even if they haven't been published.


### Warnings

Warnings above a course are shown to staff and contributors if they open the results of a course that wasn't published.
Additionally all users see warnings next to single grades within a course if there was only a small number of answers based on which the grade was calculated.

#### Calculation of the warning thresholds

For each questionnaire type of a course a median value of the maximum number of voters is calculated.
The result tells for each type of questionnaire (lecturer, tutor, ...) that was used in this course, what the median value of the individual questionnaires' maximum number of participants is.

Results which are based on less than ```RESULTS_WARNING_PERCENTAGE``` (configurable in the settings, standard value: 50%) of the median value of the maximum number of voters for this questionnaire get a warning message displayed next to them.
Additionally, all questions for which less than `RESULTS_WARNING_COUNT` (default: 4) answers have been given, show this warning.
Questionnaires where all questions would have a warning message just show one message on top.

*Example*: There are 3 lecturer questionnaires consisting of 2 questions each and they got this distribution of answers (the maximum is highlighted):

 - Lecturer 1:
  - Question 1: 5 answers
  - Question 2: **9 answers**
 - Lecturer 2:
  - Question 1: **3 answers**
  - Question 2: 1 answer
 - Lecturer 3:
  - Question 1: **6 answers**
  - Question 2: 5 answers

The median value for the lecturer questionnaire is now the median of 9, 3 and 6, which is 6.
50% of 6 is 3, so every question that got less than 3 answers will have a warning. Because of the additional fixed minimum count of 4, every question that got less than 4 answers will have a warning.
Because lecturer 2 has a maximum number of voters of 3, all of the questions would have a warning, so they are combined and displayed as one warning on top of the questionnaire.


### Exports

EvaP allows to export the results of semesters as Excel sheets. The export contains the overall values for the course (number of participants and voters, the total average) and the average grades for rating questions. The grades for contributors are aggregated for all contributors of the same type.