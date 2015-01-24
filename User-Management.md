### How are new users added?

There are three options:
* Import of enrollment data
* First login with Kerberos-credentials
* Manually via web-interface (sometimes necessary for external contributors)

There is no possibility for users to sign up on their own.

It is possible that a responsible wants to add a contributor which does not yet exist. In that case, they need to ask the EvaP staff to create accounts for these users.

### User deletion and aging

See [[Archiving]].


### In case of user account duplicates

Use the merge_users command.


### How does the authentication work for internal users?

It uses Kerberos via the django-auth-kerberos backend for django. Kerberos settings are configurable in settings.py. If a user logs in into EvaP with Kerberos-credentials and has no account on EvaP yet, a new one is automatically created.


### How does the authentication work for external users?

External users need to enter their email address, whereafter EvaP sends them a randomly generated _login key_, if an account with that email address exists. This login key (which is unique, therefore it alone is enough to identify the user) can be used to log oneself in.

Login keys expire after a certain number of days (configurable in the settings).


### How are staff rights assigned?

Currently that is only possible via the django admin pages (/admin), to which every staff member has access.