# ✈️ Airplane Booking System

Discover the world of airplane tickets booking system through our micro-service architecture. Our project features four powerful services, each with its own repository:

| **Service**             |                                   **Repository**                                    |
| :---------------------- | :---------------------------------------------------------------------------------: |
| 🌐 **API Gateway**      |   [Explore the Code](https://github.com/manojkumar-0108/Flights-API-Gateway.git)    |
| ✈️ **Flights Service**  |     [Explore the Code](https://github.com/manojkumar-0108/flights-Service.git)      |
| 📅 **Bookings Service** | [Explore the Code](https://github.com/manojkumar-0108/flights-booking-service.git)  |
| 🔔 **Reminder Service** | [Explore the Code](https://github.com/manojkumar-0108/flights-reminder-service.git) |

Explore each repository to discover the implementation details of these services and the unique features they offer.

### 🙏 Thank You [Sanket Sir](https://github.com/singhsanket143)

A big thank you to our tutor for guiding us through this project. Your expertise and dedication have been invaluable in helping us learn and grow. I truly appreciate your effort and patience! Lot's of love sir 🌟

## 🌟 Architecture of the Project

1. **API Gateway**: 🛡️ Acts as the single entry point for handling incoming requests, routing them to the appropriate services, and ensuring smooth communication. It also manages user authentication and authorization for security.

2. **Flights Service**: ✈️ Manages information about flights, including schedules, routes, and availability. Connects directly to the API Gateway to process user requests and send relevant data back through it.

3. **Bookings Service**: 📅 Handles bookings and reservations for flights. Connects directly to the API Gateway and communicates with the Flights Service to process bookings. It also processes payments and publishes booking confirmation emails to RabbitMQ, which the Reminder Service consumes.

4. **Reminder Service**: 📧 Sends reminders and notifications to customers about their bookings and flights. This service interacts with RabbitMQ to access emails that need to be sent to customers, offering both immediate and scheduled notifications.

### 📊 Diagram:

```
                                   +---------------+
                                   |      API      |
                                   |    Gateway    |
                                   |      ---      |
				       |    Reverse    |
                                   |     Proxy     |
                                   +------+--------+
                                          |
                                          |
              +---------------------------+------------------------+
              |                           |                        |
              |                           |                        |
        +-----+-----+              +------+-----+           +------+------+
        |  Flights  |              |  Bookings  |           |   Reminder  |
        |  Service  |              |  Service   |           |   Service   |
        +-----------+              +------+-----+           +-------+-----+
					  |                         |
                                          |                         |
                        +-----------------+-----------+             |
                        |                             |             |
                        |                           (PUB)         (SUB)
                        |                             |             |
                 +------+------+               +------+------+      |
                 |  Payments   |               |Message Queue|<-----+
                 +-------------+               +-------------+

```

## 🎯 Key Highlights of the Project

1. ✅ Utilized a `Reverse Proxy` for efficient traffic management and load balancing.

2. ✅ Integrated a `Rate Limiter` to manage traffic flow, prevent overloading, and safeguard against DDoS attacks.

3. ✅ The project follows an `enhanced MVC` architecture that includes:

   - `Routes`: 🌐 Defines API routes for the application.

   - `Middlewares` : 🛡️ Handles request validation, authentication, and authorization before passing control to controllers.

   - `Controllers` : 💼 Acts as an intermediary between services and the view, processing requests, communicating with services, and returning responses to the user.

   - `Services` : 🔧 Manages core application functionality and business logic, communicating with the repository layer for database interaction.

   - `Models`: 🧩 Describes data models, including entities, relationships, and schemas.

   - `Repository`: 📊 Interacts with the database, utilizing the model layer for database operations.

   - `Utils` : 🛠️ Contains common utility functions used throughout the application.

   - `Migrations` : 🛠️ Manages database migrations, including schema changes, constraints, and table updates.

   - `Seeders` : 🌱 Populates the database with default values such as user roles (e.g. customer, visitor, admin).

4. ✅ Solved engineering challenges such as:

   - `Seat Selection`: 🛫 Efficiently resolved conflicts to ensure accurate seating arrangements.

   - `Concurrent Bookings`: 📅 Successfully managed overlapping reservations to prevent conflicts.

   - `Payments`: 💳 Utilized idempotency keys for secure and consistent transactions, ensuring reliable financial operations.

## ⚙️ Technologies Used

- **`Node.js`**: A versatile, server-side JavaScript runtime for building scalable and efficient applications.

- **`Express.js`**: A minimalist web framework for Node.js, providing robust routing and middleware capabilities.

- **`Git`**: A version control system for managing code changes and collaboration among team members.

- **`MSSQL`**: A relational database management system that offers robust data storage and querying capabilities.

- **`Sequelize ORM`**: An object-relational mapping tool for Node.js that simplifies database interactions and model management.

- **`Postman`**: A popular API development tool for testing, documenting, and collaborating on APIs.

---
