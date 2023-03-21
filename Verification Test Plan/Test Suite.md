# Test Suite
## Unit Testing
### RentalCar.setCarMake(name)
```
<void, setCarMake(name = “Toyota”)>
RentalCar.make == “Toyota”
```
This test case should not return anything, but it should set the string attribute “make” to “Toyota” in the RentalCar class. When this content of “make” is compared to the “Toyota” function argument, a value of true should be returned. This indicates that the make attribute in the RentalCar class was properly set with the function argument  “Toyota.”

```
<void, setCarMake(name = "") >
Rentalcar.make == ""
```
This test case should not return anything, but it should set the string attribute “make” to an empty “” string in the RentalCar class. When RentalCar’s make attribute is compared to its argument, or the “” string, a value of true is returned. This indicates that the make attribute was properly set with “”.

```
<void, setCarMake(name = 5)>
Error: Invalid input
```
This test case should print an error message since the function argument, 5, is not a string argument. This error message should indicate that RentalCar.make should NOT equal 5 since an incorrect type is passed as an argument to the setCarMake function. This indicates that the make attribute in RentalCar class was not properly assigned.

```
<void, setCarMake(name = 'c')>
Error: Invalid input
```
This test case should print an error message since the function argument, c, is not a string argument but a char argument. This error message should indicate that RentalCar.make should NOT equal ‘c’ since an incorrect type is passed as an argument to the setCarMake function. This shows that the make attribute in RentalCar class was not properly assigned.

## Integration Testing

## System Testing
