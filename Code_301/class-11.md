# EJS
---
## EJS

**EJS** is a templeting language or engine that we can use to generate HTML with plain JavaScript. EJS stands for Embedded JavaScript. It is most useful when we have to output when we are dealing with real-time updates or generating dynamic contents.

Even though there are a number of options to use for these kinds of processes, EJS is popular because it is relatively esy to set up and its syntax and logic is simple.

To use EJS, we must first install it in our project folder as follows:

```
npm install ejs --save
```

### Intro to EJS

The following notes were drawn from the video series [*"Intro to EJS in ExpressJS"*](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt) by *WalkThroughCode*.

#### Getting Started

After installing ejs in our project folder we need to create a folder named *views* and a file named *index.ejs*.

In our server.js we need to add lines to `require('body-parser');` and `require('path');` We also ne to add the following code:
- `app.use('body-parser');`
- `app.set('views', path.join(_dirname, 'views'));`
- `app.set('view engine', 'ejs');`
- `app.get('/', function(req,res) {res.render('index');
});`
- `app.listen(8000, function() { console.log('heard on 8000');
});`

#### Injecting and Evaulating Variables

Variables can be inserted into EJS templates and evaluated as well. to evaluate the variables we must remember to include the `=` character in the EJS tags. For instance:
```
<%= foo %>
```

#### For Loops and Arrays

We can use a line in our server.js to loop through arrays in out EJS template file to generate viewable content:
```JavaScript
res.render('index', { people: [ {name: bob}, {name: sam}]});
```

...and, inside our index.ejs, we include this code:
```
<ul>
  <% for(var person of people) { %>
  <li><%= person.name %></li>
  <% } %>
```

#### If/Else

In the same basic manner, we can include if/else statements in our EJS. Care must be taken to be sure we include the evaluate character `=`, if we need the actual value of a variable in our EJS.

## Google Books API Docs



[Back to Main](../README.md)
