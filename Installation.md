Installation
============

Vagrant
------------

Usually it's easiest to just use the Vagrant VM. Since we use puppet in git submodules for easier configuration of the VM, you'll need to clone with ``--recurse-submodules`` or run ``git submodule update --init`` after checking out EvaP, and of course you need to have [Vagrant](http://www.vagrantup.com) installed. Then you can run ``vagrant up`` in your EvaP root directory; this builds you a fully working EvaP installation with PostgreSQL as database and Apache as webserver.

You can use EvaP at ``http://localhost:8000/`` on your host, write code in your git repo, and access the VM with ``vagrant ssh``. Your git checkout is mounted in ``/vagrant`` there.

Use ``vagrant halt`` to shutdown the VM, and ``vagrant destroy`` to delete it.

If you don't want to use Vagrant, you can use the following instructions to manually set up EvaP.


Vagrant and Hyper-V
-------------------

To use the Vagrant VM with Hyper-V as provider, do the following:

1. Enable Hyper-V (note the warning on [this page](https://docs.vagrantup.com/v2/hyperv/index.html)).

2. Configure Networking

  You can either connect the VM to your external network directly by creating an *External Virtual Switch* in Hyper-V Manager->Virtual Switch Manager, or use "NAT-Mode" by creating an *Internal Virtual Switch* and setting up [Windows Internet Connection Sharing](http://windows.microsoft.com/en-us/windows/using-internet-connection-sharing#1TC=windows-7) (recommended).

3. ``vagrant up --provider hyperv``

  Select the virtual switch created in step 2 and enter your Windows host credentials when prompted, in order to give the virtual machine access to the working directory via SMB.

4.  Because port forwarding doesn't work with Hyper-V, you have to access the EvaP website using the VM's IP address.


Filesystem Structure
--------------------

We recommend that you install the application into the directory ``/opt/evap`` according to the filesystem hierarchy standard. In the remaining steps, we will assume that this is your installation directory.

Clone the repository or copy the files into that directory. The installation should be correct if the settings file has the path ``/opt/evap/evap/settings.py``. Make sure that all files and directories are readable by the Apache web server. Additionally please make sure that the directory ``/opt/evap/evap/upload`` is writable by the web server.


Dependencies
------------

EvaP is written in Python using the Django framework and you need at least Python 3.4 to run it. Apart from Python and Django there are some other dependencies that are listed in the file ``requirements.txt``. Use [pip](http://www.pip-installer.org/en/latest/installing.html) to install these with the following command: ``pip install -r requirements.txt``.

*For Windows users:* As ``lxml`` has native code and compiling it with your installed compiler usually fails, you need to install a precompiled package from [lfd.uci.edu](http://www.lfd.uci.edu/~gohlke/pythonlibs/).

*For Windows users:* For the compilation of translation files gettext is used. This can be downloaded as a precompiled package from [the GnuWin project](http://sourceforge.net/projects/gnuwin32/files/gettext/).


Database Initialization
-----------------------

To initialize the database during the installation you have to perform the following command in ``/opt/evap`` directory:

- ``python manage.py migrate``


File Refresh
------------

You have to run some additional commands during the installation and whenever you update EvaP. Perform these steps in the ``/opt/evap`` directory after you have upgraded the files:

- ``python manage.py migrate`` to perform any potential database updates.
- ``python manage.py collectstatic`` to collect all files that the front-end webserver should serve.
- ``python manage.py compilemessages`` to update the binary translation catalog.
- ``python manage.py createcachetable`` to, well, create the table used for caching.

Finally, restart the Apache web server.


Load test data
--------------
 
The Vagrant VM automatically loads test data from a fixture on it's creation. If you want to load this data in your manual installation, run the following commands (*Note: This will remove all data previously stored in the database*):

        python manage.py flush --no-initial-data
        python manage.py loaddata test_data.json


Development Environment: Setup and Server Running
-------------------------------------------------

The manual creation of a superuser is just recommended for development environments. In productive environments a Kerberos authentification system or similar should be used.

To create a superuser perform in the ``/opt/evap`` directory the command ``python manage.py createsuperuser``.

A login in a development environment can be simulated by setting the variable ``REMOTE_USER`` to your previously created user.

The server for this environment can be started from within the ``/opt/evap`` directory with ``python manage.py runserver``.


Productive Environment: Settings
--------

The configuration of the application is done by creating a ``localsettings.py`` in the ``evap`` folder and overwriting the defaults from ``settings.py`` there. The defaults should be OK for most development purposes. For a production environment you should change the following settings:

- Choose an appropriate database and modify the ``default`` entry in the ``DATABASES`` settings. Please make sure that you use a database that supports transactions.
- Change the ``DEFAULT_FROM_EMAIL`` to an administrative mail address that is used as the sender of the mails generated by the system.
- Change ``MEDIA_ROOT`` to a directory that is writable by the web application. This directory will hold user-uploaded files.
- You should change the ``SECRET_KEY``.
- Finally, set ``DEBUG`` to ``False``.


Productive Environment: Apache 2 Configuration
----------------------------------------------

We recommend the following Apache configuration:

    WSGIScriptAlias / /opt/evap/evap/wsgi.py

    Alias /static /opt/evap/evap/static_collected
    <Location /static>
        ExpiresActive On
        ExpiresDefault "access plus 1 month"
    </Location>

    Alias /media /opt/evap/evap/upload


Productive Environment: Kerberos Authentication
-----------------------------------------------

To use Kerberos as an authentication backend, do the following:

- run ``pip install django_auth_kerberos``

- copy the following to your ``localsettings.py`` and edit ``KRB5_REALM`` and ``KRB5_SERVICE`` according to your setup:

```
KRB5_REALM = 'EXAMPLE.COM'
KRB5_SERVICE = 'krbtgt@AS.EXAMPLE.COM'
INSTALLED_APPS += ('django_auth_kerberos',)
MIDDLEWARE_CLASSES += ('django_auth_kerberos.backends.KrbBackend',)
```

Productive Environment: Cron Configuration
------------------------------------------

EvaP has components which need to react to timed events. This behavior is implemented by running two cronjobs, which in turn trigger a management command. One should be run hourly and the other one daily.

For example you could use a /etc/cron.daily/evap like

    #!/bin/sh

    pushd  /opt/evap
    sudo -H -u evap /usr/bin/python manage.py send_reminders
    popd

And a /etc/cron.hourly/evap like

    #!/bin/sh

    pushd  /opt/evap
    sudo -H -u evap /usr/bin/python manage.py update_course_states
    popd
