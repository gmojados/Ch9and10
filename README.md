# Ch9and10
# Chapter 9 
The stack and the heap is where things "live"
**The Stack**
This is where method invocations and local variables live
**The Heap**
Where all objects live - AKA "The garbage collettible heap"

**Instance Variables**
Instance variables are declared inside a class but not inside a method
- Represent the fields that each individual object has
  
Ex: public class Universe (){
String planet
int size
_In this example planet and size are Instance variables_
}

**Local Variables**
Local variables are declared inside a method, including method parameters.
-They are temporrary; live only as long as the method is on the stack.

Ex: public void eat(String food) (){
_In this example "food" is the local variable_
}
---------------------------------------------------------
**Methods are stacked**
-When methods are called it lands on top of the "stack"
-The new thing pushed onto the stack is the stacks "Frame"
-The method on top of the stack is always the currelty running method for that stack
-the frame holds all the code; and **local** variables
-If the local variable is a reference to an object, only the variable goes on the stack
----------------------------------------------------------
**Where do Instance variables  live**
-Instance variables live in on the "Heap" inside the object they belong to
-----------------------------------------------------------
**Constructors**
When we create objects we call the constructor

Ex:
Car myCar = new Car();
_"new car()" is the constructor_

- You can write a constructor for the class OR the complier writes one for you!
- The construcot must be the same as  the class name

- Ex:
public class guitar {

public guitar(){
  System.out.println("Strumming")
  }
}

**THE MAIN CLASS**

public static void main (String[] args) {
  Guitar guitar1 = new Guitar();
 }
 ----------------------------------------------------------
 **Using a Setter**
 -Use a setter to set a variable
 Ex:
 public class guitar {
 
  String type;
  
public guitar(){
  System.out.println("Strumming")
  }
  
  public void setType(String newType){
  type = newType
  }
}

**The Main Class**

public static void main (String[] args) {
  Guitar guitar1 = new Guitar();
  guitar1 = setType("electric");
 }

 -You can also pass it in the constructor as a parameter to be more efficient
 -------------------------------------------------------------
 -Overloaded constructors means you have more than one constructors in your class
 - _In order for it to compile each construcor must have a different argument list_
 - You can havetwo constructors that have identical types as long as the order is different
 -When you create an object that object is also part of the superclass of that parent
- for example a guitar object is also a instrument
- you would use  **"super"** to invoke the superclass constructor
---------------------------------------------------------------
# Chapter 10
**Methods in the Math class don't use any instance variable values. and because the methods are "Static" you dont need to have an instance of Math. All you need is the math class**
-If you try to make an instance of Class Math you'll get an error saying that it's privated that means you can never use the "new" keyword when creating it

-**Static** methods run without any instance of the class(Must use that static keyword)
-meaning  behavior is not dependent on an instance variable so no instace/object  is required; just the class
Ex:
public static int min(int a, int b) {
}

Math.min(12,6)
^ _Calling the class and the min method with parameters that will return the lesser of the parameter_

-With **Non-Static** methods you would use the reference variable 
Ex:
Cat cat1 = new Cat();
cat1.scratch();
^ _Calling reference variable cat1_

- You cannot use "New" in an abstract class
- **"It's impossible to instantiate an abstract class"**

**Static methods can't use non-static instnace variables**
-Static methods run without knowing about any particular instace of the static method's class. 
**Static methods can't use non-static methods either**
-Non static methods usually use instance variable stat to affect the behavior of the method. 

Static variables value is the same for ALL instances of the Class.
Ex:
 public class guitar {
 
  private String type;
  private static int guitarCount = 0;
  
  public guitar(){
    System.out.println("Strumming")
  }
  
  pulic guitar(){
    guitarCount++; <----------_now it will keep incrementing each time the guitar Constructor runs because the guitarCount is static and won't be set to 0._
    
  }

  **Static variables a re shared. All instancces of the same class share a single copy of the static variables
  Instance variable: 1 per Instance
  Static bariables: 1 per class

  -All static variables in a class are intialized before any object of that class can be created
  EX:

public  static void main (String[] args) {
  System.out.println(Guitar.guitarCount);
  Guitar guitar1 = new Guitar;
  System.out.println(Guitar.guitarCount);

}

  - static final variables are constants
  - Constant variable names should be in all caps
  - Final variables don't change

  Ex:
   public class guitar {
 
  private String type;
  private static int guitarCount = 0;
  public static final int STRINGS = 6;
  ^Guitar ALWAYS has six strings
  ------------------------------------------------------------------
  # Math Methods
  
  - Math.random()
  - Math.abs()
  - Math.round()
  - Math.min()
  - Math.max()

---------------------------------------------------------------------
# Number Formatting

String s = String.format("%,d",1000000000)
**%[argument number][flags][width][.precision] type**
("%,5.1f",42.000)
-You must include a type in your format instructions, and if you specify things besides type, type must always come last.

# Key Calendar Methods
- add(int field, int amound)
- get(int field)
- getInstance()
- getTimeInMillis()
- roll(int field, boolean up)
- set(int field, int value)
- set(year, month,day,hour,minute)
- setTimeInMillies(long millis)

  # Key Calendar Fields
- YEAR: The field indicating the year.
- MONTH: The field indicating the month.
- DAY_OF_MONTH: The field indicating the day of the month.
- DATE: Synonym for DAY_OF_MONTH.
- HOUR: The field indicating the hour of the day.
- MINUTE: The field indicating the minute within the hour.
- SECOND: The field indicating the second within the minute.
-  MILLISECOND: The field indicating the millisecond within the second.
