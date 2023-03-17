---
UML Class Diagram
---

```mermaid
classDiagram

    % Relationships
    RentalCar ..> CarBody
    RentalCar ..> Color
    RentalLocation --o "0..n" RentalCar : 0..n
    RentalLocation --o "1..n" Employee : 1..n
    Transaction --o "1" PaymentInfo : 1
    Customer --|> User
    Employee --|> User
    
    class User {
        String name
        String email
        String password
        
        changeEmail() bool
        changePassword() bool
        checkAvailableCars(rentalLocation) Map<rentalCars>
    }

    class Customer {
        int age
        bool rentalAgreement
        bool rentalInsurance
        transaction[] rentalHistory
        PaymentInfo storedPayment
        String currAddress
        
        getDistance(rentalLocation) double
        signAgreement() bool
        updatePayment(paymentInfo() bool
        getRentalHistory() transaction[]
        searchForLocation(currAddress) GPS
    }
    
    class Employee {
        rentalLocation location
        int employeeID
        
        setRentalFee(double) void
        getRentalFee() double
        checkCustomer(Customer) bool
        addAvailableCar(rentalCar) bool
        removeAvailableCar(rentalCar) bool
        checkCarAvailability(rentalCar) bool
        checkAvailableFleet(rentalLocation) Map<rentalCar>
        setCPM(rentalCar, double) bool
    }

    class RentalCar {
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
        setColor(String) void
        setCarBody(String) void
        setYear(int) void
        setNumSeats(int) void
    }
    
    class RentalLocation {
        Map<rentalCar> availableCars
        int numAvailableCars
        String address
        int numEmployees
        double rentalFee
        
        getHoursOperation() String
    }
    
    class Transaction {
        Customer assignedCustomer
        RentalCar desiredCar
        RentalLocation location
        PaymentInfo paymentMethod
        double totalCost
        
        cancelTransaction() bool
        checkRequirements(Customer) bool
        completeTransaction() bool
        calculateTotal(CPM, rentalFee) double
    }
    
    class PaymentInfo {
        String paymentType
        String cardNumber
        String cardHolder
        int CVV
    }
    
    class GPSLocation {

    }
    
    class CarBody {
        <<enumeration>>
        SEDAN
        COUPE
        HATCHBACK
        SUV
        CROSSOVER
        TRUCK
        MINIVAN
    }

    class Color {
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
