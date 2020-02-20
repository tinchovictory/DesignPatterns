# Observer Pattern

## Usage

There are two objects. `Object A` changes state, and `Object B` needs to know whenever `Object A` changes. `Object B` is called *subscriber* (there can be many simultaneous *subscribers*).

Represents a push architecture. The `Object A` is responsible to *push* the notification of having change to all the *subscribers*

`Object A` has the knowledge of who the *subscribers* are. Before the *push* is possible `Object B` the *observer* needs to register to `Object A` the *observable*.

When the *observable* changes the *observers* are notified.

### Heads First definition

> The observer pattern defines a one to many dependency between objects, so when one object changes state, all its dependencies are notified and updated automatically.

## UML Diagram

![alt text](https://github.com/tinchovictory/DesignPatterns/raw/master/Assets/ObserverPattern/uml.png "UML Diagram")

## Example

![alt text](https://github.com/tinchovictory/DesignPatterns/raw/master/Assets/ObserverPattern/example.png "UML Example Diagram")


```
interface IObservable {
  add(IObserver o);
  remove(IObserver o);
  notify();
}
```

```
interface IObservable {
  update();
}
```

```
class WeatherStation implements IObservable {
  private ArrayList<IObserver> observers;
  private int temperature;

  public WeatherStation() {
    this.observers = new ArrayList<>();
    this.temperature = 0;
  }

  public void setTemperature() {
    // Logic to update temperature value
    ...

    notify();
  }

  public int getTemperature() {
    return this.temperature;
  }

  // IObservable methods
  public void add(IObserver o) {
    this.observers.add(o);
  }

  public void notify() {
    for(IObserver o : this.observers) {
      o.update();
    }
  }
}
```

```
class PhoneDisplay implements IObserver {
  private WeatherStation station;
  
  //Injecting the weather station in the constructor 
  public PhoneDisplay(WeatherStation station) {
    this.station = station;
  }

  // IObserver methods
  public void update() {
    this.station.getTemperature();
  }
}
```

```
class Main {
  public static void main(String[] args) {
    WeatherStation station = new WeatherStation();
    PhoneDisplay display = new PhoneDisplay(display);

    // Change the station temperature
    station.setTemperature();
  }
}
```
