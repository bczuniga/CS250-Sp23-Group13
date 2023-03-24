# Test Suite
## Unit Testing
### Testing Unit: Car.setCarMake
### By Cameron Cobb
```c++
<void, setCarMake(name = “Toyota”)>
RentalCar.make == “Toyota”
```

This test case should not return anything, but it should set the string attribute “make” to “Toyota” in the RentalCar class. When this content of “make” is compared to the “Toyota” function argument, a value of true should be returned. This indicates that the make attribute in the RentalCar class was properly set with the function argument  “Toyota.”

```c++
<void, setCarMake(name = "") >
Rentalcar.make == ""
```

This test case should not return anything, but it should set the string attribute “make” to an empty “” string in the RentalCar class. When RentalCar’s make attribute is compared to its argument, or the “” string, a value of true is returned. This indicates that the make attribute was properly set with “”.

```c++
<void, setCarMake(name = 5)>
Error: Invalid input
```

This test case should print an error message since the function argument, 5, is not a string argument. This error message should indicate that RentalCar.make should NOT equal 5 since an incorrect type is passed as an argument to the setCarMake function. This indicates that the make attribute in RentalCar class was not properly assigned.

```c++
<void, setCarMake(name = 'c')>
Error: Invalid input
```

This test case should print an error message since the function argument, c, is not a string argument but a char argument. This error message should indicate that RentalCar.make should NOT equal ‘c’ since an incorrect type is passed as an argument to the setCarMake function. This shows that the make attribute in RentalCar class was not properly assigned.

### Testing Unit: [Vincent, edit here]

## Integration Testing
### Testing Integration of Employee and Car classes
### By Cameron Cobb

### RentalCar newCar(string make, string model, string color, string bodyType)
### Employee.addAvailableCar(RentalCar)

```c++
RentalCar newCar(make = "Toyota", model = "Prius", color = "BLACK", bodyType = "HATCHBACK")
Employee.validateRentalCar(newCar)
newCar.validCar == true
Employee.addAvailableCar(newCar)

Output: Employee.checkAvailableCar(newCar) == true
```

This test case should add the newCar RentalCar object to the availableCars Map located in RentalLocaton. The newCar RentalCar object’s attributes are set according to the string arguments: make is set to “Toyota”, model is set to “Prius”, color is set to “Black”, and carBody is set to “Hatchback”. First, Employee.validateRentalCar(newCar) should set newCar’s validCar attribute to true since string arguments passed into the object instantiation are valid and each argument matches the data that is stored in the central database. Then, newCar.validCar should return true. Employee.checkAvailableCar(newCar) should return false, indicating that the RentalCar is not currently added to the availableCars map.  newCar.validCar should return true, which means that the rental car matches the specifications stored in the database. Afterwards, the newCar object is added to the availableCars map located in the RentalLocation, which is an object of the Employee class. After the newCar is added to the availableCars map, checkAvailableCar(newCar) should return true. The test case passes for this scenario.


```c++
RentalCar newCar(make = 4500, model = “Tundra”, color = "GREY", bodyType = "TRUCK")
Employee.addAvailableCar(newCar)
Employee.validateRentalCar(newCar)
newCar.validCar == false 

Output: Employee.checkAvailableCar(newCar) == false
```

This test case should produce an error since the newCar object is not instantiated with valid arguments. Specifically, the make attribute for the RentalCar object is not properly set because the argument 4500 is an int value and not a string.  First, Employee.validateRentalCar(newCar) should set newCar’s validCar attribute to false since string arguments passed into the object instantiation is not valid. This is verified by checking that newCar.validCar is equal to false. An error message should appear saying that the newCar was not instantiated properly, so the newCar is not added to the availableCar map via the addAvailableCar(newCar) function in the Employee class since it is not a valid object of the RentalCar class. Therefore, Employee.checkAvailableCar(newCar) will return false since newCar is not a valid object, thus indicating that the new car is not added to the fleet of available cars. If any of the string arguments to the RentalCar object creation are invalid based on type, then a valid object will never be instantiated and inserted as an available car in the availableCars map.

```c++
RentalCar newCar(make = "", model = “”, color = "", bodyType = "") >
Employee.addAvailableCar(newCar)
Employee.validateRentalCar(newCar)
newCar.validCar == false 

Output: Employee.checkAvailableCar(newCar) == false
```

This test case will not produce an error since the attributes of newCar will be set to null. First, the newCar RentalCar object is instantiated with null values for its attributes make, model, color, and bodyType respectively. Employee.valiateRentalCar(newCar) should set validCar attribute of newCar to false since null values for the attributes will not be useful to the system. newCar.validCar returns false, indicating that the rental car does not meet the specifications of cars in the database. Employee.checkAvailableCar(newCar) should return false since the object should not be present in the availableCars<RentalCar> map. Employee.addAvailableCar(newCar) adds the object to the avalableCars<RentalCar> map, and Employee.checkAvailableCar(newCar) should return false, which means that the newCar object was not successfully added to the fleet of available cars and that an object with nonnull and valid string values for its members should be added to the availableCars<RentalCar> map in RentalLocation via the addAvailableCar(newCar) function in Employee class.

```c++
RentalCar newCar(make = "Subaru", model = 500, color = 65.7, bodyType = "SEDAN")
Employee.addAvailableCar(newCar)
Employee.validateRentalCar(newCar)
newCar.validCar == false 

Output: Employee.checkAvailableCar(newCar) == false
```
  
This test case should produce an error since the newCar object is not instantiated with proper arguments. Specifically, the model and color arguments are of type int and double respectively for the RentalCar object. This means that the object will not be instantiated correctly.  First, Employee.validateRentalCar(newCar) should set newCar’s validCar attribute to false since multiple arguments passed into the constructor are not valid types. An error message should appear saying that the newCar was not instantiated properly, so the newCar is not added to the availableCar map via the addAvailableCar(newCar) function in the Employee class. Therefore, Employee.checkAvailableCar(newCar) will return false since newCar is not a valid object, thus indicating that the new car is not added to the fleet of available cars. If any of the string arguments to the RentalCar object creation are invalid based on type, then a valid object will never be instantiated and inserted as an available car in the availableCars<RentalCar> map.

```c++
RentalCar newCar(make = "25252325gffgfdg", model = "fafxcv", color = "RED", bodyType = "fsftt352")
Employee.addAvailableCar(newCar)
Employee.validateRentalCar(newCar)
newCar.validCar == false 

Output: Employee.checkAvailableCar(newCar) == false
```
  
This test case should produce an error since the newCar object is not instantiated with proper arguments. Specifically, the make, model, and bodyType attributes are assigned with string values,s but these string values do not match data that is stored inthe BeAvis central car rental database and it will not be useful to our software system. First, Employee.validateRentalCar(newCar) should set newCar’s validCar attribute to false since multiple arguments passed into the constructor do not match data that is stored in the rental database. An error message should appear saying that the arguments to the CarRental class’ constructor did not match data that is stored in the database, so the newCar is not added to the availableCar map via the addAvailableCar(newCar) function in the Employee class. Therefore, Employee.checkAvailableCar(newCar) will return false since newCar’s attributes are not accurate; If any of the string arguments to the RentalCar object creation do not match information that is stored in the database, then it should not be added to the fleet of available cars.
  
### Testing Integration of [Vincent edit here]

## System Testing
### Testing customer use case
Creation of new customer account, checking nearest vehicles, successfully completing a transaction
```c++
// Assume that the database is already filled with cars that have been validated
Customer newCustomer(name = "Johnny", email = "johnny_appleseed@tester.com", password = "suP3rSecR3tP@SS", age = 26)
newCustomer.searchForLocation("5500 Campanile Dr, San Diego, CA 92182")

Output: customerGPS.CurrentCord == (32.778, -117.071)
```
First part of the test is to create a new customer from scratch and initialize all relevant user data: email, password, name, and age. Following that is a test to make sure that the GPS object was initialized with the proper coordinates from the address provided.
```c++
Transaction newTransaction(newCustomer, chosenCar)
newTransaction.checkRequirements(newCustomer)
```
### Testing employee use case
Adding, removing, and checking current vehicle fleet
```c++
Employee.addAvailableCar(new RentalCar)
```
