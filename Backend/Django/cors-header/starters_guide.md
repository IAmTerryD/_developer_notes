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