<div align="center">

# 🐾 Pawdcast
### The All-in-One Pet Care Platform

Pawdcast brings together the scattered tools pet owners rely on — health records, expense tracking, adoption, clinic discovery, and care guidance — into a single, unified platform.

[![Java](https://img.shields.io/badge/Java-21-orange?logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-Educational-lightgrey)](#disclaimer)
[![Maintained](https://img.shields.io/badge/Maintained-yes-success)](#roadmap)

<p>
  <a href="#key-features">Features</a> •
  <a href="#tech-stack">Tech Stack</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#running-with-docker">Docker</a> •
  <a href="#roadmap">Roadmap</a>
</p>

</div>

---

## 📖 Overview

Pet owners typically juggle multiple disconnected services: one app for vaccination records, another for finding a vet, a spreadsheet for expenses, and a separate site for adoption listings. Pawdcast consolidates these into one ecosystem, built for:

- Owners managing one or several pets
- People looking to adopt, or list a pet for adoption
- Anyone maintaining health and vaccination records
- Owners who want to track pet-related expenses and daily routines
- Users looking for breed, care, and training guidance

---

## ✨ Key Features

**User & Pet Management**
- Account registration and login
- Multiple pet profiles per account
- Digital pet diary for daily updates
- Secure document locker for pet-related paperwork

**Health & Wellness Tracking**
- Vaccination and medical record management
- Health history and reminders for important dates
- Diet and daily habit tracking
- Pet insurance cost estimator

**Breed & Care Guidance**
- Detailed breed information and recommendations
- Grooming, training, and care resources
- Food recommendations and tracking

**Adoption & Legal Support**
- Adoption listings, with separate flows for seekers and givers
- Automatic adoption certificate generation
- India-specific pet ownership guidelines

**Finder Utilities**
- Nearby veterinary clinic finder
- Pet-friendly venue finder

**Expense Management**
- Log and categorize routine vs. medical spending
- Review and estimate future pet-care costs

**Pet E-Commerce (Demo)**
- Browse products, add to cart, place mock orders
- Demonstrates a basic e-commerce workflow — no real payments are processed

---

## 🧰 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, JavaScript |
| Backend | Java, Spring Boot |
| Database | MySQL |
| Data Access | Spring Data JPA, JDBC |
| Build Tool | Maven |
| Server | Embedded Apache Tomcat |
| Containerization | Docker |
| Version Control | Git, GitHub |

---

## 🏗️ Architecture

```
Client (HTML/CSS/JS)
        │
        ▼
Spring Boot Controllers
        │
        ▼
   Service Layer
        │
        ▼
Repository / DAO Layer
        │
        ▼
   MySQL Database
```

The backend follows a standard layered architecture:

- **Controller** — handles incoming HTTP requests
- **Service** — contains application/business logic
- **Repository / DAO** — communicates with MySQL
- **Model** — defines data structures
- **Config** — manages security and app-wide settings

---

## 📁 Project Structure

```
Pawdcast-Pet-Care/
├── src/
│   ├── main/
│   │   ├── java/com/pawdcast/pawdcast/
│   │   │   ├── application/
│   │   │   ├── config/
│   │   │   ├── controller/
│   │   │   ├── dao/
│   │   │   ├── model/
│   │   │   ├── repository/
│   │   │   ├── service/
│   │   │   └── PawdcastApplication.java
│   │   └── resources/
│   │       ├── static/
│   │       │   ├── index.html
│   │       │   ├── adoption.html
│   │       │   ├── clinic.html
│   │       │   ├── digilocker.html
│   │       │   ├── expenses.html
│   │       │   ├── health.html
│   │       │   └── ...
│   │       └── application.properties
│   └── test/
├── Dockerfile
├── pom.xml
├── mvnw / mvnw.cmd
├── .gitignore
└── README.md
```

---

## ⚙️ Getting Started

### Prerequisites

- Java 21 (or compatible)
- MySQL 8
- Maven (or use the included wrapper)
- Git
- An IDE — Eclipse, IntelliJ IDEA, or VS Code

### 1. Clone the repository

```bash
git clone https://github.com/AtharvaPadwal2/Pawdcast-Pet-Care.git
cd Pawdcast-Pet-Care
```

### 2. Create the database

```sql
CREATE DATABASE pawdcast;
```

### 3. Configure environment variables

In `src/main/resources/application.properties`:

```properties
spring.datasource.url=${DATABASE_URL}
spring.datasource.username=${DATABASE_USERNAME}
spring.datasource.password=${DATABASE_PASSWORD}

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

Example local values:

```
DATABASE_URL=jdbc:mysql://localhost:3306/pawdcast
DATABASE_USERNAME=root
DATABASE_PASSWORD=your_mysql_password
```

> ⚠️ Never commit real database passwords, email credentials, JWT secrets, or API keys to GitHub. Use a `.env` file or your IDE's environment variable settings, and confirm they're listed in `.gitignore`.

### 4. Run the application

```bash
# Windows
.\mvnw.cmd spring-boot:run

# Linux / macOS
./mvnw spring-boot:run
```

Or run `PawdcastApplication.java` directly from your IDE.

### 5. Open it

Visit **http://localhost:8080** (or `http://localhost:8081` if you set a custom port via `server.port` in `application.properties`).

---

## 🐳 Running with Docker

```bash
./mvnw clean package -DskipTests
docker build -t pawdcast-pet-care .
docker run -p 8080:8080 \
  -e DATABASE_URL=<your-db-url> \
  -e DATABASE_USERNAME=<your-username> \
  -e DATABASE_PASSWORD=<your-password> \
  pawdcast-pet-care
```

---

## 🗺️ Roadmap

- [ ] Responsive design across mobile devices
- [ ] Automated unit and integration tests
- [ ] Role-based authorization
- [ ] Email / in-app reminders
- [ ] Live maps for clinics and venues
- [ ] Cloud storage for pet documents
- [ ] Secure payment gateway integration
- [ ] Admin dashboard
- [ ] Accessibility and performance improvements
- [ ] Public deployment

---

## 🎯 What This Project Demonstrates

- Full-stack Java web development with Spring Boot
- RESTful backend design and layered architecture
- Spring Data JPA + MySQL integration
- Authentication and multi-user data management
- Connecting a static frontend to backend services
- Containerizing a Spring Boot app with Docker
- Version control workflow with Git and GitHub

---

## ⚠️ Disclaimer

Pawdcast is an educational project. Health, insurance, and legal information provided within the app is for informational purposes only and should not replace professional veterinary, financial, or legal advice.

---

## 👨‍💻 Author

**Atharva Padwal**
IT Engineering Student & Full-Stack Developer

- GitHub: [@AtharvaPadwal2](https://github.com/AtharvaPadwal2)
- LinkedIn: [Atharva Padwal](https://www.linkedin.com/in/atharva-padwal-11b005397)

---

<div align="center">

⭐ **If you find this project useful, consider starring the repo!** ⭐

</div>
