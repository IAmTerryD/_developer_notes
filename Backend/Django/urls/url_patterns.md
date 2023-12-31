# What is a URL pattern?

A URL pattern in Django is like a set of instructions that tells your web application how to respond when a user visits a particular web address (URL).

It connects a specific URL to the code (views) that should handle them.


<p>
For example, if you have a web page for showing articles, you might create a URL pattern that says, "If someone goes to '/articles/', show them a list of articles. If they go to '/articles/1/', show them the first article." These patterns are defined in Django using the urlpatterns variable in the urls.py file.
</p>

# Examples of Django URL Patterns

```
from django.urls import path
from . import views

urlpatterns = [
    path("home/", views.home, name="home_url")
]
```

In this example if a user goes to the "/home/" url, Django should call the home function from the views module.