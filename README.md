# Oops
# Railway Reservation System (Java Console App)

A console-based **Railway Ticket Reservation System** built in Java to demonstrate core Object-Oriented Programming concepts: abstraction, inheritance, polymorphism, and interfaces.

## Features

- Choose from 3 train types: **Express**, **SuperFast**, **Passenger**
- Choose from 3 ticket classes: **General**, **Sleeper**, **AC**
- Automatic fare calculation based on ticket class
- Choose from 3 payment methods: **UPI**, **Card**, **Net Banking**
- Prints a final ticket summary on successful booking

## Project Structure

```
railway-reservation-system/
├── pom.xml
├── README.md
├── .gitignore
├── LICENSE
└── src/
    └── main/
        └── java/
            └── com/
                └── railway/
                    ├── Railway.java                 # Main entry point
                    ├── model/
                    │   ├── Train.java                # Abstract base class
                    │   ├── ExpressTrain.java
                    │   ├── SuperFastTrain.java
                    │   └── PassengerTrain.java
                    ├── ticket/
                    │   ├── Ticket.java                # Abstract base class
                    │   ├── General.java
                    │   ├── Sleeper.java
                    │   └── AC.java
                    ├── payment/
                    │   ├── Payment.java               # Interface
                    │   ├── UPIPayment.java
                    │   ├── CardPayment.java
                    │   └── NetBankingPayment.java
                    └── passenger/
                        └── Passenger.java
```

## Design Overview

| Concept        | Where it's used                                              |
|----------------|---------------------------------------------------------------|
| Abstraction    | `Train` and `Ticket` are abstract classes                     |
| Inheritance    | `ExpressTrain`, `SuperFastTrain`, `PassengerTrain` extend `Train`; `General`, `Sleeper`, `AC` extend `Ticket` |
| Interface      | `Payment` implemented by `UPIPayment`, `CardPayment`, `NetBankingPayment` |
| Polymorphism   | `showTrainDetails()`, `calculateFare()`, and `makePayment()` behave differently per subclass/implementation |

## Requirements

- JDK 17 or later
- Maven 3.6+ (optional, for building with `pom.xml`)

## How to Run

### Option 1 — Using Maven

```bash
mvn clean package
java -jar target/railway-reservation-system.jar
```

### Option 2 — Using javac directly

```bash
# From the project root
javac -d out $(find src -name "*.java")
java -cp out com.railway.Railway
```

## Sample Flow

1. Enter passenger name and age
2. Select a train type and enter source/destination
3. Select a ticket type (fare is calculated automatically)
4. Review the ticket summary
5. Select a payment method to complete the booking

## Future Improvements

- Add unit tests (JUnit) for fare calculation logic
- Persist bookings to a file or database
- Add seat availability and booking IDs
- Build a simple GUI or REST API wrapper

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
