To list the related objects of a ForeignKey field in a Django template, you can use template tags and filters to access the related objects and iterate through them. Here's how you can do it:

Assuming you have a model with a ForeignKey relationship, let's say a Book model with a ForeignKey to an Author model:

# Create the Models

```
# models.py

from django.db import models

class Patients(models.Model):
    # class information

class Diagnosis(models.Model):
    patient = models.ForeignKey(Patients, on_delete=models.CASCADE)
    # class information

```

# Create View

```
# To display children of patient instances

def patient(request, pk):
    patient = Patients.objects.get(id=pk)
    return render(
        request,
        "patients/patient.html",
        {"patient": patient},
    )
```

# Create Template:

```
    {% for diagnosis in patient.diagnosis_set.all %}
    {{ diagnosis.diagnosis }}
     {% endfor %}
```

<h1>{{ author.name }}'s Books</h1>
<ul>

    {% for book in author.book_set.all %}
        <li>{{ book.title }}</li>
    {% endfor %}

</ul>
In the above code:

author.name retrieves the author's name.
author.book_set.all retrieves all the books related to that author using the default reverse relation created by Django (in this case, book_set). You can customize the related name using the related_name attribute in the ForeignKey field definition if needed.
Now, when you visit a URL that corresponds to this view and provides an author's ID, it will display the author's name and list their books.

Remember to replace 'appname' with your actual app name and adjust the view function and template as needed based on your project structure and requirements.
