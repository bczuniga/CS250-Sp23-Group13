---
UML Class Diagram
---

```mermaid
classDiagram

    RentalCar ..> CarBody
    RentalCar ..> Color
    RentalCar ..> FuelType
    RentalLocation --o "0..n" RentalCar
    RentalLocation --o "1..n" Employee
    Transaction --o "1" Customer
    Transaction --o "1" RentalCar
    Transaction --o "1" RentalLocation
    Customer --o "1" GPSLocation
    Customer --o "1..*" PaymentInfo
    Customer --|> User
    Employee --|> User
    
    class User {
        String name
        String email
        String password
        
        changeEmail(String) bool
        changePassword(String) bool
        checkAvailableCars(rentalLocation) Map<rentalCars>
    }

    class Customer {
        int age
        bool rentalAgreement
        bool rentalInsurance
        transaction[] rentalHistory
        PaymentInfo storedPayment
        GPSLocation currLocation
        
        Customer(name, email, password, age) void
        getDistance(rentalLocation) double
        signAgreement() bool
        updatePayment(paymentInfo) bool
        getRentalHistory() transaction[]
        searchForLocation(String) GPS
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
        validateRentalCar(rentalCar) void
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
        bool validCar
        
        RentalCar(String, String, String, String) void
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
        calculateTotal(costPerMile, rentalFee) double
    }
    
    class PaymentInfo {
        String paymentType
        String cardNumber
        String cardHolder
        int CVV

        PaymentInfo(paymentType, cardNumber, cardHolder) void
    }
    
    class GPSLocation {
        Pair<double> CurrentCoord
        Pair<double> DestinationCoord
        
        GPSLocation(address)
        getCoordFromAddress(String)
        getClosestRoute() double
        setCurrentCoord(Pair<double, double>) bool
        setDestinationCoord(Pair<double, double>) bool
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
    
    class FuelType {
        <<enumeration>>
        GAS
        HEV
        PHEV
        BEV
        FCEV
}
```

# What's New?
## Enumerations
We have three enumerations for CarBody, Color, and FuelType that the RentalCar class will use. Because of the variability in how an employee could input these values, we've streamlined it using these enumerations to keep it consistent across all cars.
## User
The `User` class is a superclass of both `Customer` and `Employee`. The user class is what lets us create individual account access to the system. The `User` class contains name, email, and password that is required for either types of accounts. The functions that are in the class is general account manipulation and availability of vehicles given a location it gets passed
### Customer
The `Customer` class inherits the `User` class that covers the functions and members that a customer would need to manipulate their rental account. The class also contains relevant documents such as `rentalAgreement` and `rentalInsurance` required to complete a transaction. In this class, the `GPSLocation`, and `PaymentInfo` are used as well which will be described later in the document.
### Employee
The `Employee` class now includes a validation method that checks if the customer has the proper documents and is of age in order to rent a vehicle. The changes also include functions that allow an Employee to add, modify, or remove cars in an existing fleet at a location.
## Payment info
The `PaymentInfo` class is another object that a customer creates either one or more instances of. This class contains credit card information that can be stored and used for future transactions.
## GPS Location
The `GPSLocation` class manages directions to and from a customers location to a given rental location using coordinates that the class finds given an address string passed by the customer. Any function that requires location for finding directions of will use the `GPSLocation` class. It now utilizes Pairs and GPS coordinates that allows for precise locations.
## RentalCar
The `RentalCar` class has new setters to update the class's members such as `make`, `model`, `color`, `carBody`, `year`, and `setNumSeats`.
## RentalLocation
Added an `availableCars<map>` that contains available vehicles at a given RentalLocation.
