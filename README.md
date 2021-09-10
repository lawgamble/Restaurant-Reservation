# H1 Restaurant Reservation Application

A restaurant table reservation and seating application that allows an employee to take reservations at appropraite times and seat guests at the perfect table.



# H3 Dashboard
![Dashboard](https://raw.githubusercontent.com/lawgamble/Restaurant-Reservation/main/screenshots/Res%20Dash.PNG)
-------------
The dashboard allows you to view the current tables and their status. It will also display all reservations (depending on date).



# H3 Create Tables
![Create-Table](https://raw.githubusercontent.com/lawgamble/Restaurant-Reservation/main/screenshots/Res%20Create%20Table.PNG)
-------------
Allows user to create new tables and add available capacity to new tables.


# H3 Create Reservation 
![Create-Reservation](https://raw.githubusercontent.com/lawgamble/Restaurant-Reservation/main/screenshots/Res%20Create%20Res.PNG)
-------------
Allows user to create a brand new reservation for present and future times.


# H3 Search for reservation
![Search](https://raw.githubusercontent.com/lawgamble/Restaurant-Reservation/main/screenshots/Ress%20Search.PNG)
-------------
User is able to look up any reservation stored in the database by reservation phone number.


# H2 Stack/Tech
--------------------------------------------------------
    * React: rendering front end.
    * React Router - client-side routing through the application.
    * Node.js: Back-End.
    * CSS and bootstrap for styling.
    * Express - framework for building application's API.
    * PostgreSQL: SQL database for storing and retrieving application data.
    * Deployed with Vercel.



## API Routes
| Method   | Route                                 | Function                                                                                                                                                                                                          |
|----------|---------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `GET`    | `/reservations`                       | Gets the complete list of reservations, sorted by `reservation_date` and `reservation_time`.                                                                                                                      |
| `GET`    | `/reservations?date=YYYY-MM-DD`       | Gets all reservations made for the specified date, sorted by `reservation_time`.                                                                                                                                  |
| `POST`   | `/reservations`                       | Validates the posted reservation, adding it to the database if validations pass.                                                                                                                                  |
| `GET`    | `/reservations/:reservationId`        | Gets the reservation with the specified ID, assuming such a reservation exists in the database.                                                                                                                   |
| `PUT`    | `/reservations/:reservationId`        | Validates the updated reservation information, updating the reservation with the specified ID using the sent data if validations pass.                                                                            |
| `PUT`    | `/reservations/:reservationId/status` | Updates the status of the reservation with the specified ID according to the `status` parameter inside of the request body data.                                                                                  |
| `GET`    | `/tables`                             | Gets the complete list of tables.                                                                                                                                                                                 |
| `POST`   | `/tables`                             | Validates the posted table, adding it to the database if validations pass.                                                                                                                                        |
| `PUT`    | `/tables/:tableId/seat`               | Seats the specified table using the reservation specified in the request body data. Updates the reservation's entry to a status of `seated` and the        table's entry to the reservation_id of the given reservation. |
| `DELETE` | `/tables/:tableId/seat`               | Finishes the specified table. Updates the table's reservation_id to `null` and the associated reservation's status to `finished`.                                                                                 |

    
## Installation

1. Clone this repository to a local directory.
1. Run `cp ./back-end/.env.sample ./back-end/.env`.
1. Update the `./back-end/.env` file with the connection URLs to your PostgreSQL database instances.
1. Run `cp ./front-end/.env.sample ./front-end/.env`.
1. You should not need to make changes to the `./front-end/.env` file unless you want to connect to a backend at a location other than `http://localhost:5000`.
1. Run `npm install` to install project dependencies.
1. Run `npm run start:dev` to start the application in development mode.












    