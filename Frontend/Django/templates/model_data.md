# Rendering Data from Model to Template

Displaying model data on a template in Django involves a few simple steps. Let's break it down:

## 1. Modify Views

In your Django view, retrieve the data from the model and pass it to the template. 

```
from django.shortcuts import render
from .models import YourModel

def your_view(request):
    data = YourModel.objects.all()
    return render(request, 'your_template.html', {'data': data})
```

You can use the objects.all() method to get all instances of a model.

# 2. Templates 

Create a template (HTML file) where you want to display the model data. Use Django template syntax to loop through the data and display it.

```
<!-- template.html -->

<h1>Your Model Data</h1>

<ul>
    {% for item in data %}
        <li>{{ item.field1 }} - {{ item.field2 }}</li>
    {% endfor %}
</ul>
```

Since there are more than likely multiple objects of a model class, you will have to loop through each object to pull data from each. 

### Complete

That's it! When you visit the URL associated with your view, it will render the template, and you'll see your model data displayed. Adjust the field names and HTML structure based on your model and design preferences.
