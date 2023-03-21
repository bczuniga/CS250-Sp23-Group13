# Test Suite
## Unit Testing
### Setting Car Make
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

## Integration Testing
### Creating a new Car object and interact with Employee class
```c++
RentalCar newCar("Toyota", "Prius", BLACK, HATCHBACK)
Employee.validateRentalCar(newCar)
newCar.validCar == true
Employee.addAvailableCar(newCar)

Output: Employee.checkAvailableCar(newCar) == true
```
This test case should add the newCar RentalCar object to the availableCars Map located in RentalLocaton. The newCar RentalCar object’s attributes are set according to the string arguments: make is set to “Toyota”, model is set to “Hatchback”, color is set to “Black”, and carBody is set to “Standard”. First, Employee.checkAvailableCar(newCar) should return false, indicating that the RentalCar is not currently added to the availableCars map. Afterwards, the newCar object is added to the availableCars map located in the RentalLocation, which is an object of the Employee class. After the newCar is added to the availableCars map, checkAvailableCar(newCar) should return true. The test case passes for this scenario.

```c++
RentalCar.newCar(4500, “Tundra”, GREY, TRUCK)
Employee.addAvailableCar(newCar)
Employee.validateRentalCar(newCar)
newCar.validCar == false 

Output: Employee.checkAvailableCar(newCar) == false
```
This test case should produce an error since the newCar object is not instantiated with proper arguments. Specifically, the make attribute for the RentalCar object is not properly set because the argument 4500 is an int value and not a string. An error message should appear saying that the newCar was not instantiated properly, so the newCar is not added to the availableCar map via the addAvailableCar(newCar) function in Employee class since it is not a valid object of the RentalCar class. Therefore, Employee.checkAvailableCar(newCar) will return false since newCar is not a valid object, thus indicating that the new car is not added to the fleet of available cars. 

## System Testing
### New customer signing up for a new account, checking nearest available vehicles, successfully renting a vehicle

### Employee manipulating the car fleet 
