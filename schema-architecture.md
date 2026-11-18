# Section 1: Architecture summary

This Spring Boot application has a Thymeleaf-based web dashboard (AdminDashboard / DoctorDashboard) and a REST API client to interact via HTTP and JSON responses.
When a user interacts with the application, requests are routed to controllers. Server-rendered views are handled by the Thymeleaf controller, which returns an HTML file as a page. APIs are handled by the REST controller, which processes actions and returns a response in JSON.
The service layer is the place where logic is placed. Controller requests come here to be processed, to apply validation, perform calculations, etc.
The service communicates with the repository layer, where database operations are being performed: the MySQL repository, which handles relational data (patients, doctors, appointments, admin records), and the MongoDB repository, which handles document-based data like prescriptions.
MySQL stores core entities in an established order, MongoDB stores flexible data.
MySQL is bound to JPA entities, which are annotated with @Entity, while MongoDB uses document objects that are annotated with @Document.
In MVC, models are routed to Thymeleaf templates, where they are rendered as dynamic HTML code. REST uses the same models, but they are serialized into JSON and sent back using an HTTP response.

# Section 2: Numbered flow of data and control

1. The user accesses the app via the Thymeleaf dashboards or a REST API client.
2. The request goes to the MVC controller (HTML pages) or the REST controller (JSON).
3. The controller passes it to the common service layer.
4. The service applies validation and business logic.
5. The service calls the MySQL repository (patients, doctors, appointments, admins) or the MongoDB repository (prescriptions).
6. The repository accesses the database using JPA entities (@Entity) for MySQL or document models (@Document) for MongoDB.
7. The result returns through the same layers, rendered as a Thymeleaf HTML page (MVC) or serialized as JSON (REST).
