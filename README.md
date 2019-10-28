# sockslevel

## What is this ?

Gestor de niveles de Pilates. Para usuarios VIP, con calcetines de niveles.


## Apps Django que componen el Proyecto SocksLevel

- socklogin (Login/Registro)

Extraído de [este artículo](https://medium.com/@himanshuxd/how-to-create-registration-login-webapp-with-django-2-0-fd33dc7a6c67).
Pasos :

1. Crear la app socklogin para login/registro de usuarios.

```
$ django-admin startproject socklogin
```

2. Crear dirs estáticos '/templates', '/media', '/static', 'media/profile_pics', 'templates/socklogin' dentro del proyecto *sockslevel*

3. Crear _migrations_ y ejecutar par aque los cambios se propaguen.

```
$ python manage.py migrate
$ python manage.py makemigrations socklogin
$ python manage.py migrate
```
4. Añadir las apps a _settings.py_

```
INSTALLED_APPS = [
    'socklogin',
```

5. Añadir directorios creados y TEMPLATE_DIR a DIRS[] em _settings.py_

```
TEMPLATE_DIR = os.path.join(BASE_DIR,'templates')
STATIC_DIR = os.path.join(BASE_DIR,'static')
MEDIA_DIR = os.path.join(BASE_DIR,'media')
```


6. Añadir estas líneas al final de _settings.py_

```
STATIC_URL = '/static/'
STATICFILES_DIRS = [STATIC_DIR,]
MEDIA_ROOT = MEDIA_DIR
MEDIA_URL = ‘/media/’
LOGIN_URL = ‘/socklogin/user_login/’
```
