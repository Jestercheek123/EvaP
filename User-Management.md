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

Use the `Merge Users` functionality available from the user index page.


### Authentication for internal users

It uses Kerberos via the [django-auth-kerberos](https://github.com/02strich/django-auth-kerberos) backend for django. Kerberos settings are configurable in settings.py. If a user logs in into EvaP with Kerberos-credentials and has no account on EvaP yet, a new one is automatically created.


### Authentication for external users

External users get a login URL with each email they receive, which allows them to log in once. If they need to log in without having received an email, they can request a login URL by entering their email address on the front page.

If not used, the URL expires after a certain number of days (configurable in the settings).

This is handled in [evaluation/auth.py](https://github.com/fsr-itse/EvaP/blob/master/evap/evaluation/auth.py).


### Authentication with username and password without Kerberos

For development, where usually no Kerberos backend is available, the [test_data.json](https://github.com/fsr-itse/EvaP/blob/master/evap/evaluation/fixtures/test_data.json) fixture includes lots of users with the password `evap`. Currently there is no way to set a user's password via the UI. 

### How are manager, reviewer and grade publisher rights assigned?

That is possible via the user edit form to which every manager has access.