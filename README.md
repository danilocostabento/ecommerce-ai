# 🛒 E-commerce AI

A full-stack e-commerce application designed to explore modern software architecture, multiple database technologies, REST APIs, artificial intelligence, and scalable application design.

The project combines a **React + TypeScript frontend** with a **Java + Spring Boot backend**, using different database technologies according to the characteristics of each domain.

---

## 🚧 Project Status

> **In Development**

The project is currently in the initial setup and architecture phase.

### Current stage

* [x] Repository initialized
* [x] React + TypeScript + Vite initialized
* [x] Sass configured
* [x] Java environment configured
* [x] Spring Boot + Maven backend initialized
* [ ] Frontend base architecture
* [ ] Backend base architecture
* [ ] Product catalog
* [ ] Product database
* [ ] User authentication
* [ ] Shopping cart
* [ ] Order management
* [ ] Payment flow
* [ ] Product recommendations
* [ ] AI/ML recommendation system
* [ ] Automated tests
* [ ] CI/CD
* [ ] Production deployment

---

# 🏗️ Architecture

The application is planned as a full-stack distributed architecture.

```text
                         ┌─────────────────────┐
                         │      React SPA       │
                         │   TypeScript + Vite  │
                         └──────────┬──────────┘
                                    │
                                  HTTP
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    Spring Boot API   │
                         │     Java + Maven     │
                         └──────────┬──────────┘
                                    │
                 ┌──────────────────┼──────────────────┐
                 │                  │                  │
                 ▼                  ▼                  ▼
          ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
          │  MongoDB    │    │ PostgreSQL  │    │    Redis    │
          │             │    │             │    │             │
          │  Products   │    │ Users       │    │ Cart        │
          │  Catalog    │    │ Orders      │    │ Sessions    │
          │  Reviews    │    │ Payments    │    │ Cache       │
          └─────────────┘    └─────────────┘    └─────────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Recommendation / AI │
                         │       Services      │
                         └─────────────────────┘
```

The architecture follows a **polyglot persistence** approach, where each database technology is used according to the type of data and access pattern it is designed to handle.

---

# 💻 Technology Stack

## Frontend

| Technology   |            Version | Purpose                                 |
| ------------ | -----------------: | --------------------------------------- |
| React        |             19.3.0 | User interface                          |
| TypeScript   | See `package.json` | Static typing                           |
| Vite         |              8.3.0 | Frontend tooling and development server |
| Sass         |            1.105.0 | CSS preprocessor                        |
| React Router |            Planned | Client-side routing                     |

![React](https://img.shields.io/badge/React-19.3.0-61DAFB?logo=react\&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript\&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-8.3.0-646CFF?logo=vite\&logoColor=white)
![Sass](https://img.shields.io/badge/Sass-1.105.0-CC6699?logo=sass\&logoColor=white)

---

## Backend

| Technology        |       Version | Purpose                         |
| ----------------- | ------------: | ------------------------------- |
| Java              |        21 LTS | Backend programming language    |
| Spring Boot       |         4.1.1 | Backend framework               |
| Maven             | Maven Wrapper | Dependency and build management |
| Spring Web        |         4.1.1 | REST API                        |
| Spring Validation |         4.1.1 | Request/data validation         |

![Java](https://img.shields.io/badge/Java-21-ED8B00?logo=openjdk\&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.1-6DB33F?logo=springboot\&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-Build-C71A36?logo=apachemaven\&logoColor=white)

---

# 🗄️ Databases

The application will use multiple database technologies.

### MongoDB

Used primarily for:

* Product catalog
* Product attributes
* Categories
* Product reviews
* Flexible product metadata

![MongoDB](https://img.shields.io/badge/MongoDB-Document%20Database-47A248?logo=mongodb\&logoColor=white)

### PostgreSQL

Used as the relational system of record for:

* Users
* Addresses
* Orders
* Order items
* Payments
* Coupons
* Transactional data

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Relational%20Database-4169E1?logo=postgresql\&logoColor=white)

### Redis

Used for high-speed and temporary data:

* Shopping carts
* Sessions
* Caching
* Temporary application state
* Recommendation caching

![Redis](https://img.shields.io/badge/Redis-Cache%20%2F%20Key--Value-DC382D?logo=redis\&logoColor=white)

---

# 🤖 Artificial Intelligence

The project will eventually include an AI-powered recommendation system.

Potential capabilities include:

* Product recommendations
* Similar product detection
* User behavior analysis
* Semantic product search
* Product embeddings
* Personalized recommendations

The recommendation architecture will be developed separately from the main REST API where appropriate.

---

# 📦 Project Structure

```text
ecommerce-ai/
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── types/
│   │   └── styles/
│   ├── package.json
│   └── vite.config.ts
│
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   └── resources/
│   │   └── test/
│   ├── pom.xml
│   ├── mvnw
│   └── mvnw.cmd
│
├── docs/
│   └── architecture/
│
├── .gitignore
├── README.md
└── docker-compose.yml
```

---

# 🎨 Frontend Architecture

The frontend uses a component-based architecture.

```text
src/
│
├── assets/
│
├── components/
│   ├── Header/
│   ├── Footer/
│   ├── ProductCard/
│   └── ...
│
├── pages/
│   ├── Home/
│   ├── Products/
│   ├── ProductDetails/
│   ├── Cart/
│   └── Checkout/
│
├── services/
│   └── api.ts
│
├── types/
│   └── ...
│
├── styles/
│   ├── abstracts/
│   ├── base/
│   └── main.scss
│
├── App.tsx
└── main.tsx
```

Component-specific styling will use **SCSS Modules**:

```text
ProductCard/
├── ProductCard.tsx
└── ProductCard.module.scss
```

This keeps component styles isolated and prevents global CSS conflicts.

---

# ☕ Backend Architecture

The Spring Boot application will follow a layered architecture.

```text
backend/
└── src/main/java/com/ecommerce/backend/
    │
    ├── controller/
    │
    ├── service/
    │
    ├── repository/
    │
    ├── model/
    │
    ├── dto/
    │
    ├── config/
    │
    └── exception/
```

### Responsibilities

**Controller**

Handles HTTP requests and responses.

**Service**

Contains business logic.

**Repository**

Handles persistence and database communication.

**Model**

Represents application/domain entities.

**DTO**

Defines data structures exchanged through the API.

**Config**

Contains application configuration.

**Exception**

Contains centralized exception handling.

---

# 🔄 Data Flow

A typical product request will follow this flow:

```text
React
  │
  │ GET /api/products
  ▼
Spring Boot Controller
  │
  ▼
Product Service
  │
  ▼
Product Repository
  │
  ▼
MongoDB
  │
  ▼
Product Repository
  │
  ▼
Product Service
  │
  ▼
Controller
  │
  ▼
JSON Response
  │
  ▼
React
```

---

# 🛒 Shopping Cart Architecture

The shopping cart will primarily use Redis.

```text
React
   │
   │ POST /api/cart
   ▼
Spring Boot
   │
   ▼
Redis
   │
   └── cart:user:{userId}
```

The cart is intentionally separated from the relational transactional database because it represents temporary, frequently accessed state.

During checkout:

```text
Redis
  │
  │ Retrieve cart
  ▼
Spring Boot
  │
  ├── MongoDB
  │      └── Validate products
  │
  └── PostgreSQL
         └── Create order
```

---

# 🧰 Development Environment

The project is developed primarily using **GitHub Codespaces**.

Expected development environment:

| Tool    |                Version |
| ------- | ---------------------: |
| Node.js |                 22 LTS |
| npm     |   Bundled with Node.js |
| Java    |                 21 LTS |
| Maven   |          Maven Wrapper |
| Git     | Codespaces environment |
| Docker  | Codespaces environment |

![Node.js](https://img.shields.io/badge/Node.js-22%20LTS-339933?logo=node.js\&logoColor=white)
![GitHub Codespaces](https://img.shields.io/badge/GitHub-Codespaces-181717?logo=github\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?logo=docker\&logoColor=white)

---

# 🚀 Running the Project

## Frontend

```bash
cd frontend
npm install
npm run dev
```

The Vite development server will normally be available on:

```text
http://localhost:5173
```

---

## Backend

```bash
cd backend
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

The Spring Boot API will normally be available on:

```text
http://localhost:8080
```

---

# 🔧 Environment Variables

Sensitive configuration must not be committed to the repository.

Environment-specific configuration will use environment variables.

Example:

```env
MONGODB_URI=
POSTGRESQL_URL=
POSTGRESQL_USERNAME=
POSTGRESQL_PASSWORD=
REDIS_HOST=
REDIS_PORT=
JWT_SECRET=
```

A `.env.example` file will be maintained as a template.

---

# 🧪 Testing

Testing will be introduced progressively throughout the project.

### Frontend

Planned:

* Unit tests
* Component tests
* Integration tests
* End-to-end tests

### Backend

Planned:

* Unit tests
* Service tests
* Repository tests
* Controller/API tests
* Integration tests

---

# 🔐 Security

Security will be implemented progressively.

Planned features:

* Authentication
* Authorization
* Password hashing
* JWT/session management
* Input validation
* API security
* CORS configuration
* Environment-based secrets
* Secure payment integration

---

# 📈 Observability

The project will eventually include:

* Application logging
* Health checks
* Metrics
* Error tracking
* API monitoring
* Database monitoring

---

# ☁️ Deployment

The production architecture is planned to use separate deployments for the frontend and backend.

```text
                 ┌───────────────┐
                 │    Browser    │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │    Frontend   │
                 │ React + Vite  │
                 └───────┬───────┘
                         │
                         │ HTTPS
                         ▼
                 ┌───────────────┐
                 │    Backend    │
                 │ Spring Boot   │
                 └───────┬───────┘
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
      MongoDB       PostgreSQL        Redis
```

---

# 📚 Main Technologies

![React](https://img.shields.io/badge/React-19.3.0-61DAFB?logo=react\&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript\&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-8.3.0-646CFF?logo=vite\&logoColor=white)
![Sass](https://img.shields.io/badge/Sass-1.105.0-CC6699?logo=sass\&logoColor=white)
![Java](https://img.shields.io/badge/Java-21-ED8B00?logo=openjdk\&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.1-6DB33F?logo=springboot\&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-Build-C71A36?logo=apachemaven\&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb\&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql\&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker\&logoColor=white)
![GitHub Codespaces](https://img.shields.io/badge/GitHub-Codespaces-181717?logo=github\&logoColor=white)

---

# 📌 Development Philosophy

This project is being developed with a focus on:

* Clean architecture
* Separation of concerns
* RESTful API design
* Type safety
* Database specialization
* Scalability
* Maintainability
* Automated testing
* Security
* Observability
* Cloud deployment
* AI integration

The goal is not simply to build an e-commerce application, but to use the project as a practical study of **modern full-stack software architecture**.
