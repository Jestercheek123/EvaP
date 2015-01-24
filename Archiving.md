### General
On the results pages, voters and participant counts of each course are displayed. These counts are computed on the fly and as such dependent on user accounts, if a voter/participant gets deleted, these counts would also change. To prevent this, it is usually not possible to delete participants of courses through the UI. 

However, an archiving functionality is implemented that decouples these counts from user accounts. This functionality is available in the staff's semester view site. When all courses of a participant have been archived, deleting the participant is possible again.

It is not possible to archive individual courses, only whole semesters. Semesters can only be archived if all of their courses are in the states "new" or "published".

### How can users be deleted?

For the reasons explained above, participants cannot be deleted if they participate in a course that is or has been in evaluation (in other words, if the user already had the chance to vote for that course), but has not been archived yet.

Contributors cannot be deleted. Deleting them would also delete all results associated to them. There is currently no way to decouple contributor accounts from their results, and it is not planned to implement that. See below for a workaround.


### User-Aging: When should users be deleted?

For participants: In theory, as soon as they don't have a university account anymore. If that is technically not possible, one probably has to resort to deleting them after a certain number of semesters.

For contributors: As explained, it is not possible to delete contributors without altering results. When a staff member is required to import a new contributor that has the same name as an existing one, one can give the existing contributor a new username, e.g. by appending their ID to their previous username, as that username is not visible to users except in some staff pages. The importer will warn if a new contributor with the same username but different email address is about to be added.