Here are some tips, roughly ordered by usefulness:

* run **`manage.py run`** to start the django development server
* run **`manage.py test`** before opening a pull request (but it also helps while developing!)
* run **`manage.py migrate`** whenever you pull changes with new migrations
* run **`manage.py makemigrations`** whenever you change any models
* run **`manage.py reload_testdata`** to throw away the database and reload the test_data
* use [poedit ](http://poedit.net/) to edit the translation files
* run **`manage.py shell_plus`** to interactively test python code
   * in contrast to `shell`, this automatically imports e.g. all models.
* use **`manage.py dump_testdata`** for creating a new test_data.json
* when the vagrant VM does not boot, search for some commented-out lines in the vagrant file and uncomment them to start the VM with the virtualbox GUI
* there's also an apache server installed in the vagrant vm. it is running by default and accessible on the host at localhost:8001:
   * you have to run **`service apache2 reload`** when python code changes
   * you have to run **`manage.py collectstatic`** when static files change
   * easiest way to reroute console output to apache error logs: put **`sys.stdout = sys.stderr`** into manage.py
   * access logs via: **`sudo su -c "less /var/log/apache2/evap_error.log"`**
* styles are only recompiled when you change the main `evap.scss`.
   If you want to automatically recompile the styles even for other files,
   you can comment out the config line `COMPRESS_CACHEABLE_PRECOMPILERS` in `settings.py`.
