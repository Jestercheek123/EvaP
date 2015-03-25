## Import of enrollment data

1.  Get the enrollment data from the university office. The data is an .xls which must match the format in the [sample file](../blob/master/evap/static/sample.xls) exactly.
1. Check the format of the file manually. E.g. right column order, no blank fields, search for unusual usernames and email addresses etc. EvaP has only rudimentary checks for the syntactical correctness of the data and no checks for its semantical correctness.
1. Determine the default evaluation period.
1. Create a new semester.
1. Import the data. All courses are now in the state **new**.
1. You probably should spot-check the data after importing.
1. [[Assign questionnaires | Questionnaires: Assignment]]. These are the default questionnaires based on the course type and can be changed per course later on.

[[Files/states_of_a_course.png]]

## Evaluation

1. When all preparations are done, the FSR can "enable the course for lecturer review". This will send the "Lecturer Review Notice" email to the responsible person. If possible, do this with all courses at once, so the responsibles will get only one email. The new state is **pending for lecturer approval**.
1. The responsible person can now adjust the evaluation period and the selection of questionnaires, modify the participant list and add contributors. When he approves the course, it is in the state **approved by lecturer**.
1. The FSR can check if the responsible person did everything right and approve the course as well, the course is then **approved by FSR**.
1. (Automatically) When the evaluation period starts, the course will be switched to the state **in evaluation**. This is done by a [management command](../blob/master/evap/fsr/management/commands/run_tasks.py), which is executed by a [cron job](../blob/master/docs/installation.rst#productive-environment-cron-configuration).
1. (Automatically) A fixed time before the evaluation period ends, the system will send the "Student Reminder" email to all participants who did not evaluate one of their courses yet.
1. (Automatically) When the evaluation period ends, the course will be closed for evaluation and switched it to the state **comment review pending**.

##### Notes
* The FSR can approve each course in the states *new*, *pending for lecturer approval* and *approved by lecturer* and thus switch it to the state *approved by FSR*
* The FSR can edit any course at any time until it is *in evaluation*.

## After Evaluation

1. The FSR can now check all comments e.g. for insults. When the last comment is reviewed, the system will switch the course to the state **publication pending**.
1. When the grades of the course are released, the FSR can publish the course, it is then in the state **published**. This will send the "Publishing Notice" email to all contributors and participants. Again, this should be done in batches, to reduce the number of emails.
1. (Optional) The FSR can run the lottery to give prizes to some of the participants who evaluated all their courses.
1. (Optional) The FSR can export the results as a PDF to get a printable version.

