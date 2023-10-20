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
from .models import Author

class AuthorAdmin(admin.ModelAdmin):
    list_display = ["name", "title", "view_birth_date"]
    
    fieldsets = [
        (
            None, {
                'fields':[
                    ('name', 'title',),  'birth_date',
                ],
            },
        ),
    ]

admin.site.register(Author, AuthorAdmin)   
```