We want to make sure that EvaP behaves the way we intended and *only* this way. Bad things must not happen. This is why we need an acceptable test coverage.

[At the moment](https://github.com/fsr-itse/EvaP/commit/5fb89162e5419cfde0378e3c8f180fca1687b672) we have a couple of test cases in ``evap.fsr`` for the administration of courses. However, there are still some main aspects which should be put under the umbrella of an automated test.

The following list is by no means complete but should serve as a starting point for testing ideas. Wherever possible, a wiki-page or issue should be referenced for further details. Additions welcome.

*Note: The [[Terminology]] is used here.*

### Evaluation process

* A *student representative* (in the following: *FSR member*) can create a new course, edit the details (name, description, evaluation date, etc.), assign a *person responsible* and add participants to it.
* An *FSR member* can import a list of courses.
* If an import fails, nothing is imported at all.
* A course can take the lifecycle/state machine described in [[Evaluation Process]] and *only* that lifecycle. For instance, a transition from ``new`` to ``approved by FSR`` is allowed, whereas a transition from ``new`` to ``published`` is not. If a transition requires certain constraints to be satisfied, make sure that the transition can only fire if and only if these requirements are met.
* The state of a course can only be altered by the authorized individuals or mechanisms. FSR members can do any allowed transition, except the start or end of the evaluation phase which is handled by a time-based trigger [TODO: reference!]. (Un)Authenticated users cannot alter the state of a course.

### Users and their Rights
EvaP has different [[Users and their Rights]]. Make sure that they can do/see all the things they are allowed to. Make sure that they cannot do anything that they should not be able to do (e.g. a non-FSR member creating new user accounts, a non-participant of a course voting for a course, a non-FSR member being able to access administration web pages and so on).

Special attention should be paid to situations where a user can have multiple roles (e.g. an individual being participant of one course and contributor of another) or is the delegate of one or more other individuals.

### Emails
At several occasions, emails are sent out to notify users of the system about important events:

* A person resonsible and its delegates must be notified when one or more of their courses become ``pending for lecturer approval``.
* A participant must be notified if he or she has not performed yet the evaluation for a course whose evaluation phase is about to expire.
* All contributors and participants of a course must be notified when the evaluation results are ``published``.

[TODO: Did I forget something?]

 We need to make sure that
* emails are sent at the right time to the right users
* bulk emails are sent out where appropriate
* email templates are used

### Other constraints
* A person responsible or contributor cannot be participant of its own course.