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

[Back to Main](README.md)
