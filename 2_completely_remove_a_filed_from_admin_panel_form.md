# models.py
```python
from django.db import models


class Author(models.Model):
    name = models.CharField(max_length=100)
    title = models.CharField(max_length=3)
    birth_date = models.DateField(blank=True, null=True)
```

# admin.py
```python
from django.contrib import admin


class AuthorAdmin(admin.ModelAdmin):
    exclude=['title']

    @admin.display(empty_value="???")
    def view_birth_date(self, obj):
        return obj.birth_date
```