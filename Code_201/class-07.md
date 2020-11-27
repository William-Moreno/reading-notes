# Domain Modeling, HTML Tables and JavaScript Constructor Functions

---

## Domain Modeling

Domain modeling is the process of creating a conceptual model for a specific problem. A domain model that's articulated well can verify and validate the understanding of a specific problem.

When building domain models:

1. When modeling a single entity that will have many instances, build self-contained objects with the same attributes and behaviors.
1. Model its attributes with a constructor function that defines and intializes properties.
1. Model its behaviors with small methods that focus on doing one job well.
1. Create instances using the `new` keyword followed by a call to a constructor function.
1. Store the newly created object in a variable so you can access its properties and methods from outside.
1. Use the `this` variable within methods so you can access the object's properties and methods from inside.

## HTML Tables

A table represents information in a grid format. Examples might be: financial reports, TV schedules and sports results.

### Basic Structure

```HTML
<table>
 <tr>
  <td>15</td>
  <td>15</td>
  <td>30</td>
 </tr>
 <tr>
  <td>45</td>
  <td>60</td>
  <td>45</td>
 </tr>
 <tr>
  <td>60</td>
  <td>90</td>
  <td>90</td>
 </tr>
</table>
```

- `<table>` - this is used to create a table
- `<tr>` - indicates the start of each new row
- `<td>` - represents each cell of a table
- `<th>` - this element is used like the `<td>` element but its purpose is to represent the heading for either a column or a row _(indicated by the scope attribute)_

Cell data can span multiple columns or rows. This is done by assigning the specified `<td>` element with either the `colspan` or `rowspan` attribute and a value.

Information in long tables should be broken down into three elements. This helps people with screen readers as well as allowing us to style the different sections.

1. `<thead>` - The headings of the table should sit inside this element
1. `<tbody>` - The body of the table should sit in this element
1. `<tfoot>` - The footer of the table belongs in this element

## JavaScript Constructor Functions

The `new` keyword and the object constructor create a blank object which we can then add properties and methods to. For example:

```JavaScript
var hotel = new Object();

hotel.name = 'Quay';
hotel.rooms = 40;
hotel.booked = 25;
hotel.checkAvailability = function() {
 return this.rooms - this.booked;
};
```

### Updating an Object

To update the value of properties, use dot notation or square brackets. These work on objects created in either of the two ways. To delete a property, use the `delete` keyword. The value of properties can be changed or, if the object doesn't already have the property, the property can be added to the object in the following ways:

```JavaScript
hotel.name = 'Park';
```

or

```JavaScript
hotel['name'] = 'Park';
```

### Creating Many Objects: Constructor Notation

When we want several objects to represent similar things, we can use a function as a template as an object constructor.

Example:

```JavaScript
function Hotel(name, rooms, booked) {
 this.name = name;
 this.rooms = rooms;
 this.booked = booked;
 this.checkAvailability = function() {
  return this.rooms - this.booked;
 };
}
```

You can create instances of the object using the constructor function. The `new` keyword followed by a call to the function creates a new object with properties that were given to the function as arguments.

```JavaScript
var quayHotel = new Hotel('Quay', 40, 25);
var parkHotel = new Hotel('Park', 120, 77);
```

Properties can be added to objects using dot notation. They can even be removed by using the `delete` keyword.

## This

The keyword `this` is commonly used inside functions and objects. Where a function is declared alters what `this` means. It always refers to one object, usually the object in which the function operates.

- **A Function in Global Scope** - when a function is not inside another object or function it is in the global scope. The default object therefore becomes the `window` object, so `this` refers to the `window` object.
- **A Method of an Object** - When a function is defined _inside_ an object, it becomes a method. In this case, `this` refers to the containing object.
- **Function Expression as Method** - If a named function was defined in the global scope, and then it is used as a method of an object, `this` refers to the object it is contained within.

## Arrays

Arrays are a special type of object that hold a related set of key/value pairs, but the key for each value is an index number. We can combine arrays and objects to create complex data structures.

- Arrays can store a series of objects
- Objects can also hold arrays as values of their properties

## Built-In Objects

There are three groups of built-in objects. They all have a variety of related properties and methods.

1. Browser Object Model
   - Window
     - Document
     - History
     - Location
     - Navigator
     - Screen
1. Document Object Model
   - document
     - element
     - attribute
     - text
1. Gobal JavaScript Objects
   - String
   - Number
   - Boolean
   - Date
   - Math
   - Regex

## Data Types

In JavaScript there are six data types. Five of them are described as simple, or primitive, data types. The sixth is the object and is considered as a complex data type. Simple data types can still have methods and properties. The five simple types are:

1. String (properties and methods of the `String` object can be used on these)
1. Number (properties and methods of the `Number` oblect can be used on these)
1. Boolean (while there is a Boolean object, its properties and methods are rarely used)
1. Undefined (does not have an object)
1. Null (does not have an object)

## The Date Object

In order to work with dates, we create an instance of the `Date` object. We can then specify the time and date that we want to represent. Once we have create a `Date` object, there are a variety of methods that let us manipulate that object.

```JavaScript
var today = new Date();
```

[Back to Main](../README.md)
