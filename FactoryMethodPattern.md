# Factory Method Pattern

## Usage

Objects need to be instantiated somewhere. In order to be sure the object is correctly instantiated, use the factory to instantiate the object.

It's possible that the instantiation of an object is very complex. You might need computation to determine the parameters to pass to the object.

Polymorphism is a benefit of the Factory. If you have a factory that wraps your object's construction, and the factory is an instance. Then at runtime you can swap that instance, for an instance of another factory.

### Heads First definition

> The factory method pattern defines an interface for creating an object. But lets subclasses decide which class to instantiate. Factory method lets a class differ instantiation to subclasses.

## UML Diagram

![UML Diagram](https://github.com/tinchovictory/DesignPatterns/raw/master/Assets/FactoryMethodPattern/uml.png "UML Diagram")

## Example

![UML Example Diagram](https://github.com/tinchovictory/DesignPatterns/raw/master/Assets/FactoryMethodPattern/example.png "UML Example Diagram")
