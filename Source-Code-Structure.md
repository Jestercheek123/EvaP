Source Code
===========

EvaP is a standard Django project, divided up into several apps:

`evaluation`
contains all the data models relevant for the evaluation, and some views like the login page and FAQ. It also contains some generic code used by other apps.

`staff`
provides views for the people overseeing the evaluation process

`contributor`
provides views for contributors

`results`
provides views to show results and produce exports

`student`
provides views relevant for students (mainly voting)

`rewards`
provides views relevant for the rewards functionality

`static`
contains third-party vendors like Bootstrap and Fontawesome and our custom styling

Data Import
-----------

The key module for data imports is `staff.importers`.
