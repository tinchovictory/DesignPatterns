# Decorator Pattern

## Usage

An original object is wrapped in a *decorator* object, where every connection to the original object goes throw the wrapper object. It provides the benefit of adding dynamic functionality to a component.
An `Object A` can be wrapped with `Decorator A`. Then `Decorator A` can be wrapped with `Decorator B`.

### Heads First definition

> The decorator pattern, attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

## UML Diagram

![UML Diagram](https://github.com/tinchovictory/DesignPatterns/raw/master/Assets/DecoratorPattern/uml.png "UML Diagram")

## Example

![UML Example Diagram](https://github.com/tinchovictory/DesignPatterns/raw/master/Assets/DecoratorPattern/example.png "UML Example Diagram")

```
public abstract class Beverage {
  public abstract int cost();
}
```

```
public class Espresso extends Beverage {
  public int cost() {
    return 1;
  }
}
```

```
public abstract class AddonDecorator extends Beverage {
  public abstract int cost();
}
```

```
public class Caramel extends AddonDecorator {
  private Beverage beverage;

  public Caramel(Beverage beverage) {
    this.beverage = beverage;
  }

  public int cost() {
    return this.beverage.cost() + 2;
  }
}
```