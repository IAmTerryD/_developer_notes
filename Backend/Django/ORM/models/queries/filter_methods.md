# Filtering Table Queries

## Starts With
```
starts_with_filter = Project.objects.filter(title__startswith="E")
print(starts_with_filter)
```

## Greater than, Equal To

```
greater_than_equal_to = Project.objects.filter(vote_ratio__gte=50)
print(greater_than_equal_to)
```

# Set All 
```
project = Project.objects.get(title="Ecommerce Website)

print(project).review_set.all()

```