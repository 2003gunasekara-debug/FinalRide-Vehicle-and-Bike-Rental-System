# 🚗 FinalRide — Vehicle & Bike Rental System

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Servlet](https://img.shields.io/badge/Servlet-4.0.1-blue?style=for-the-badge)
![JSP](https://img.shields.io/badge/JSP-Pages-orange?style=for-the-badge)
![Bootstrap](https://img.shields.io/badge/Bootstrap-4.0-purple?style=for-the-badge&logo=bootstrap&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-Build-C71A36?style=for-the-badge&logo=apache-maven&logoColor=white)

**A full-featured vehicle and bike rental & ride-sharing web application built with Java Servlets, JSP, and Bootstrap 4.**

[Features](#-features) • [Tech Stack](#-tech-stack) • [Project Structure](#-project-structure) • [Setup](#-setup--installation) • [Usage](#-usage) • [Screenshots](#-screenshots)

</div>

---

## ✨ Features

### 🔐 User Management
- **User Registration** — Sign up as a Rider or Admin
- **User Login** — Secure session-based authentication
- **Profile Management** — Update email, change password
- **Account Deletion** — Delete your account with confirmation

### 🚴 Bike Rental
- **Add Bikes** — Admin can add new bikes (Electric/Regular)
- **Browse Bikes** — View all available bikes with pricing
- **Edit/Delete Bikes** — Full CRUD operations on bike listings

### 🛣️ Ride Sharing
- **Offer a Ride** — Drivers can post ride offers with origin, destination, date, seats & price
- **Browse Rides** — View all available rides
- **Edit/Delete Rides** — Manage ride listings
- **Book a Ride** — Select seats and payment method to book

### 📋 Booking System
- **Create Bookings** — Book rides with seat selection and payment
- **View My Bookings** — See all your active and past bookings
- **Cancel Bookings** — Cancel bookings when needed

### ⭐ Review System
- **Submit Reviews** — Rate and review rides or bikes (1-5 stars)
- **View Reviews** — Browse all community reviews
- **Delete Reviews** — Remove reviews when necessary

---

## 🛠 Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | Java Servlets (javax.servlet 4.0.1) |
| **Frontend** | JSP (JavaServer Pages) |
| **UI Framework** | Bootstrap 4 + Colorlib Autoroad Template |
| **Build Tool** | Apache Maven |
| **Server** | Apache Tomcat |
| **Data Storage** | File-based persistence (.txt files) |
| **Font** | Google Fonts (Poppins) |

---

## 📂 Project Structure

```
FinalRide-main/
├── pom.xml                          # Maven build configuration
├── .gitignore                       # Git ignore rules
├── README.md                        # This file
├── Data/                            # Data storage directory
│   ├── users.txt                    # User records
│   ├── rides.txt                    # Ride records
│   ├── bikes.txt                    # Bike records
│   ├── bookings.txt                 # Booking records
│   └── reviews.txt                  # Review records
└── src/
    └── main/
        ├── java/
        │   ├── model/               # Data models (POJOs)
        │   │   ├── User.java        # User entity
        │   │   ├── Ride.java        # Ride entity
        │   │   ├── Bike.java        # Bike entity
        │   │   ├── Booking.java     # Booking entity
        │   │   └── Review.java      # Review entity
        │   ├── servlet/             # HTTP Servlets (Controllers)
        │   │   ├── UserServlet.java    # Auth & user CRUD
        │   │   ├── RideServlet.java    # Ride CRUD
        │   │   ├── BikeServlet.java    # Bike CRUD
        │   │   ├── BookingServlet.java # Booking operations
        │   │   └── ReviewServlet.java  # Review operations
        │   └── utils/               # Utility classes
        │       └── UserUtils.java   # User validation helpers
        └── webapp/
            ├── index.jsp            # Landing page
            └── WEB-INF/
                ├── web.xml          # Deployment descriptor
                ├── login.jsp        # Login page
                ├── register.jsp     # Registration page
                ├── profile.jsp      # User settings/profile
                ├── listRides.jsp    # Available rides listing
                ├── listBikes.jsp    # Available bikes listing
                ├── offerRide.jsp    # Create ride offer form
                ├── editRide.jsp     # Edit ride form
                ├── bookRide.jsp     # Book a ride form
                ├── myBookings.jsp   # User bookings view
                ├── addBike.jsp      # Add new bike form
                ├── editBike.jsp     # Edit bike form
                ├── submitReview.jsp # Submit review form
                └── viewReview.jsp   # Reviews listing
```

---

## 🚀 Setup & Installation

### Prerequisites
- **Java JDK** 8 or higher
- **Apache Maven** 3.6+
- **Apache Tomcat** 9.x
- **IDE** — IntelliJ IDEA / Eclipse / VS Code

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/FinalRide.git
   cd FinalRide
   ```

2. **Update file paths**
   
   Update the `FILE_PATH` constants in each servlet file to match your local setup:
   ```java
   // In each servlet, update the path:
   private static final String FILE_PATH = "YOUR_PATH/Data/users.txt";
   ```

3. **Build the project**
   ```bash
   mvn clean package
   ```

4. **Deploy to Tomcat**
   - Copy the generated `target/FinalRide.war` to Tomcat's `webapps/` directory
   - Or configure your IDE to deploy directly

5. **Start Tomcat and visit**
   ```
   http://localhost:8080/FinalRide/
   ```

---

## 💡 Usage

### Getting Started
1. **Visit the homepage** — Browse available vehicles and services
2. **Register** — Create an account as a Rider or Admin
3. **Login** — Access your dashboard

### As a Rider
- Browse available rides and bikes
- Book rides with your preferred payment method
- View and manage your bookings
- Leave reviews for rides and bikes

### As an Admin
- Add, edit, and delete bikes from the inventory
- Manage ride listings
- Oversee all bookings and reviews

---

## 🏗️ Architecture

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│   Browser   │────▶│   Servlets   │────▶│  .txt Files │
│  (JSP/HTML) │◀────│ (Controllers)│◀────│   (Data)    │
└─────────────┘     └──────────────┘     └─────────────┘
                           │
                    ┌──────┴──────┐
                    │   Models    │
                    │   (POJOs)   │
                    └─────────────┘
```

The application follows a **simplified MVC pattern**:
- **Model** — Java POJOs with file serialization (`toFileString()` / `fromFileString()`)
- **View** — JSP pages with Bootstrap 4 styling
- **Controller** — Java Servlets handling HTTP requests

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [Colorlib](https://colorlib.com/) — Autoroad Bootstrap 4 Template
- [Bootstrap 4](https://getbootstrap.com/) — Frontend framework
- [Google Fonts](https://fonts.google.com/) — Poppins font family
- [Apache Maven](https://maven.apache.org/) — Build automation

---

<div align="center">

**⭐ Star this repo if you found it helpful!**

Made with ❤️ for the FinalRide project

</div>
