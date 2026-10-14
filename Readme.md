# 🌾 AgriConnect - Agricultural Digital Marketplace & Management System

[![Java](https://img.shields.io/badge/Java-17-orange.svg?logo=java)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.3-brightgreen.svg?logo=springboot)](https://spring.io/projects/spring-boot)
[![Thymeleaf](https://img.shields.io/badge/Thymeleaf-3.x-green.svg?logo=thymeleaf)](https://www.thymeleaf.org/)
[![SQLite](https://img.shields.io/badge/Database-SQLite-blue.svg?logo=sqlite)](https://www.sqlite.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**AgriConnect** is a full-stack Java and Spring Boot web application designed to empower farmers and streamline agricultural commerce. It directly connects farmers with wholesale buyers and consumers, eliminating exploitative middlemen, while providing crucial agricultural utilities such as live Mandi market prices, weather advisories, government subsidy information, and direct messaging.

---

## 🌟 Key Features

### 🛒 1. Direct Agricultural Marketplace
- **List Produce**: Farmers can publish fresh crops with details (variety, quantity, unit price, photos, and location).
- **Browse & Filter**: Buyers can explore available produce categorized by Vegetables, Fruits, Grains, and Commercial crops.
- **Cart & Direct Orders**: Seamless order placement with instant invoice and status tracking.

### 📊 2. Real-Time Mandi Market Prices
- Transparent daily market rates across regional Agricultural Produce Market Committees (APMC / Mandis).
- Displays **Minimum Price**, **Maximum Price**, and **Modal Price** (per kg / per Quintal) with last-updated timestamps.

### 🌦️ 3. Weather Forecast & Agricultural Advisory
- Real-time weather monitoring (Temperature, Conditions, Humidity, Wind speed, and Rainfall probability).
- Actionable agronomic advisories based on prevailing weather conditions (e.g., harvesting timing, irrigation cautions).

### 🏛️ 4. Government Schemes & Subsidies Portal
- Curated repository of central and state agricultural schemes (e.g., **PM-KISAN**, **PMFBY Crop Insurance**, **Soil Health Card**, and **Farm Equipment Subsidies**).
- Comprehensive eligibility criteria, benefit breakdowns, and official direct application links.

### 💡 5. Farming Tips & Knowledge Hub
- Expert guidance from agronomists covering soil health improvement, pest management, crop rotation, and water-saving irrigation techniques.

### 💬 6. Buyer-Farmer Communication
- In-app messaging system allowing buyers and farmers to negotiate terms, ask questions, and arrange delivery logistics.

### ⭐ 7. Reviews, Ratings & Notifications
- Peer review and rating system ensuring trust and quality between buyers and farmers.
- Automated system notifications for new orders, status changes, and critical weather warnings.

### 🛡️ 8. Role-Based Access Control (RBAC)
- Multi-role support for **Farmers**, **Buyers**, and **Administrators** with customized dashboard views.

---

## 🛠️ Technology Stack

| Layer | Technology |
|---|---|
| **Language** | Java 17 |
| **Framework** | Spring Boot 3.2.3 |
| **Web & Templating** | Spring Web MVC, Thymeleaf Template Engine |
| **Database Access** | Spring Boot Starter JDBC (`JdbcTemplate`) |
| **Database Engine** | SQLite 3 (`sqlite-jdbc` 3.45.1.0) |
| **Styling & UI** | Semantic HTML5, Vanilla CSS3 (Custom Responsive Theme), FontAwesome Icons |
| **Build & Dependency Tool** | Apache Maven 3.x (with Maven Wrapper included) |

---

## 🏗️ Architecture & Design Pattern

AgriConnect follows the standard **MVC (Model-View-Controller)** layered architecture:

```
src/main/
├── java/com/agriconnect/
│   ├── config/          # Database configuration, table creation & seeders
│   ├── controller/      # Spring MVC controllers handling HTTP requests
│   ├── model/           # Domain POJOs representing business entities
│   ├── repository/      # Data access layer using Spring JdbcTemplate
│   ├── service/         # Business logic and coordination layer
│   └── AgriConnectApplication.java  # Main application entry point
└── resources/
    ├── application.properties       # Server port & datasource configuration
    ├── static/css/                  # Custom CSS stylesheets
    └── templates/                   # Thymeleaf HTML views
```

- **Zero-Setup Database**: The application uses an embedded **SQLite** database (`agriconnect.db`). When the application starts for the first time, `DatabaseConfig.java` automatically creates all required tables and seeds default demo data.

---

## 🚀 Getting Started

### Prerequisites
- **Java Development Kit (JDK) 17** or later installed.
- **Git** installed on your machine.

### Installation & Execution

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/<YOUR-USERNAME>/AgriConnect.git
   cd AgriConnect
   ```

2. **Run the Application**:
   - **On Windows (using Maven Wrapper)**:
     ```cmd
     mvnw.cmd clean spring-boot:run
     ```
     *(Or simply double-click the included `RUN_AGRICONNECT.bat` script)*
   
   - **On Linux / macOS**:
     ```bash
     chmod +x mvnw
     ./mvnw clean spring-boot:run
     ```

3. **Access the Application**:
   Open your browser and navigate to:
   ```
   http://localhost:5000
   ```

---

## 🔑 Demo Login Credentials

The application pre-populates demo accounts with sample products, market prices, and government schemes:

| Role | Email Address | Password | Permissions |
|---|---|---|---|
| **Farmer** | `farmer@agriconnect.com` | `farmer123` | Sell produce, track orders, view market prices, weather & schemes |
| **Buyer** | `buyer@agriconnect.com` | `buyer123` | Browse marketplace, place orders, chat with farmers, post reviews |
| **Admin** | `admin@agriconnect.com` | `admin123` | Platform oversight, product and user moderation |

> *Note: You can also register a new account anytime via the Register page.*

---

## 📂 Project Directory Structure

```text
AgriConnect/
├── .mvn/wrapper/               # Maven wrapper binaries & properties
├── src/
│   ├── main/
│   │   ├── java/com/agriconnect/
│   │   │   ├── config/
│   │   │   │   └── DatabaseConfig.java
│   │   │   ├── controller/
│   │   │   │   ├── AdminController.java
│   │   │   │   ├── AuthController.java
│   │   │   │   ├── DashboardController.java
│   │   │   │   ├── MarketPricesController.java
│   │   │   │   ├── MarketplaceController.java
│   │   │   │   ├── MessageController.java
│   │   │   │   ├── NotificationController.java
│   │   │   │   ├── OrderController.java
│   │   │   │   ├── ProductController.java
│   │   │   │   ├── ProfileController.java
│   │   │   │   ├── ReviewController.java
│   │   │   │   ├── SchemeController.java
│   │   │   │   ├── TipsController.java
│   │   │   │   └── WeatherController.java
│   │   │   ├── model/
│   │   │   ├── repository/
│   │   │   └── service/
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── static/css/style.css
│   │       └── templates/*.html
├── mvnw                        # Maven wrapper script (Unix)
├── mvnw.cmd                    # Maven wrapper script (Windows)
├── pom.xml                     # Maven project configuration & dependencies
├── RUN_AGRICONNECT.bat         # 1-click Windows runner script
├── .gitignore                  # Git ignore rules
└── README.md                   # Project documentation
```

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
