# Basketball Court Booking Web App

Web application for managing bookings at a basketball facility. Players can register, search for available courts, book them individually or with a session pass, and manage their bookings. Administrators can add courts and equipment, assign equipment to courts and manage future bookings.

Built with **Java (Servlets + JSP)** following the **MVC** pattern, deployed on **Apache Tomcat** with a **MySQL** database, as a university project for the Web Programming course of the Computer Engineering degree at the University of Córdoba.

![Main page](docs/screenshot-main.png)

## Features

**Players**
- Sign up, log in and edit their personal data
- Search for available courts (indoor/outdoor, size)
- Book a court for adults, children or families, with the price calculated automatically
- Buy a session pass and book using it (one pass of each type per player)
- View, modify and cancel their bookings

**Administrators**
- Add new courts and equipment (balls, hoops, cones)
- Assign equipment to courts and update its status
- Delete future bookings, either all at once or one by one

**Security**
- Access control filter that restricts each page according to the user's role
- All database queries use `PreparedStatement`

## Architecture

The project is organised in layers:

- **View:** JSP pages styled with CSS, plus a small JavaScript script to show/hide passwords
- **Controller:** Java Servlets and JSP controllers that handle the HTTP requests
- **Business logic:** manager classes (`GestorReservas`, `GestorPistas`, `GestorUsuarios`) and factories for the different booking types
- **Data access:** DAO and DTO classes for each table (players, courts, equipment, bookings and passes)

## Tech stack

Java · Jakarta Servlets · JSP · HTML · CSS · JavaScript · MySQL · Apache Tomcat 10 · Maven

## Getting started

1. Create a MySQL database and run the script `scripts/bbdd.sql` to create the tables.
2. Copy `src/main/resources/config.properties.example` to `config.properties` and fill in your database URL, user and password.
3. Build the project with Maven:
   ```bash
   mvn package
   ```
4. Deploy the generated `.war` file on Apache Tomcat 10 and open the application in your browser.

## Documentation

The full project documentation (in Spanish) is available in [`docs/Documentacion_PW.pdf`](docs/Documentacion_PW.pdf).

## Team

Developed as a team project by José Trujillo, Guillermo, Antonio, Manuel and Carlos.
