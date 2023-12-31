# When to Use Media Files 

If you want to handle user-uploaded images, use the Media directory.

# Configuring Media File Settings

## Settings.py

In your settings.py, define the MEDIA_ROOT and MEDIA_URL. 

```
# settings.py

MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
MEDIA_URL = '/media/'
```

## URLS. PY

In your urls.py, include the media route during development.

```
# urls.py

from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    # ... your other patterns
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

## Media 

In your model, use the ImageField to store the image.

```
# models.py

from django.db import models

class YourModel(models.Model):
    image = models.ImageField(upload_to='images/')
```

## Template

In your template, use the url attribute of the image field.

```
<img src="{{ your_model_instance.image.url }}" alt="Image">
```
