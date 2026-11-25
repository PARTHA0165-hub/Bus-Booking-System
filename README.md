# Bus Reservation System

Console-based Java application for bus ticket booking, built with JDBC and MySQL.

## Features
- Displays bus details: bus number, AC or non-AC, and capacity
- Checks seat availability for a bus on a travel date before confirming a booking
- Stores each booking (passenger name, bus number, travel date) in MySQL
- Layered design: model classes, DAO classes and a separate JDBC connection class

## Tech Stack
Java · JDBC · MySQL · SQL · OOP · DAO pattern · Eclipse

## Project Structure
- `src/bus_reservation/`
  - `Bus.java`, `Booking.java`: model classes
  - `BusDAO.java`, `BookingDAO.java`: DAO classes for database operations
  - `DbConnection.java`: JDBC connection setup
  - `BusDemo.java`: application entry point (console menu)
- `lib/mysql-connector-j-9.7.0.jar`: MySQL JDBC driver

## Prerequisites
- JDK 9 or higher (the project uses `module-info.java`)
- MySQL Server
- Eclipse (or any Java IDE)

## Database Setup
Create the database and tables in MySQL:

```sql
CREATE DATABASE busresv;
USE busresv;

CREATE TABLE bus (
    id INT PRIMARY KEY,
    ac TINYINT(1),      -- 0 = non-AC, 1 = AC
    capacity INT
);

CREATE TABLE booking (
    passenger_name VARCHAR(50),
    bus_no INT,
    travel_date DATE
);
```

Add a few rows to the `bus` table before running the app.

## How to Run
1. Clone the repository and import it into Eclipse as a Java project.
2. Add `lib/mysql-connector-j-9.7.0.jar` to the project's Build Path.
3. Run the SQL above in MySQL.
4. In `DbConnection.java`, set your MySQL URL, username and password.
5. Run `BusDemo.java` as a Java Application.
6. In the console, enter `1` to book a seat or `2` to exit.

## Future Improvements
- Rebuild as a Spring Boot REST API with Spring Data JPA
- Add booking cancellation and passenger records
