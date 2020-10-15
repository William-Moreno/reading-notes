# Programming with JavaScript

---

## How JavaScript Makes Web Pages More Interactive

JavaScript allows us to make web pages more interactive and responsive based on four abilities it possesses:

- **Access Content** - access to the content of a page such as elements and attributes
- **Modify Content** - the ability to add content to or remove content from the page
- **Program Rules** - specifying a set of steps or rules the browser can follow which allows it to access or change the content
- **React** - respond to specified events triggered by the user or browser

## The ABCs

- Scripts are a series of step-by-step instructions that a computer can follow.
- The browser may only use different parts of the script dependent on situations and user interaction.

## Writing a Script

To create a script , we start with a big picture of what we want to achieve and then break it down into smaller tasks. Creating a script can be broken down into three general steps:

- Define the Goal
  - Determine what _puzzle_ you want the computer to solve
- Design the Script
  - Split the goal into a series of tasks _(best accomplished using a flowchart)_
  - Further split the identified tasks into individual steps required to achieve them
- Code Each Step

  - Using a programming language the computer understands _(in this case JavaScript)_ write the code to accomplish each step

## Thinking Like a Computer

Computers think **programmatically**. Simply stated, they follow a series of explicit step-by-step instructions to solve a problem. Successful programmers often develop the ability to "think like a computer", which better enables them to write directions for one.

## Expressions, Operators and Functions (oh my...)

An **expression** results in a single value. There are basically two types of expressions:

- Expressions that assign a value to a variable
  - `var color = 'beige';`
- Expressions that use two or more values to return a single value
  - `var area = 3 * 2;` or `var gamma = alpha * beta;`

Expressions rely on **operators** to create a single value from multiple values. The types of operators are:

- **Assignment** - Assign a value to a variable.
  - In `var this = 'that';` the `=` is the operator
- **Arithmetic** - Perform basic math.
  - `+` `-` `/` `*` `++` `--` `%`
  - Arithmetic operators follow the standard order of execution
- **String** - There is only one string operator, `+` and it combines or _concatenates_ two strings.
  - `greeting = 'Hi ' + 'Molly';` makes the value of greeting = 'Hi Molly'
  - When numbers and strings are added together the result is a string. If any other arithmetic operators are applied to a string the result will be `NaN`, or 'Not a Number'

**Functions** are a series of statements grouped together into a single block that instruct the browser to perform a certain task. A function must be **declared** or defined. having declared a function we can then **call** that function any time we want the computer to perform that task.

Declaration of a function requires the function keyword, a function name, also called an **identifier**, we designate, possibly a list of parameters the function requires and a series of one or more statements located inside curly brackets. to perform the given task. An example might be:

```
function sayHello() {
 document.write('Hello!');
}
```

- `sayHello` is the function's name
- this function requires no parameters
- `document.write('Hello!);` is the statement the function will execute

If a function requires specific information in order to perform its task, there will be a list of **parameters** inside the () following the function's name. For instance, in the case of `getArea(width,height)`, the getArea function would need the values for width and height supplied to it in order to execute its task. When we supply this information is is known as passing **arguments** into the function. In the case above, we would pass in values for _width_ and _height_.

Finally, by including the `return` keword in the statements of the function we can have the called function return a value and then exit the function, ignoring any subsequent statements remaining in the block.

[Back to Main](README.md)
