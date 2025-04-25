# Django Notes

## Dumpscript

Link: <https://django-extensions.readthedocs.io/en/latest/dumpscript.html>

To dump the data from all the models in a given Django app (appname):

```bash
./manage.py dumpscript appname > scripts/testdata.py
```

To dump the data from just a single model (appname.ModelName):

```bash
./manage.py dumpscript appname.ModelName > scripts/testdata.py
```

To reset a given app, and reload with the saved data:

```bash
./manage.py reset appname
./manage.py runscript testdata
```

## Django Manager

py manage.py makemigrations
py manage.py migrate
py manage.py runserver

py manage.py createsuperuser
py manage.py startapp

## Django Admin

Play List: <https://www.youtube.com/watch?v=QCnefsgalF8&list=PLOLrQ9Pn6cazhaxNDhcOIPYXt2zZhAXKO&index=3>
Add CSV Import: <https://www.youtube.com/watch?v=BLxCnD5-Uvc&list=PLOLrQ9Pn6cazhaxNDhcOIPYXt2zZhAXKO&index=11>

## Docker

Link: <https://www.youtube.com/watch?v=eZouw1ohH0s&list=PLOLrQ9Pn6caxNFR2PWbHl3laaAI6J-GbN&index=6>

## Tutorial

Admin Page: <https://docs.djangoproject.com/en/5.2/intro/tutorial07/>
ORM: <https://www.youtube.com/watch?v=46au1MxtOJE&list=PL-2EBeDYMIbQXKsyNweppuFptuogJe2L-&index=3>

## Extensions

<https://github.com/django-commons>
<https://github.com/django-import-export/django-import-export>

## ML

<https://www.deploymachinelearning.com/>
<https://dvc.org/doc/use-cases>

## Style Guide

<https://github.com/HackSoftware/Django-Styleguide?tab=readme-ov-file>
<https://www.hacksoft.io/category/django>

## Misc

## Django in Jupyter

<https://dj-notebook.readthedocs.io/en/latest/>
<https://www.reddit.com/r/django/comments/1017n60/how_to_run_a_jupyter_notebook_inside_a_django/>
<https://dj-notebook.readthedocs.io/en/latest/>

## Deployment

<https://djangodeployment.readthedocs.io/en/latest/08-postgresql.html>
