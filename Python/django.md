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

## Many-to-Many

### Documentation

Assuming models with a custom through model:

```python
class Membership(models.Model):
    person = models.ForeignKey(Person, on_delete=models.CASCADE)
    group = models.ForeignKey(Group, on_delete=models.CASCADE)
    date_joined = models.DateField()

class Group(models.Model):
    name = models.CharField(max_length=50)
    members = models.ManyToManyField(Person, through='Membership', related_name='groups')

class Person(models.Model):
    name = models.CharField(max_length=50)
```

Get groups where a specific person (e.g., with name "John") is a member, filtering by the join date:

```python
groups = Group.objects.filter(
    membership__person__name="John",
    membership__date_joined__lte=date(2025, 5, 28)
)
```

### Example

Assuming models with a custom through model:

```python
class Zone(BaseModel):
    farm = models.ForeignKey(Farm, on_delete=models.CASCADE)
    name = models.CharField(max_length=100, default="")

class Device(BaseModel):
    name = models.CharField(max_length=100)
    zones = models.ManyToManyField(Zone, through="DeviceZone", blank=True)

class DeviceZone(BaseModel):
    class LocationTypeChoices(models.TextChoices):
        INSIDE = "Inside"
        OUTSIDE = "Outside"

    device = models.ForeignKey(
        Device, on_delete=models.CASCADE, related_name="device_zones"
    )
    zone = models.ForeignKey(
        Zone, on_delete=models.CASCADE, related_name="device_zones"
    )
    type = models.CharField(
        max_length=10,
        choices=LocationTypeChoices.choices,
        default=LocationTypeChoices.INSIDE,
    )
```

```python
devices = models.Device.objects.filter(
    status="Active",
    type="Weather",
    {through_model related_name}__type=models.DeviceZone.LocationTypeChoices.INSIDE,
)
```

## Django Admin

Play List: <https://www.youtube.com/watch?v=QCnefsgalF8&list=PLOLrQ9Pn6cazhaxNDhcOIPYXt2zZhAXKO&index=3>
Add CSV Import: <https://www.youtube.com/watch?v=BLxCnD5-Uvc&list=PLOLrQ9Pn6cazhaxNDhcOIPYXt2zZhAXKO&index=11>
Customize Admin: <https://testdriven.io/blog/customize-django-admin/>

## Docker

Link: <https://www.youtube.com/watch?v=eZouw1ohH0s&list=PLOLrQ9Pn6caxNFR2PWbHl3laaAI6J-GbN&index=6>
Video: <https://www.youtube.com/watch?v=37aNpE-9dD4&t=300s>
Setup: <https://saasitive.com/tutorial/django-celery-redis-postgres-docker-compose/>

## Tutorial

Admin Page: <https://docs.djangoproject.com/en/5.2/intro/tutorial07/>
ORM: <https://www.youtube.com/watch?v=46au1MxtOJE&list=PL-2EBeDYMIbQXKsyNweppuFptuogJe2L-&index=3>

## Extensions

[django-simple-history](https://django-simple-history.readthedocs.io/en/stable/)
<https://github.com/django-commons>
<https://github.com/django-import-export/django-import-export>

## ML

<https://www.deploymachinelearning.com/>
<https://dvc.org/doc/use-cases>

## Style Guide

<https://github.com/HackSoftware/Django-Styleguide?tab=readme-ov-file>
<https://www.hacksoft.io/category/django>

## Misc

[Split Settings](https://code.djangoproject.com/wiki/SplitSettings)

## Django in Jupyter

<https://dj-notebook.readthedocs.io/en/latest/>
<https://www.reddit.com/r/django/comments/1017n60/how_to_run_a_jupyter_notebook_inside_a_django/>
<https://dj-notebook.readthedocs.io/en/latest/>

## Deployment

<https://djangodeployment.readthedocs.io/en/latest/08-postgresql.html>

## Real World

<https://www.reddit.com/r/django/comments/1j6pc54/how_does_a_django_project_work_in_realworld/>

## Celery

<https://adamj.eu/tech/2020/02/03/common-celery-issues-on-django-projects/>

## Testing

pytest: <https://pytest-with-eric.com/pytest-advanced/pytest-django-restapi-testing/>
