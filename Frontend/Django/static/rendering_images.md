There are two ways to render an image on Django. 

## Using Static Files:

You can store your images in the static directory of your Django app and then reference them in your templates.

1. Create a static directory in your app (if it doesn't already exist).

2. Inside the static directory, create a folder to store your images, e.g., images.

3. Place your images in the images folder.

```
your_app/
|-- static/
|   |-- your_app/
|       |-- images/
|           |-- image.jpg
```

In your template, load the static files and use the {% static %} template tag to reference the image.

```
# template.html 

{% load static %}

<img src="{% static 'your_app/images/image.jpg' %}" alt="Image">
```