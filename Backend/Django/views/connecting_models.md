# Import a Model for View 

```
from .models import Project
```

# Using A Model In View Logic

```
def projects(request):
    model_instances = Project.objects.all()
    context = {"instances": model_instances, "greet": "Hello Django"}
    return render(request, "projects/projects.html", context)
```
