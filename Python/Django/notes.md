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
