# Django REST Framework & Docker
Docker is an open-source platform that allows you to automate the deployment, scaling, and management of applications using containerization. It provides a way to package an application and its dependencies into a standardized unit called a container. Containers are lightweight, isolated environments that run applications consistently across different computing environments, such as development, testing, and production.

## The key components of a Docker container, and how do they help streamline the development and deployment of applications
Docker containers are like virtual machines, but much lighter and faster. They package applications and all their dependencies into a single unit, making them easy to move and run consistently on any system with Docker installed. 

With Docker, developers can create a `Dockerfile`, which is a set of instructions that specify how to build the application environment. This ensures that everyone working on the project uses the same setup, reducing compatibility issues and making collaboration smoother.

Once the Docker image is built, it can be run as a container. Containers are isolated, meaning they don't interfere with other containers or the host system. They provide a controlled environment for the application to run reliably, regardless of the underlying infrastructure.

Docker containers are highly portable, which means you can develop locally, test, and then deploy the same container to production. This eliminates the need to worry about differences in operating systems, libraries, or configurations between development and deployment environments.

In addition, Docker simplifies scalability. You can easily scale up or down by running multiple containers of the same image to handle increased traffic or demand. Docker also offers orchestration tools like Docker Swarm or Kubernetes, which automate the management of multiple containers across multiple hosts or clusters.

Overall, Docker containers streamline the development and deployment process by providing a consistent, portable, and scalable environment, while reducing compatibility issues and simplifying collaboration.

## Describe the primary steps involved in building a library website using Django, including essential components like models, views, and templates

### 1. Set up a new Django project
```
django-admin startproject project_name
```
### 2. Create a new Django app within the project
```
python manage.py startapp app_name
```
### 3. Define Models
In the app_name/models.py file, define models using Django's model syntax

### 4. Create Database Tables
```
python manage.py makemigrations
python manage.py migrate
```
### 5. Create Views
In the app_name/views.py file, define view functions or classes to handle logic and interact with models

### 6. Design URLs
In the app_name/urls.py file, define URL patterns that map to specific views

### 7. Build Templates
Create HTML templates in the app_name/templates directory to define the visual layout and structure

### 8. Link Views to Templates
In the views, render the appropriate template using the render() function or class-based views

### 9. Handle Forms
In the app_name/forms.py file, define forms to handle user input and validation

### 10. Apply Styling and CSS
Add CSS styles to the templates or link external CSS files to customize the appearance

### 11. Test and Debug
Continuously test the website's functionality and debug any issues or errors

### 12. Implement User Authentication
Use Django's built-in authentication views and decorators to handle user login, registration, and authorization

### 13. Dockerize the Application

- Create a Dockerfile in the project's root directory, specifying the base image, copying project files, installing dependencies, exposing ports, and setting the entry point.

### 14. Build the Docker Image
```
docker build -t library_image .
```
### 15. Run the Docker Container
```
docker run -p 8000:8000 library_image
```
### 16. Deploy the Website
Deploy the Docker container to a web server or hosting platform for public access

## Explain the primary differences between Django and Django REST framework

- **Django** is a full-stack web framework primarily used for building web applications. It focuses on server-side rendering of HTML pages and provides tools for various web development tasks.

- **Django REST framework**, on the other hand, is an extension of Django specifically designed for building Web APIs. It emphasizes API development and follows RESTful design principles. It includes features for data serialization, authentication, and API interaction.

**REST** stands for "`Representational State Transfer`" It is an architectural style for designing networked applications. RESTful systems are based on a set of principles that prioritize simplicity, scalability, and uniformity in the design of web services.



| Aspect               | Django                                              | Django REST framework                                |
| -------------------- | --------------------------------------------------- | --------------------------------------------------- |
| `Purpose`              | Full-stack web framework for building web apps      | Toolkit for building RESTful APIs                   |
| `API Development`     | Basic support for building APIs                     | Specifically designed for building APIs             |
| `Serialization`        | Basic support                                       | Powerful serialization framework for APIs           |
| `Authentication`       | Support for various authentication methods          | Simplified implementation of authentication methods |
| `Browsable API`        | Not available                                       | Provides a browsable API for testing and exploration|
| `URL Routing`          | Regular expressions-based routing                   | Flexible and powerful routing system for APIs       |


In summary, Django is a web framework for building web applications, while Django REST framework is an extension of Django focused on API development and RESTful API design.

### *Resources:*
**Reading**

[Beginner’s Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)

[Django for APIs - Library Website](https://djangoforapis.com/library-website-and-api/)

**Bookmark and Review**

[Beginner’s Guide to Django REST Framework](https://learndjango.com/tutorials/official-django-rest-framework-tutorial-beginners)

## Things I want to know more about
