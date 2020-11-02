# Problem Domain, Objects and the DOM

---

## Understanding Problem Domains

Many problem domains we face as programmers are difficult to understand. Often, these problem domains also look completely different depending on individual viewpoints.

Programmers are also routinely not given complete information about the problem domain, whihch leads to the issue of not even having the information needed to understand it.

## Programming Is Easy If You Understand...

When the problem domain is understood, dlear and concise, writing the code becomes far easier.

> Understanding is the most critical piece...

Coversely, it is difficult to solve a problem before you know what the question is.

## What can we do?

We can do one of two things:

1. Make the Problem Domain easier, simpler, less complex, etc.
   - The domain can sometimes be made easier by cutting out cases and narrowing focus to a smaller piece of the problem.
1. Get better at understanding Problem Domains.
   - We can become better at understanding problem domains, and avoid rushing to start coding before we thoroughly understand enough of the problem domain.

It may take a little more time and money to invest in understanding, but it cost significantly more to have to do things over rather than get them right the first time.

## JavaScript Objects

**Objects** group together a set of variables and functions to create a model of something. In an object, variables and functions take on new names. In an object:

- _variables_ become known as _properties_. Properties tell us about the object. The value of a property can be a string, number, Boolean, array, or even another object.
- _functions_ become known as _methods_. Methods represent tasks that are associated with the object. The value of a method is always a function.
- Properties and methods have a name and a value. The name is called a **key**.
- An object cannot have two keys with the same name, because keys are used to access their corresponding values.

In JavaScript:

- Variables have a name and an assigned value of a string, number or Boolean.
- Arrays have a name and a group of values. _(Each item in an array is a name/value pair because it has an index and a value.)_
- Named functions have a name and value that is made up of a set of statements to run when the function is called.
- Objects consist of a set of name/value pairs, but the names are referred to as keys.

### Creating an Object: Literal Notation

Literal notation is the easiest and most popular way to creat objects. The object is the set of keys and values inside a set of curly braces. It is stored in a variable.

```JavaScript
var hotel = {
   name: 'Quay',
   rooms: 40,
   booked: 25,
   checkAvailability: function() {
      return this.rooms - this.booked;
   }
};
```

When creating an object:

- Separate each key from its value with a colon.
- Separate each property and method with a comma. (But not after the final value)
- In the `checkAvailability()` method above, the **this** keyword is used to indicate that it is using the _rooms_ and _booked_ properties of **_this_** object.
- Treat values for properties like we would for variables, strings live in cuotes and arrays line in square brackets.

### Accessing an Object and 'Dot Notation'

We can access the properties or methods of an object using dot notation. We can also access properties using square brackets. To access properties of methods of objects, we use the name of the object followed by a period and then the name of the property or method we want to access. This is called **dot notation**. The period is known as the **member operator**.

```JavaScript
var hotelName = hotel.name;
```

We can also access the properties or methods using square bracket syntax.

```JavaScript
var hotelName = hotel['name'];
```

This notation is most commonly used when:

1. THe name of the property or method contains special characters
1. The name of the property is a number (technically allowed, but should be avoided).
1. A variable is being used in place of the property name

Functions that are used as methods of an object can still have parameters. When called as methods, arguments are passed to the method just like when we call a regular function.

[Back to Main](README.md)
