Here are some tips, roughly ordered by usefulness:

* for developing, do **`vagrant ssh`** and then **`sudo python manage.py run`**
   * this stops apache (that runs on the VM by default) and start django's integrated server, which, unlike apache, automatically instantly reloads all code changes and prints uncaught exceptions directly on the console.
* run **`manage.py test`** before opening a pull request (but it also helps while developing!)
* run **`manage.py migrate`** whenever you pull changes with new migrations
* run **`manage.py makemigrations`** whenever you change any models 
* use [poedit ](http://poedit.net/) to edit the translation files
* run **`manage.py shell`** to interactively test python code 
* use **`manage.py dump_testdata`** for creating a new test_data.json
* when the vagrant VM does not boot, search for some commented-out lines in the vagrant file and uncomment them to start the VM with the virtualbox GUI
* when using apache:
   * **`service apache2 reload`** when code changes
   * **`manage.py collectstatic`** when static files change
   * easiest way to reroute console output to apache error logs: put **`sys.stdout = sys.stderr`** into manage.py 
