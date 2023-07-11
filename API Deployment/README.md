# API Deployment

In the "Django Settings Best Practices" reading, the key principles to follow when organizing and configuring Django settings for a project are as follows:

1. Keep settings in separate files: Split the settings into multiple files based on their functionality, such as base settings, development settings, production settings, etc. This helps maintain a clean and organized structure.

2. Use environment variables: Store sensitive or environment-specific settings, such as database credentials or API keys, in environment variables rather than hardcoding them in the settings files. This improves security and allows for easy configuration across different environments.

3. Separate secrets: Store sensitive information, such as passwords and secret keys, in a separate file or a key-value store. Avoid storing secrets directly in version control systems.

4. Import settings: Use import statements to include different settings files within the main settings file. This allows for modular and reusable settings configurations.

5. Utilize a settings module: Create a dedicated module to manage settings, separate from the project's main module. This helps encapsulate the settings-related logic and keeps the project structure clean.

Regarding White Noise, it is a library used for efficiently serving static files in a Django application. It is particularly useful when deploying Django projects to platforms like Heroku. White Noise works by serving static files directly from the web server's memory, avoiding the need to access the filesystem for every request.

To integrate White Noise into a Django project, you can follow these steps:

1. Install the White Noise library using pip:
    ```shell
    pip install whitenoise
    ```

2. In your Django project's settings module, add `'whitenoise.middleware.WhiteNoiseMiddleware'` to the `MIDDLEWARE` setting. Make sure it is placed before Django's `django.middleware.security.SecurityMiddleware` to ensure proper functioning.
    ```python
    MIDDLEWARE = [
        'whitenoise.middleware.WhiteNoiseMiddleware',
        ...
        'django.middleware.security.SecurityMiddleware',
        ...
    ]
    ```

3. Configure White Noise to serve static files by adding the following setting to your settings module:
    ```python
    STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
    ```

4. Collect static files using Django's `collectstatic` command:
    ```shell
    python manage.py collectstatic
    ```

White Noise will now handle the serving of static files efficiently in your Django application.

Cross-Origin Resource Sharing (CORS) is a mechanism that allows web browsers to request resources from a different domain than the one the web page originated from. It is a security feature implemented in web applications to control access to resources and protect against unauthorized cross-domain requests.

In a Django project, you can implement and configure CORS using the `django-cors-headers` package. Follow these steps to set it up:

1. Install the `django-cors-headers` package:
    ```shell
    pip install django-cors-headers
    ```

2. Add `'corsheaders'` to the `INSTALLED_APPS` setting in your Django project's settings module.
    ```python
    INSTALLED_APPS = [
        ...
        'corsheaders',
        ...
    ]
    ```

3. Include the `CorsMiddleware` in the `MIDDLEWARE` setting, preferably as one of the first middlewares.
    ```python
    MIDDLEWARE = [
        'corsheaders.middleware.CorsMiddleware',
        ...
    ]
    ```

4. Configure the CORS settings by adding the following configuration in your settings module:
    ```python
    CORS_ORIGIN_ALLOW_ALL = False

    CORS_ORIGIN_WHITELIST = [
        'http://example.com',
        'https://example.com',
    ]

    # Additional CORS settings if needed
    # ...
    ```

In the above example, `CORS_ORIGIN_ALLOW_ALL` is set to `False` to allow requests only from the domains listed in `CORS_ORIGIN_WHITELIST`. Adjust the whitelist according to your requirements.

By implementing CORS in your Django project, you can control and restrict access to resources from different origins, enhancing security and preventing unauthorized access.

### *Resources:*
**Reading**

[Django Settings Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)

**Bookmark and Review**

[White Noise](http://whitenoise.evans.io/en/stable/)

[CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)

## Things I want to know more about