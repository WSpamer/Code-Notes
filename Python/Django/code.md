# Django Code

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

## Model Save Override

```python
from django.db import models

class MyModel(models.Model):
    name = models.CharField(max_length=100)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    def save(self, *args, **kwargs):
        if not self.pk:  # Check if the object is being created (no primary key yet)
            print(f"Custom logic before creating: {self.name}")
        else:
            print(f"Custom logic before updating: {self.name}")

        super().save(*args, **kwargs)  # Call the original save method

        if not self.pk:
            print(f"Custom logic after creating: {self.name}")
        else:
            print(f"Custom logic after updating: {self.name}")
```
