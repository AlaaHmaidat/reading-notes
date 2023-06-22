# Django Custom User

## The key benefits of using a Django Custom User Model, and how does it differ from the default Django User Model
The key benefits of using a Django Custom User Model are flexibility, scalability, improved authentication, integration capabilities, and extensibility.

The default user model in Django uses a username to uniquely identify a user during authentication. If you'd rather use an email address, you'll need to create a custom user model by either subclassing `AbstractUser` or `AbstractBaseUser`.

Options:

1. AbstractUser: Use this option if you are happy with the existing fields on the user model and just want to remove the username field.
2. AbstractBaseUser: Use this option if you want to start from scratch by creating your own, completely new user model.


## The process of creating and implementing a Custom User Model in Django, including the necessary changes to settings.py and the required model fields

### **Setup**
To start, create a new Django project from the command line. We need to do several things:

create and navigate into a dedicated directory called for example `accounts` for our code
- install Django
- make a new Django project called `django_project`
- make a new app `accounts`
- start the local web server

Here are the commands to run:

```
# Windows
> cd onedrive\desktop\code
> mkdir pages
> cd pages
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
(.venv) > django-admin startproject django_project .
(.venv) > python manage.py startapp accounts
(.venv) > python manage.py runserver

# macOS
% cd ~/desktop/code
% mkdir pages
% cd pages
% python3 -m venv .venv
% source .venv/bin/activate
(.venv) % python3 -m pip install django~=4.0.0
(.venv) % django-admin startproject django_project .
(.venv) % python3 manage.py startapp accounts
(.vent) % python3 manage.py runserver
```
Note that we did not run `migrate` to configure our database. It's important to wait until after we've created our new custom user model before doing so.

If you navigate to http://127.0.0.1:8000 you’ll see the Django welcome screen.
![django](../img/django.png)

For now, stop the local server with `Control+c` because otherwise it will start kicking off lots of errors as we implement a custom user model.

### Custom User Model
Creating our initial custom user model requires four steps:

- update django_project/settings.py
- create a new CustomUser model
- create new UserCreation and UserChangeForm
- update the admin

In `settings.py` we'll add the accounts app and use the `AUTH_USER_MODEL` config to tell Django to use our new custom user model in place of the built-in `User` model. We'll call our custom user model `CustomUser`.

Within `INSTALLED_APPS` add `accounts` at the bottom. Then at the bottom of the entire file, add the `AUTH_USER_MODEL` config.

```python
# django_project/settings.py
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "accounts",  # new
]
...
AUTH_USER_MODEL = "accounts.CustomUser"  # new
```

Now update `accounts/models.py` with a new User model which we'll call `CustomUser`.

```python
# accounts/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```
We need new versions of two form methods that receive heavy use working with users. Stop the local server with `Control+c` and create a new file in the `accounts` app called `forms.py`.
```
(accounts) $ touch accounts/forms.py
```

We'll update it with the following code to largely subclass the existing forms.

```python
# accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm

from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

Finally we update `admin.py` since the Admin is highly coupled to the default User model.

```python
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ["email", "username",]

admin.site.register(CustomUser, CustomUserAdmin)
```

And we're done! We can now run `makemigrations` and `migrate` for the first time to create a new database that uses the custom user model.
```
(.venv) > python manage.py makemigrations accounts
(.venv) > python manage.py migrate
```
### *Resources:*

**Reading**

[Django Custum User Model](https://learndjango.com/tutorials/django-custom-user-model)

## What is DjangoX and how does it complement or extend the functionality of Django? Provide an example use case for incorporating DjangoX in a project


DjangoX is a powerful Django-based framework that extends the functionality of Django, offering additional features and utilities to enhance the development experience.

[DjangoX](https://github.com/wsvincent/djangox)

### Key Features

- **Enhanced Admin Interface**: DjangoX provides advanced features for the Django admin interface, including improved search functionality, customizable templates, and bulk actions.

- **Authentication Options**: With DjangoX, you can easily implement additional authentication methods like social authentication (OAuth) and two-factor authentication (2FA) to enhance the security of your Django projects.

- **Code Generation**: DjangoX offers code generation tools that enable you to scaffold common components of a Django project, such as models, views, forms, and templates. This accelerates development and improves productivity.

- **Database Management**: Simplify your database operations with DjangoX's tools, which include generating database diagrams, running migrations, and generating SQL scripts. These features make managing databases easier and provide better insights into the database structure.

- **Debugging and Profiling**: DjangoX includes debugging and profiling utilities to identify and resolve performance issues in your Django applications. It offers SQL query profiling, code profiling, and debugging panels for improved introspection during development and optimization.

### Example Use Case

Imagine you're building a sophisticated web application with Django that requires an advanced administration interface. You want to provide your admin users with powerful search capabilities, the ability to perform bulk actions on data, and the flexibility to customize the admin templates to match your branding.

By incorporating DjangoX into your project, you can extend the default Django admin interface with its enhanced features. Your admin users will benefit from advanced search functionalities, seamless execution of bulk actions, and the ability to customize the admin templates according to their needs.

Additionally, if your project demands additional security measures, such as social authentication or two-factor authentication, DjangoX offers the necessary tools to implement these features seamlessly.

DjangoX complements and extends the functionality of Django, providing a range of features that simplify common tasks and enhance the development experience. Incorporating DjangoX in your project empowers you to build robust and feature-rich Django applications more efficiently.


### *Resources:*

**Reading**

[Django Custum User Model](https://learndjango.com/tutorials/django-custom-user-model)

[DjangoX](https://github.com/wsvincent/djangox)

**Videos**

[Creating a Custom User Moel](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)

[Abstract User, User Profile and Signals in Django](https://www.youtube.com/watch?v=EudKs1HPUfE)

**Bookmark and Review**

[Substituting a custom User model](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#auth-custom-user)

## Things I want to know more about