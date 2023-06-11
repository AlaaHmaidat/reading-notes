Django Key Components:
----------------------
- Models: Define the structure and behavior of the data in a database.
- Views: Handle the logic and processing of a web request.
- Templates: Define the presentation layer of a web application.
- URLs: Map specific URLs to corresponding views.
- Forms: Simplify user input handling and validation.
- Middleware: Perform various functions between the web server and Django's view processing.

Django's MTV Architecture:
---------------------------
In Django's Model-View-Template (MTV):
- Models represent the data layer and define the database schema.
- Views handle the logic and interact with models to prepare data.
- Templates define how the data is presented to the user.

Web Request-Response Cycle in Django:
--------------------------------------
1. User makes a request by entering a URL.
2. Django's URL resolver maps the URL to a view.
3. View processes the request, interacts with models, and prepares data.
4. View selects the appropriate template and renders it with the data.
5. Rendered template is returned as a response to the user's browser.
6. User's browser receives the response, renders HTML, and displays the web page.

Tailwind CSS vs. Bootstrap CSS:
-------------------------------
Tailwind CSS:
- Purpose: Utility-first CSS framework with a customizable approach.
- Styling Approach: Apply utility classes directly in HTML for flexible styling.

Bootstrap CSS:
- Purpose: Opinionated CSS framework with pre-designed components.
- Styling Approach: Use pre-defined CSS classes and HTML markup for consistent styles.
