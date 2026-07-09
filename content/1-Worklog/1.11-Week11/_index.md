---
title: "Week 11 Worklog"
date: 16-06-2026
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 11 Objectives:

* Initialize the backend project and design the layered architecture.
* Implement database connection, entities, and DTOs.
* Develop authentication using JWT and build core APIs (User, Field, Booking, Payment).

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Initialize backend project <br>&emsp; + Set up project structure based on layered architecture | 26/06/2026 | 26/06/2026      | |
| 3   | - Construct entities, DTOs and configure database connection <br>&emsp; + Establish Connection Pool and ORM settings | 27/06/2026 | 27/06/2026      | |
| 4   | - Implement User Registration and Login authentication <br>&emsp; + Integrate JWT (JSON Web Tokens) for security and authorization | 28/06/2026 | 28/06/2026      | |
| 5   | - Implement User management and Field management APIs <br>&emsp; + Develop standard CRUD operations for fields and profiles | 29/06/2026 | 29/06/2026      | |
| 6   | - Develop Booking API and implement business logic <br>&emsp; + Handle slot availability checks and booking conflict resolution | 30/06/2026 | 30/06/2026      | |
| 7   | - Develop Payment integration service <br>&emsp; + Update booking status after successful transactions <br> - Perform code review, optimize backend core, and implement input validation | 01/07/2026 | 02/07/2026      | |


### Week 11 Achievements:

* Initialized backend project with a robust layered architecture structure:
  * Separation of concerns: Controller, Service, Repository, Entity layers

* Configured database persistence layer:
  * Created domain entities and Data Transfer Objects (DTOs)
  * Configured connection pool and confirmed database connectivity

* Implemented authentication & authorization:
  * Secured application endpoints using stateless JWT authentication
  * Implemented role-based access control (User, Field Owner, Admin)

* Developed core business APIs:
  * CRUD endpoints for Users and Sports Fields
  * Booking endpoint with conflict-prevention slot checking logic
  * Payment processor service to handle transaction callback and update booking state

* Performed security and reliability optimization:
  * Added request interceptors and input validation middleware to secure API inputs
  * Optimized SQL queries to ensure quick response times
