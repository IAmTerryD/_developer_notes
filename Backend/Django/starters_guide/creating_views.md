
# 1. Define a View Function:

Inside your app's directory, open the views.py file or create one if it doesn't exist. 

In this file, you can define your view functions. 

A view function is a Python function that takes an HTTP request as input and returns an HTTP response. Here's a simple example of a view function:

```
# app > views.py

from django.shortcuts import render, redirect
from django.http import HttpResponse
from .models import Patients

# Create your views here.
def patients(request):
    model_instances = Patients.objects.all()
    context = {"instances": model_instances, "greet": "Hello Django"}

    # structure "folder/patients.html"
    return render(request, "patients/patients.html", context)

```

# 2. Map URLs to Views:
To make your view accessible via a URL, you need to define URL patterns that map to your view function.

This is typically done in your app's urls.py file. If the urls.py file doesn't exist, create it in your app's directory. Here's how you can define a URL pattern for the my_view function:

```
# app > urls.py

from django.urls import path
from . import views

urlpatterns = [
    path("", views.patients, name="patients"),
]
```

# 3. Include App URLs in Project URLs:
To make your app's URLs available in the project, you need to include your app's URLs in the project's urls.py file. Here's how you can include them:

```
# project > urls.py

from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("admin/", admin.site.urls),
    path("patients/", include("patients.urls")),
]

```

## Run the Development Server:

python manage.py runserver
You can access your view in a web browser at http://localhost:8000/patients/, and it should display "Patients"

That's it! You've created a basic Django view and mapped it to a URL pattern. You can expand on this by adding more views and templates to create a fully functional web application.