# To create an admin user

```
python manage.py createsuperuser
```

## Configure the Admin 

```
from django.contrib import admin
from .models import YourModel

admin.site.register(YourModel)
```