## Architecture summary
This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models. 

## Numbered flow of data and control
1. User accesses AdminDashboard or Appointment pages or DoctorDashboard.
2. The action is routed to the appropriate Thymeleaf or REST controller or API controller.
3. The controller calls the service layer which is common for all type controllers.
4. Each serices will use their respective repostories .
5. Two databases are used MYSQL & MongoDB . Both are accessible through same service layer .
6. Each type of data  is mapped to Table or Document as per their data sturcture .
7. These data models will used to persist and transfer data between  different layers . 

