---
UML Class Diagram
---

```mermaid
classDiagram
    rentalCar ..> carBody
    rentalCar ..> color
    class user {
        String name
        String email
        String password
        changeEmail() bool
        changePassword() bool
    }

    class customer {
        int age
        bool rentalAgreement
        bool rentalInsurance
        transaction[] rentalHistory
    }

    class rentalCar {
        String make
        String model
        String color
        String carBody
        int year
        int numSeats
        double MPG/e
        String fuelType
        Date unavailableDates
        int odometer
        double costPerMile

        isAvailable(String) bool
        getDetails() String
        setMake(String) void
        setModel(String) void
        setColor() void
    }

    class carBody {
        <<enumeration>>
        SEDAN
        COUPE
        HATCHBACK
        SUV
        CROSSOVER
        TRUCK
        MINIVAN
    }

    class color {
        <<enumeration>>
        WHITE
        BLACK
        GREY
        SILVER
        BLUE
        RED
        BROWN
        GREEN
        ORANGE
        BEIGE
        PURPLE
        GOLD
        YELLOW
    }
```
