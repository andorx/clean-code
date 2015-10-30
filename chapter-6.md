### Chapter 6: Objects and Data Structures

The reason that we keep our variables private that is we don't want anyone else to depend on them. Why, then, do so many programmers automatically add getters and setters to their objects, exposing their private variables as if they were public?

###### Data Abstraction
Hiding implementation is not just a matter of putting a layer of functions between the variables. Hiding implementation is about abstractions!

> A class does NOT simply push its variables out through getters and setters.

That allow its users to manipulate the essence of the data, without having to know its implementation.
E.g:
```javascript
public interface Point {
	// avoid that ridiculous implement
	double getX();
	double getY();

    // should be
    double getFuelTankCapacityInGallons();
	double getGallonsOfGasoline();
}
```
We want to express our data in abstract terms. This is not merely accomplished by using interfaces and/or getters and setters.

###### Data/Object Anti-symmetry
- Objects **hide their data** behind abstractions and expose functions that **operate on that data**.
- Data structure **expose their data** and have **no meaningful functions**.
E.g:
```java
public class Square {
    public Point topLeft;
    public double side;
}
public class Rectangle {
    public Point topLeft;
    public double height;
    public double width;
}
```
```java
public class Geometry {
	public final double PI = 3.141592653589793;

	public double area(Object shape) throws NoSuchShapeException
    {
        if (shape instanceof Square) {
        Square s = (Square)shape;
        return s.side * s.side;
        }
        ...
	}
```
** Read the ebook for more detail - Page 97 **

###### The Law of Demeter
> Objects hide their data and expose operations

**Law of Demeter**
> The mthod *f* of a class *C* should only call the methods of these:
> - C
> - An object created by *f*
> - An object passed as an arguments to *f*
> - An object held in an instance variable of *C*

The method should not invoke methods on objects that are returned by any of allowed functions.
In other words, talk to friends, not to strangers.

###### Train wrecks
Another way to call chain method
E.g:
```java
final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath();
```

###### Hybrids
Avoid creating them. They are indicative of a muddled design whose authors are unsure of - or worse, ignorant of - whether they need protection from functions or types.

###### Hiding structure
// Comback later

###### Data transfer objects
the quintessential form of *data structure* is a class w/ pbulic variables and no functions. This sometimes called a data transfer object (DTO). DTOs are very useful structures, especially when communicating w/ databases or parsing messages from sockets...

###### Active Record
Active Record are special forms of DTOs. They are data structures w/ public variables; but they typically have navigational methods like *save* and *find*. Typically these ACs are direct translations from database tables, or other data sources.

Treat the AC as a data structure and to create separate objects that contain the business rules and that hide their internal data.

###### Conclusion
Objects expose behavior and hide data.
- This makes it easy to add new kinds of objects without change  existing behaviours
- It also makes it hard to add new behaviors to existing objects

Data structures expose data and have no significant behavior.
- This makes it easy to add new behaviors to existing data structures
- Make it hard to add new data structure to existing functions

























