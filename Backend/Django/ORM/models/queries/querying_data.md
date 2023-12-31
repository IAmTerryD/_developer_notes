# Querying Data using Models

Querying data using models in Django involves interacting with the Django ORM (Object-Relational Mapping) system, which allows you to work with database tables as Python objects. Here's a simple guide on how to do this:

# Define Your Models:

First, you define your models in models.py in your Django app. A model is a Python class that inherits from django.db.models. Model. Each attribute of the model represents a database field.

```
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=100)
    published_date = models.DateField()
```

# Make and Run Migrations:

```
python manage.py makemigrations
python manage.py migrate
```

# Querying Data:

## Retrieve All Records: 

To get all instances of a model, use the all() method:

```
books = Book.objects.all()
```

## Filter Records: 

To get records that match certain criteria, use the filter() method:

```
books_by_author = Book.objects.filter(author='J.K. Rowling')
```

## Get a Single Record: 

To get a single record, use the get() method. 

Note that get() will raise an exception if the record doesn't exist or if multiple records are returned:

```
book = Book.objects.get(id=1)

```

## Complex Queries: 

You can chain methods to build more complex queries:

```
recent_books = Book.objects.filter(published_date__year__gte=2000).order_by('-published_date')
```

# Working with Query Results:

The results returned by queries like all() and filter() are querysets, which are iterable. You can loop through them in your views or templates:

```
for book in books:
    print(book.title)
```

# Creating and Saving Data:

To add new records to the database, you create an instance of your model and save it:

```
new_book = Book(title='New Book', author='Author Name', published_date='2021-01-01')

new_book.save()
```

# Updating Records:

To update a record, you fetch it, change its attributes, and save it:

```
book = Book.objects.get(id=1)
book.title = 'Updated Title'
book.save()
```

# Deleting Records:

To delete a record, you fetch it and call the delete() method:

```
book = Book.objects.get(id=1)
book.delete()
```
