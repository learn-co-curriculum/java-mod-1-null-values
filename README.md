# Null Values

## Learning Goals

- Define what a null is
- Explain the `NullPointerException`

## What is a Null Value?

The **null value** is used to represent the absence of a value. The `null`
keyword is a reserved word in Java and is neither a type nor an object. It was
created as a way to point a reference variable to nothing.

Let's look at the different types of variables again: primitive types and
reference types.

As we recall, primitive types are predefined types in Java. These data types
also have an underlying default value. For example, an uninitialized `int` will
default to 0 and an uninitialized `boolean` will default to false:

```java
int firstNumber = 8;
int secondNumber;
double thirdNumber = 4.5;
double fourthNumber;

System.out.println(firstNumber);
System.out.println(secondNumber);
System.out.println(thirdNumber);
System.out.println(fourthNumber);
```

The above will have an output like this:

```plaintext
8
0
4.5
0.0
```

So if primitive data types have a default value, what about reference types?
Do they have a default value? The answer is they do - and it's `null`. The
`null` value is the default value for all reference types (objects and `String`
data types). This means, in memory, if we do not initialize the reference type
when we first declare it, the variable in the stack will point to `null` in the
heap. Let's see what happens when we don't initialize a reference
variable!

```java
String nullString;

System.out.println(nullString);
```

The output of the above will look like this:

```plainttext
null
```

If we want, we can even assign a reference type to `null` like so:

```java
String nullString = null;
```

Notice that the `null` is in all lowercase letters. The casing of the word
matters. If the code were to be written `String nullString = NULL` it would not
compile.

The `null` value is only to be used with reference types and not primitives. If
we were to assign a primitive type to `null`, we would get an error about the
type being incompatible. But, as we remember from our Type Casting lesson, we
can use the `null` value with the wrapper classes. 

```java
int x = null;    // Will result in an error at compilation

Integer y = null;    // this is okay since Integer is a reference type
```

## NullPointerException

The `NullPointerException` is a runtime exception that we may see occur in our
programs from time to time. This is a more common exception to be on the lookout
for! `NullPointerException` is thrown when we try to use an object that has a
value of `null`. Consider the following:

```java
public class Cat {

    public void purr() {
        System.out.println("Purr");
    }

    public static void main(String args[]) {
        Cat tom = new Cat();
        Cat garfield = null;

        garfield.purr();    // Would throw a NullPointerException
    }
}
```
