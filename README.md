# React-Django-Vite
An integrated React and Django application base template.

### To change Django app name:
*In MANAGE.PY, WSGI.PY, and ASGI.PY:*
```python
os.environ.setdefault('DJANGO_SETTINGS_MODULE', '<django_app_name>.settings')
```

*In SETTINGS.PY*
```python
ROOT_URLCONF = '<django_app_name>.urls'

WSGI_APPLICATION = '<django_app_name>.wsgi.application'
```


### To change React app name:
*In SETTINGS.PY:*
```python
TEMPLATES = [
  {
    # add the new path to this line
    'DIRS': [os.path.join(BASE_DIR, '<reactAppName>/dist/')],
  },
]

STATICFILES_DIRS = [
  # and this line
  os.path.join(BASE_DIR, '<reactAppName>/dist/assets')
]
```


### Get it running:
*React:*
```bash
# in react's app directory
npm i
# this will create the "dist" directory, and the "assets" static files directory
npm run build
```

*Django:*
```bash
python manage.py runserver
# or
django-admin runserver
```