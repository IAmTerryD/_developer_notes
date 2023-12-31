# QuerySets in Django ORM

QuerySets in Django's Object-Relational Mapping (ORM) system are central to interacting with the database. They represent a collection of SQL queries to retrieve objects from your database. 

Here are various types and methods of QuerySets you'll commonly use in Django:

## 1. Retrieving All Objects:

```
MyModel.objects.all()
```

## 2. Filtering:

```
MyModel.objects.filter(attribute=value)
```


## 3. Excluding:

```
MyModel.objects.exclude(attribute=value)
```

# 4. Chaining Filters:

```
MyModel.objects.filter(condition1).exclude(condition2)

```

# 5. Retrieving a Single Object

## get

```
MyModel.objects.get(id=1)
```

Retrieves a single object. Raises an exception if the object does not exist or if multiple objects are returned.

## first

```
MyModel.objects.filter(attribute=value).first()
```

Returns the first object matched by the filter, or None if no match is found.

# 6. Ordering

Returns a QuerySet ordered by the specified field. Add a minus sign (-) before field_name for descending order.

```
MyModel.objects.order_by('field_name')
```



# 7. Slicing
Limits the QuerySet to a specified number of results.
```
MyModel.objects.all()[:5]
```


# 8. Value and Values_List

```
MyModel.objects.values('field1', 'field2')
```
