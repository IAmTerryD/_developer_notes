# What are Static Files?

Static files are non-changing files used in your web application, such as stylesheets, scripts, images, and icons. 

These files remain static, meaning their content doesn't change dynamically based on user interactions.

# Where to Place Static Files? 

In a Django project, you typically organize your static files within a folder named static at the top level of your app. Django will automatically look for this folder.

```
your_app/
├── static/
│   ├── your_app/
│   │   ├── css/
│   │   ├── js/
│   │   └── img/

```

# Rendering Static Components

To include static files in your HTML templates, you use the {% static %} template tag. 

This tag generates the correct URL to point to the static file.

```
<!-- For CSS File -->
<link rel="stylesheet" type="text/css" href="{% static 'your_app/css/style.css' %}">

<!-- For JavaScript File -->
<script src="{% static 'your_app/js/script.js' %}"></script>

<!-- For an Image -->
<img src="{% static 'your_app/img/logo.png' %}" alt="Logo">
```

## Configure Settings for Static Files

In your Django project settings, you need to make sure the STATICFILES_DIRS and STATIC_URL settings are correctly configured to point to your static files.

```
# settings.py

STATIC_URL = '/static/'
STATICFILES_DIRS = [BASE_DIR / "static"]
```

# Production Builds

When deploying a Django application in a production environment, you need to handle static files differently than during development. Here are the steps to manage static files in Django for a production build: 

## 1. Collect Static Files

Django provides a management command called collectstatic that gathers all static files from your various apps into a single directory. This directory can then be served by your web server.

Run the following command to collect static files:

```
python manage.py collectstatic 
```

## 2. Configure 'STATIC_ROOT' 

In your settings.py file, set the STATIC_ROOT variable to the directory where you want Django to collect static files. For example:

```
# settings.py

import os

BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))

STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')

```

## 3. Configure STATICFILES_DIRS:

```
# settings.py

STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'your_app/static'),
]
```

## 4. Serve Static Files 

### Whitenoise

```
pip install whitenoise
```

Whitenoise will not serve user uploaded images. 

> Remember when production build is on, the static files like CSS will be read from the 'staticfiles' folder.
