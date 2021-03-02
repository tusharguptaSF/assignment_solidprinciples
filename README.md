# SOLID Principles Assignments

##Exercise 1:
Examine the Text.ts class in exercise1. 
If you find any violation of any SOLID principles, refactor it.

### Note to Mentor
The Text class is violating Single responsibility principle. It is doing too many things:    
* Representing text
* Formatting text
* Printing text 
You should break this class into smaller classes each responsible for doing one thing.

#### Solution

* Text.ts
* TextFormatter.ts
* Printer.ts

## Exercise 2:
Consider an insurance system that validates health insurance claims before approving one.
The process is as follows:
1. A customer of the company files a claim to the manager
2. A health insurance surveyor is assigned to the manager. The surveyor validates a claim
3. The manager either approves or rejects the claim

The system with skeleton code is present in exercise2. However the code violates the SOLID principles. 
Analyze to identify the violated principle. Refactor the code. 

### Note to Mentor
The exercise code is violating both Open/Close Principle and Dependency Inversion principle.
The code is not open for extension without modification.    
If we add a CarInsuranceSurveyor, the Manager class needs modification because it is tightly coupled to the concreete class HealthInsuranceSurveyor.

The solution shows how to create an abstraction (Surveyor interface) and refactor the Manager to code against the abstraction instead of concrete implementation.



## Exercise 3:
You are developing an application that models a toy builder. Each toy will have a price and
color. Some toys, such as a toy car or toy train can additionally move, while some toys, such as a
toy plane can both move and fly.

The system with skeleton code is present in exercise3. However the code violates the SOLID principles. 
Analyze to identify the violated principle. Refactor the code. 

### Note to Mentor
The exercise code is violating Interface Segregation principle.
The Toy interface is defining multiple contracts thyat might not be required to be implemented by sub classes.
As a result, in the exercise code, TrainToy and StationaryDollToy were forced to implement methods that they don't require.

This violation can be addressed by segregating the interface into multiple ones.

The solution shows the contract segregation into three interfaces:
* `Toy.ts`
* `Flyable.ts`
* `Movable.ts` 

Now Toy implementations can implement only those interfaces they require.


## Exercise 4:
Consider the scenario of an electric switch that turns a light bulb on or off. Implement the
requirement with code

The system with skeleton code is present in exercise4. However the code violates the SOLID principles. 
Analyze to identify the violated principle. Refactor the code. 

## Note to Mentor
The exercise code similiar to Exercise 2 is violating both Open/Close Principle and Dependency Inversion principle.
The code is not open for extension without modification.
We cannot add a ElectricFan to the system without modifying ElectricSwitch     

The solution shows how to create  abstractions (Switchable and ElectricDevice interfaces) and refactor the current code in ElectricSwitch against the abstraction instead of concrete implementation.
