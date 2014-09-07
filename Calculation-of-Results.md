### Calculation of the grades per question

For each Likert and grading question its grade is the average of all given answers. For Likert questions the answers are counted on a scale where "strongly agree" is 1 and "strongly disagree" is 5.


### Calculation of the total grades

The calculation of the total grade differentiates between Likert and grading questions and between questions about the course and about contributors.

The total grade for a course is now calculated as follows:

    total_likert = CP * likert_answers_about_contributors + (1-CP) * likert_answers_about_courses
    total_grade = CP * grade_answers_about_contributors + (1-CP) * grade_answers_about_courses
    total = GP * total_grade + (1-GP) * total_likert

```GRADE_PERCENTAGE``` (GP) is initially set as ```0.8``` and ```CONTRIBUTION_PERCENTAGE``` (CP) is set as ```0.5```.
That means the total value for the Likert answers is calculated by 50% of the answers about contributors and by 50% of the answers about the course.
The total value for grade answers is calculated in the same way.
The total grade of the course is then determined by 80% of the grade answers' total value and by 20% of the Likert answers' total value.