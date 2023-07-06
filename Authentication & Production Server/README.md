# Authentication & Production Server

## What is the primary purpose of JSON Web Tokens (JWTs) and how do they work in terms of encoding and decoding data?
JSON Web Tokens (JWTs) are a type of token-based authentication and authorization mechanism commonly used in web applications. The primary purpose of JWTs is to securely transmit information between parties as a JSON object. They are often used for authentication, authorization, and data exchange in client-server architectures.

JWTs consist of a header, payload, and signature. The data is encoded using Base64URL and concatenated with periods. Servers create and sign JWTs, while clients decode and verify them. JWTs are not encrypted, so sensitive information should not be included in the payload.

## How does JWT Authentication integrate with Django REST Framework to secure API endpoints, and what are the key components involved in this process?

JWT authentication in Django REST Framework (DRF) involves the following key components: 

1. JWT Authentication Middleware: Validates JWT tokens.
2. Authentication Backend: Configures JWT authentication in DRF settings.
3. Token Generation: Generates JWT tokens upon successful authentication.
4. Token Transmission: Clients receive tokens and send them in the `Authorization` header.
5. Authorization Decorators: Secure endpoints using decorators like `@permission_classes` and `@authentication_classes`.
6. Token Verification: Middleware verifies token validity, including signature and expiration.
7. User Identification: Extracts user information from the token's payload for further authorization checks.

## Why is Django’s built-in runserver not suitable for production environments, and what are some alternative server options that should be considered for deploying a Django application?

Django's built-in runserver command is not suitable for production environments due to its limited performance, lack of security features, and scalability limitations. Alternative server options like Gunicorn, uWSGI, Nginx + uWSGI/Gunicorn, and Apache + mod_wsgi are recommended for deploying Django applications in production. These options offer better performance, scalability, security, and flexibility to handle production-level traffic and ensure optimal deployment configurations.

### *Resources:*
**Reading**

[JSON Web Tokens](https://jwt.io/introduction/)

[DRF JWT Authentication](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

[Django Runserver Is Not Your Production Server](https://build.vsupalov.com/django-runserver-in-production/)

**Videos**

[JWT with DRF](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)

**Bookmark and Review**

[Gunicorn](https://gunicorn.org/)

[Django Migrations Primer](https://realpython.com/django-migrations-a-primer/)

## Things I want to know more about