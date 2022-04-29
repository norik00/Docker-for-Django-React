# README

## Django & postgres & React


### Prepare to create containers

#### Create django project
```console
$ docker-compose run --rm django django-admin startproject template .
```
`tamplate` is directory name of a Django project. The last `.` is that create this project under this directory.
`--rm` is to delete the command the container that was created for a Django project.


#### Connect the database

```python
# settings.py
   
import os
   
[...]
   
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ.get('POSTGRES_NAME'),
        'USER': os.environ.get('POSTGRES_USER'),
        'PASSWORD': os.environ.get('POSTGRES_PASSWORD'),
        'HOST': 'postgres', # service name
        'PORT': 5432,
    }
}
```


#### Create React app

```console
$ docker-compose run --rm react sh -c "npx create-react-app app --use-npm"
```
`app`is a React app name.The app name use in `docker-compose.yml`.
`--rm`is to delete the command the container that was created for a React app.

#### Create apps

```console
$ docker-compose up -d
```