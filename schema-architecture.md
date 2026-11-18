# Section 1: Architecture summary

This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models.

# Section 2: Numbered flow of data and control

1. The user accesses the app via Thymeleaf dashboards (Admin/Doctor) or an API client.
2. The action is sent to an MVC or REST controller.
3. The controller forwards the request to the common service layer.
4. The service handles the backend logic.
5. The service calls the right repository: MySQL (patients, doctors, appointments, admins) or MongoDB (prescriptions).
6. The repository talks to the database, using JPA entities for MySQL and document models for MongoDB.
7. The result returns through the same layers as a Thymeleaf page or JSON response.
