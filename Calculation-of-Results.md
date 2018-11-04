### Calculation of the grades per question

For each non-text question its grade is the average of all given answers.


### Calculation of the total grades

The calculation of the total grade differentiates between grade/non-grade questions and between general questions/questions about contributors. All mentioned constants can be changed in the settings file.

For each contributor an average grade is calculated weighted by grade questions (`CONTRIBUTOR_GRADE_QUESTIONS_WEIGHT`, default: 4) and non-grade questions (`CONTRIBUTOR_NON_GRADE_RATING_QUESTIONS_WEIGHT`, default: 6).

All contributor grades are then averaged weighted by the maximum number of votes any question of each contributor received.

For the general questions two average grades for all grade questions and for all non-grade questions are calculated.

These two and the overall contributor average grade are then averaged by using the weights `GENERAL_GRADE_QUESTIONS_WEIGHT`, `GENERAL_NON_GRADE_QUESTIONS_WEIGHT`, `CONTRIBUTIONS_WEIGHT` (default for all of them is 1) to a total grade.