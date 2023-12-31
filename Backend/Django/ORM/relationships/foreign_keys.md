# What is a foreign key?

A foreign key in SQL is like a special link between two tables. It's a way to connect information in one table to information in another table. If you have information in one table that is related to information in another table, you can use a foreign key to create a connection between them.

So, when you use a foreign key, you're telling the database, "Hey, these two sets of information are related to each other!" It's a way to organize and make sense of data across multiple tables in a database.

# Foreign Key in Models

In Django, models. ForeignKey() is like a special marker you put in your model to show a relationship between two models. A foreign key is a child to that particular model.

```
# models.py 

from django.db import models

class Course(models.Model):
    name = models.CharField(max_length=100)

class Student(models.Model):
    name = models.CharField(max_length=50)
    enrolled_course = models.ForeignKey(Course, on_delete=models.CASCADE)

```

# on_delete = models.CASCADE

When you specify on_delete=models.CASCADE in a foreign key relationship, it means that if the parent record is deleted, all the child records associated with it will also be deleted.

This is a way to maintain data integrity. If you no longer have the parent record, it might not make sense to keep the child records that depend on it.

