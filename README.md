My Django Skeleton
==================

My own Django project skeleton. [From Randall Degges](https://github.com/rdegges/django-skel/)


Quickstart
==========

To create a new django-skel base project, run the following command (this assumes you have Django installed already):

    $ django-admin.py startproject --template=https://github.com/yannikmesserli/django-skel/zipball/master PROJECT_NAME
    $ cd PROJECT_NAME
    $ heroku config:add DJANGO_SETTINGS_MODULE=myproject.settings.prod


Where ``PROJECT_NAME`` is the name of the project you'd like to create. Then create a virtualenv to isolate your package dependencies locally:

	$ virtualenv ENV
	$ source ENV/bin/activate

I try to keep the same name for my virtualenv so that whenever I go in a project I know exactly how to active it. Then the next thing you probably want to do is remove Randall's project docs:

	$ rm -rf docs README.md

We can always come back to his documentation on [Read the doc](http://django-skel.readthedocs.org/). He usually propose to create apps in the ``apps`` folder, but small project you can prefer to create only one app like this:

	$ django-admin.py startapp apps PROJECT_NAME/apps


Then you can install the dev prerequies using:

	$ pip install -r reqs/dev.txt

And finally:

	$ python manage.py syncdb
	$ python manage.py migrate
	$ python manage.py runserver

Quick note for south
--------------------
The First Migration

	$ python manage.py schemamigration apps --initial
	$ python manage.py migrate apps

And the later

	$ manage.py migrate apps

[Full documentation](http://south.readthedocs.org/en/latest/index.html)

Notes
=====

- I have added the good ``iPython notebook`` to the dev requirement. I found it really useful to take note while developping or to keep pieces of code that I run often. However iPython requires Python 2.6, 2.7, or 3.2. To open the notebook, type:

	$ ipython notebook

- I'm not using newrelic, so I changed the ``Procfile`` in consequence.
- I have added ENV to the ``.gitignore``
- I'm using the [Django Rest Framework](http://www.django-rest-framework.org/tutorial/quickstart)
