# What are Models?

In Django, a model is a Python class that represents a database table. 

In essence, a Django model defines the structure of your data, specifies how it should be stored in the database, and provides a convenient way to interact with the database using Python code.

It defines the fields (attributes) of the table and their types, acting as a blueprint for how data should be structured and stored in the database.

## Creating Models

```
from django.db import models

class Person(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
```

Each attribute in the class represents a field in the database table.

## Fields 

Fields define the types of data that can be stored in each column of the database table.

In the example above, the Person model has two fields: name (a character field) and age (an integer field).

## Database Table

Django automatically creates a database table based on your model when you run migrations. In this case, Django would create a table named "person" with columns for "name" and "age."

# Object Mapping (Creating Instance of the Model)

Django's ORM handles the translation between your Python objects (instances of your model) and the corresponding database records.

> <em>Models are like classes, instances of the model are like objects.</em>

```
# Creating a new person
new_person = Person(name='John Doe', age=25)
new_person.save()

# Querying persons
all_persons = Person.objects.all()
```
