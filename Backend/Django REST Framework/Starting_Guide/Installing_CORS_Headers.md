# Enable CORS Headers

# Install from PIP
```
python -m pip install django-cors-headers
```

# Add to INSTALLED_APPS 

```
"corsheaders",
```

# Add to MIDDLEWARE

```
  "corsheaders.middleware.CorsMiddleware",
```

# Add Allowed URLs to access API Endpoints 

CORS_ALLOWED_ORIGINS = [
    "http://localhost:3000",
]

This allows frontend frameworks to connect to Django API
```

# Ensure Django Rest Framework backend:

```
INSTALLED_APPS = [
    "rest_framework",
    "api",
    "corsheaders",
]
```