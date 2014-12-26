### How are new users added?

There are three options:
* Import of enrollment data
* First login with Kerberos-credentials
* Manually via web-interface (sometimes necessary for external contributors)

There is no possibility for users to sign up on their own.

It is possible that a responsible wants to add a contributor which does not yet exist. In that case, they need to ask the EvaP staff to create accounts for these users.

### How can users be deleted?

Users cannot be deleted if they are contributor of a course or participant of a course that is or has been evaluation (in other words, if the user already had the chance to vote for that course), but has not been archived yet (not yet implemented, see [issue #371](https://github.com/fsr-itse/EvaP/issues/371)). This is necessary to keep results consistent. Right now, deleting contributors would also delete questionnaires and answers for that contributor, and deleting participants would alter the participant count of courses.


### User-Aging: When should users be deleted?

For students: In theory, as soon as they don't have a university account anymore. If that is technically not possible, one probably has to resort to deleting them after a certain number of semesters.

For contributors: Right now, it is not possible to delete contributors without altering results. As a workaround, one can give contributors a new username, e.g. by appending their ID to their previous username, as that username is not visible to users except in some staff pages. The importer will warn if a new contributor with the same username but different email address is about to be added (not yet implemented, see [issue #371](https://github.com/fsr-itse/EvaP/issues/371)).



### In case of user account duplicates

Use the merge_users command.


### How does the authentication work for internal users?

It uses Kerberos via the django-auth-kerberos backend for django. Kerberos settings are configurable in settings.py. If a user logs in into EvaP with Kerberos-credentials and has no account on EvaP yet, a new one is automatically created.


### How does the authentication work for external users?

External users need to enter their email address, whereafter EvaP sends them a randomly generated _login key_, if an account with that email address exists. This login key (which is unique, therefore it alone is enough to identify the user) can be used to log oneself in.

Login keys expire after a certain number of days (configurable in the settings).


### How are staff rights assigned?

Currently that is only possible via the django admin pages (/admin), to which every staff member has access.