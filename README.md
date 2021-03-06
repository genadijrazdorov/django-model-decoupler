# Django model decoupler

django-model-decoupler enables simplification of development and separation of
business logic from presentation and data persistence in Django web framework.


## Install

With pipenv:

~~~
$ pipenv install django-model-decoupler

~~~

or with pip:

~~~
$ python -m pip install django-model-decoupler

~~~


## Quick start

1. Add "model_decoupler" to your INSTALLED_APPS setting like this::

    ~~~python
    INSTALLED_APPS = [
        ...
        'decoupler',
    ]
    ~~~

2. Change your models to inherit from `decoupler.Model`:

    ~~~python
    from django.db import models
    import decoupler.models as decoupler
    from pure_python_module import PurePythonClass

    class MyModel(decoupler.Model, adaptee=PurePythonClass):
	    attr1 = models.Field(...)
	    ...

    ~~~

3. Your changed MyModel should be able to act proxy to PurePythonClass from
    now.

