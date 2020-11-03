.. _installation:

Installation
############

Requirements
============

* Python: ``3.8``
* Django: ``2.2`` ``3.0`` ``3.1``

Quick Installation
==================

If you want to get started fast see our ``/example`` folder in your local installation. Or look at it `on github <https://github.com/sawadashota/django-oidc-provider/tree/main/example>`_.

Install the package using pip::

    $ pip install django-oidc-provider2

Add it to your apps in your project's django settings::

    INSTALLED_APPS = (
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'oidc_provider',
        # ...
    )

Include our urls to your project's ``urls.py``::

    urlpatterns = patterns('',
        # ...
        url(r'^openid/', include('oidc_provider.urls', namespace='oidc_provider')),
        # ...
    )

Run the migrations and generate a server RSA key::

    $ python manage.py migrate
    $ python manage.py creatersakey

Add this required variable to your project's django settings::

    LOGIN_URL = '/accounts/login/'
